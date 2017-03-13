---
title: "Clean Code"
layout: post
date: 2016-04-03 22:48
image: /assets/images/markdown.jpg
headerImage: false
tag:
- Books
category: blog
author: andrewpierce
description: My Thoughts on the book Clean Code
# jemoji: '<img class="emoji" title=":ramen:" alt=":ramen:" src="https://assets.github.com/images/icons/emoji/unicode/1f35c.png" height="20" width="20" align="absmiddle">'
---


I just finished reading Clean Code, by Uncle Bob. Lately I've been really trying to
write _better_ code. I feel really confident that in most cases, I can figure out
some kind of working solution to whatever problem I'm asked to solve. The counterpoint
to that though, is I certainly can't make the claim that I can find solutions that
are either efficient or generally good readable code.

Reading Clean Code was a really great way to get some great, actionable, techniques
for writing better and cleaner code. I felt like one of my major barriers to writing
better code before, was that I just didn't really know what clean code looked like.
When I say that, I mean that while I was able to recognize that what I was writing
_wasn't_ clean, I wasn't exactly able to put my finger on what exactly was dirty about
it or how it had become that way.

Some things really stuck out to me that I've really tried to keep in mind while I'm
writing new code at work.

*Variable names.* One thing that Uncle Bob mentions that made a lot of sense is that
as developers, we're the authors of our code. With that idea, we should think of
ourselves as authors when we write code, and strive to make as easy an experience as
possible for those people reading our code. With descriptive names, people don't have
to guess what a variable contains or hunt down clues to what 'a' or 'obj' actually
contain.

*Smaller functions.* Uncle Bob says that every function should act on one layer of
abstraction. This makes a lot of sense. You should have high level functions, like a
main gameplay loop for example, that calls things like move_player() or fire_shot() or
whatever else your game is going to do. Then you'll have functions that are much
lower level, that might do things like directly change the coordinate values of your
player or missile. Doing it all in the same function gets pretty confusing pretty fast.

These lower level functions tend to also be code thats repeated more often, so its
pretty nice to have it wrapped up in a nice helper function.

*Clean out commented code.* This one comes up a lot at my current work place and now
that I've seen it, it drives me crazy to find commented out code still hanging out.
The reason for this makes a lot of sense, code that's commented out isn't being maintained.
Everyone is scared to delete it because they're not sure what it was supposed to do,
but thats the thing, it doesn't _do_ anything! It just confuses us and clutters up
our working space. He makes a good point that if you really need it, Git remembers.

*Formatting.* This one comes a little easier when you have small functions and aren't
hanging on to commented out code, but having nice formatting does make your code much
easier on the eyes. Python was the first language I learned, and I'm continually grateful
for it. Whitespace matters in Python and its given me a pretty good base for decent formatting.
