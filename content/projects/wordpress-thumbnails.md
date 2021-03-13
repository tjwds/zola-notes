+++
title="getting a widget of recent posts with thumbnails on wordpress"
date=2020-11-27
+++

Man, this was a frustrating thing to figure out.  Today's problem:  on Gutenburg WordPress, how do I add thumbnails to the recent posts widget that gets embedded in a page?

Turns out that WordPress now has two things that it calls "widgets."  The embeddable widgets are still a bit of a mystery to me, but I had a hard time figuring out how to add the post's thumbnail to the existing widget, and all of the existing "widget" plugins that did support other properties like thumbnails didn't seem to be embeddable in any way!

## the answer

You want the [Display Posts Shortcode plugin](https://wordpress.org/plugins/display-posts-shortcode/).  Get this and add shortcode blocks to your pages based on their documentation.

