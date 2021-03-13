+++
title="how to write about descriptive data in plain text"
date=2020-11-18
+++

This morning, I decided that I wanted to draw up a big chart of the daily routines that I've mapped out for myself, along with the times that I've assigned for myself to actually do them, and to compare it against the times that I actually did the things.  (You know, if at all.)  The hope is that by actually looking at this data right in front of me, I can reconcile the differences a little bit and make sure my routines continue to work without effort.

But this betrays an interesting question:  how would I write this sort of table in a way that could be shared?

## option one: don't

Honestly, maybe don't?  If you're running into this problem, is it really a problem to just share a spreadsheet instead?  If you don't have spreadsheet software handy while you're composing this, you could just hand-write a csv and then convert the file name later when you're sharing it.  (I actually do this all the time!)

So, as a concrete example, here's what the first few lines would look like in my csv:
<!-- I know this is messed up, but I wrote this when I didn't have a lot of time to actually fix the code block display here, so I'm leaving it.  Sorry! -->
```
time,planned,reality
06:30,"wake up, put away dishes, water pets, stretch, and
review my goal for the day","woke up, stared into my
phone while drinking coffee and trying to wake up"
07:00,start my flashcards,still scrolling on my phone
```

But you might be in a situation where the closest you could get to a good user experience with this text would be "okay, now save this text as a CSV and open it in your favorite spreadsheet editor."  That doesn't seem to cut it!

## option two:  no, really, don't

Maybe descriptive text would be better instead?  That way you're conveying the real meaning of the text you're writing, and potentially cutting out extraneous information; those things, combined with a more presentable format, means that your message might have a better chance of coming across the way you want it to.

An example:

> I woke up at 6:30 a.m.  I have the first half hour after I wake up set aside for small chores, like watering the pets, but instead I don't accomplish anything but staring at my phone.

## option three:  a table

If you know your text is always going to be read in an environment where the font is fixed width, you can always use a table in your text, but I think it's unlikely that this is going to suit your needs, either.

```
| time  | expectation        | reality                  |
|-------|--------------------|--------------------------|
| 06:30 | wake up, do chores | woke up, stared at phone |
| 07:00 | do flashcards      | still scrolling          |
```

## the real answer:  very long form text

So here's what I came up with:

> Time: 6:30  
> Expectation:  wake up, put away dishes, water pets, stretch, and review my goal for the day  
> Reality:  woke up, stared into my phone while drinking coffee and trying to wake up  
>  
> Time: 7:00  
> Expectation:  start my flashcards  
> Reality:  still staring at phone

Clearly, that's going to take up a lot of space. But it _definitely_ meets the requirements.  I think I'll just write the csv by hand instead, though.
