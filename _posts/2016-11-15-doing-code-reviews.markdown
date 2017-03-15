---
title: "The Biggest Thing I've Learned by Doing Code Reviews On My Team"
layout: post
date: 2016-11-15 22:48
image: /assets/images/markdown.jpg
headerImage: false
tag:
- Mentoring
- Code Reviews
category: blog
author: andrewpierce
description: I just started doing code reviews on my team, I learned a lot!
# jemoji: '<img class="emoji" title=":ramen:" alt=":ramen:" src="https://assets.github.com/images/icons/emoji/unicode/1f35c.png" height="20" width="20" align="absmiddle">'
---
*A lot of people would be surprised to hear I wasn't previously doing code reviews, but it's really just a weird side effect of working in a massive company
with oddly segmented contracted and salaried employee divisions. I recognize that most people will be doing code reviews, or at least have access to PRs pretty
much from day one.*


Up until pretty recently, while I had received a lot of code review feedback, I had never performed a code review for another team member.
Our team is structured with contractor employees (me, and the majority of the devs on my team) doing most of the actual code writing, and a
few salaried AT&T employees who do mostly code reviews, architecture, handle deployments and Sev 1 issues, etc. They recently changed our
process a little so that all the issues worked on were first code reviewed by people on the contracting side, which means I get to do code reviews!.

One of the biggest drawbacks to me of never doing code reviews and not having access to other people's pull requests is that you simply don't know what the rest
of your team is working on and the relative difficulty of their assignments. They might briefly mention what they're working on in standup, but you don't
generally get a really good idea of what they're doing without looking at some code. As a result of this, whether based on some lingering Imposter's Syndrome or
whatever else, I had kind of always assumed they just gave me a bunch of easy issues to work on, relative to what everyone else was doing.

That totally wasn't true! With a few exceptions, all the tickets worked on were of relatively the same difficulty, or at least the average of the tickets was the same general difficulty. This made me feel pretty good about myself. Myself and one other developer on my team were hired directly out of code school at the same time, but every other developer on my team has a minimum of several years of experience and is a mid or senior level developer. I'm doing just as well as any of them! My work gets turned in in similar time frames, and my approaches are rarely very different from the approaches that my teammates take. I'm not saying that there isn't a LOT that these developers know that I don't, but I am saying that at least in this particular role, I'm able to produce real production code at the same level as the majority of my teammates.

It's also just really refreshing to see that literally every developer makes kind of stupid mistakes sometimes! Intellectually I knew this to be true, everyone is human! It's
easy for the occasional stupid mistake to slip through to code review, whether its just a glaring typo in some function documentation or forgetting to remove a console.log or
even just some flat out bad logic that works on your test cases, but is probably a little brittle. Seeing other people's mistakes is really key in recognizing that letting
the occasional error slip through doesn't mean you're a bad developer, it just means you let something slip through!

When all you see are your mistakes returned to you in code review, its easy to get the impression that you're a less capable developer than you actually are. Being able to see other people's mistakes is absolutely vital in understanding where you actually are in terms of engineering ability and productivity compared to your peers.
