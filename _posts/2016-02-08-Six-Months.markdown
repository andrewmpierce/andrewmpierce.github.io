---
title: The Code Base is the Hardest Part
layout: post
date: 2016-02-08
image: /assets/images/markdown.jpg
headerImage: false
tag:
- Progress Update
- Six Months
category: blog
author: andrewpierce
description: Six Months at AT&T
# jemoji: '<img class="emoji" title=":ramen:" alt=":ramen:" src="https://assets.github.com/images/icons/emoji/unicode/1f35c.png" height="20" width="20" align="absmiddle">'
---

I've officially been at AT&T as a full stack developer for a little over six months. The time has truly flown
by. Turns out being a developer is pretty awesome.

I've learned a LOT in the past six months, but the biggest thing I've come away with is that learning the code base is
the biggest hurdle.

Depending on how big and hairy the code base you're diving into is, it definitely takes some
time to figure out what's going on with it. If I'm assigned to work on fixing a user submitted bug,
there are a ton of things to take into consideration when hunting down the problem. What kind of
APIs are we pulling from that could be giving us back a weird response? What databases are we using
to get the information we need, and what kind of values do they expect? What new features have we
rolled out recently and how could they cause problems?

Having a general idea of at least parts of the code base and how these things factor in make debugging
a much faster and easier process. If you have an idea of potential failure points surrounding the break or you're
working on fixing, you have a great checklist to go down before you start working on the really crazy potential
problems.

When it comes to writing new features, knowing the code base is just as beneficial. If I'm adding a feature into a
legacy code base, it has to work with the existing code. I have to figure out how the code base is giving me the information
that I'll need to incorporate. I need to have a basic idea of the libraries we're using and how to work those in if I
need and if not, how can I generally follow the style shown in the rest of the code base.

This all takes a significant chunk of time to get a handle on, but once you do, you'll be exponentially more efficient in your day to day debugging and in writing new features.
