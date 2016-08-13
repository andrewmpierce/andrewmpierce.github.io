---
layout: post
published: False
title: The Code Base is the Hardest Part... Probably
comments: True
---

I've officially been at AT&T as a full stack developer for a little over six months. The time has truly flown
by. I've loved my first six months as a professional developer, and really looking forward to the rest of
my career. The biggest thing that I've learned is that knowing the code base is most of the battle.

Depending on how big and hairy the code base you're diving into is, it definitely takes some
time to figure out what's going on with it. If I'm assigned to work on fixing a bug in the browser,
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
that I'll need to incorporate
