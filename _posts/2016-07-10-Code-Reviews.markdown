---
title: "Code Reviews Are Awesome"
layout: post
date: 2016-07-10 22:48
image: /assets/images/markdown.jpg
headerImage: false
tag:
- Professional
category: blog
author: andrewpierce
description: Code Reviews at Work
# jemoji: '<img class="emoji" title=":ramen:" alt=":ramen:" src="https://assets.github.com/images/icons/emoji/unicode/1f35c.png" height="20" width="20" align="absmiddle">'
---


I've been at my current job for almost six months now. I've learned an incredible amount in that time, using Perl and Javascript and SQL and learning how to interact with a LAMP stack, as well as Ember. On top of all that, I've learned the general ins and outs of working in a professional development environment, which is arguably the most useful thing.

The best thing about working in a professional development environment, at least in my opinion, has been the code reviews. Code reviews are awesome! They've made me a MUCH better developer by giving me very targeted and honest feedback about the code I'm submitting.

Every single ticket I've been given over the past few months I've been able to provide a working solution to. Of that, I am actually pretty proud. However, I'm not always able to provide an ideal, or even good solution. Sometimes I just don't know the ins and outs of AT&T's numerous internal systems well enough and sometimes I just miss a generally better solution or don't know of a better way to write something until someone looks over my code and suggests something else.

For example, the other day I had a ticket to fix a common user error where people put invalid values in a certain text field where there are only a set number of accepted values. I created a validation function that checked whether the input was valid and then mapped the most common errors to their intended values.

You know what's way easier and makes way more sense to do here? A dropdown! That was the first thing my code review said. To paraphrase: "Your code works! However a dropdown seems like a better overall solution for this problem."

A dropdown took about ten minutes to code and was an easier solution for the user as well. They can see all the options and know exactly what they want. It's interesting because OBVIOUSLY a dropdown makes more sense here. I just didn't think about it. The original validation function I wrote was more technically challenging to write than the dropdown, but was a far worse solution.

Other times, I might get critiqued for not providing proper error handling or not handling some expected edge cases. It all depends on the specific problem and generally how familiar I am with that application and part of the code base.

I learn a lot by tackling new problems, and I learn even more by getting critiques on how to solve them in a better way. Many of the developers in my office have literally been professional developers since before my parents started dating, years and years before I was born. I love having that kind of expertise go into my code critiques and being able to learn every day about better ways to solve problems.
