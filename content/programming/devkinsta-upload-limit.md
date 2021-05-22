+++
title="Bypassing DevKinsta's 128 MB upload restriction"
date=2021-05-22
+++

I'm working on a WordPress site that has a _lot_ of content in it.  The thing is, there's now more than one person looking at the staging server I've set up on a random DigitalOcean droplet… so I wanted to be able to do some theme development locally, then eventually plop the new theme on the staging server.

I figured I'd give [DevKinsta](https://kinsta.com/devkinsta/) a shout.  I haven't had a lot of luck with Docker, but DevKinsta's branding is really cool, so that alone made me download it and fire it up.

The problem I ran into:  I'm using the "All-in-One WP Migration" plugin to back up the work on this staging server, right?  "I'll just pop that backup into my local devkinsta WordPress instance and it should just work, right?"

Wrong!

Everywhere, I see the dreaded maximum upload file size:  128 MB.

Normally, that would be a lot of bytes, but it turns out, this site is huge — our take-out clocks in at just over 162 MB.  Wolfram Alpha informs me that that's about a quarter of the capacity of a compact disk.

So:  how do we solve this?  DevKinsta has, at its core, a bunch of Docker containers talking to each other.  We need to update values in two of those containers:  `devkinsta_nginx` and `devkinsta_fpm`.

Fortunately, you can execute arbitrary commands in Docker containers from the command line.

## Update the nginx config

First, let's invoke:

`docker exec -i devkinsta_nginx cat /etc/nginx/nginx.conf > temp.conf`

Edit temp.conf, find the line which reads `client_max_body_size 128M;` and bump it up to, say, 256M.

Pipe your edited file back into the Docker container:

`docker exec -i devkinsta_nginx sh -c 'cat > /etc/nginx/nginx.conf' < temp.conf`

## Update the fpm config

Next, let's work on fpm.  This is the one I was least sure about — if anyone thinks that any of these steps aren't actually necessary, please let me know!

**Note:  I'm running php 7.4** in DevKinsta — you may need to change `7.4` in all of the commands below to whichever version you're running.

Let's do the same thing to get the file we need to edit:

`docker exec -i devkinsta_fpm cat /etc/php/7.4/fpm/php.ini > temp.ini`

(or, again, substitute in whichever version you're running for `7.4`)

Edit temp.ini and make sure these values are set high enough:  `upload_max_filesize`, `memory_limit`, `post_max_size`.  I set them all to `256M`.

Put it back:

`docker exec -i devkinsta_fpm sh -c 'cat > /etc/php/7.4/fpm/php.ini' < temp.ini`

I believe DevKinsta also set up an additional configuration file that we need to change too:

`docker exec -i devkinsta_fpm cat /etc/php/7.4/fpm/conf.d/tuning.ini > temp.ini`

Update those three values (`upload_max_filesize`, `memory_limit`, `post_max_size`) here as well.

Put it back:

`docker exec -i devkinsta_fpm sh -c 'cat > /etc/php/7.4/fpm/conf.d/tuning.ini' < temp.ini`

## Restart everything

Finally, just restart some stuff:

```
docker exec -i devkinsta_fpm service php7.4-fpm reload
docker exec -i devkinsta_nginx service nginx reload
```

Go back to your local DevKinsta WordPress instance, refresh the page, and you should see your updated file size limit!

## That's all

I'm not going to lie, figuring this out made me feel _really_ great.  Look, I mostly write javascript — I don't really look at servers that often, so this was a big one for me!

Kinsta, if you're listening, any chance you could bump this limit up a bit? ;-)

Thanks for reading!  Please reach out with any comments at joewoods at fastmail.com.

