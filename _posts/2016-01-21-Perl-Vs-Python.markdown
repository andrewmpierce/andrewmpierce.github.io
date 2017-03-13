---
title: "Perl Vs Python"
layout: post
date: 2016-01-21 22:48
image: /assets/images/markdown.jpg
headerImage: false
tag:
- Python
- Perl
category: blog
author: andrewpierce
description: A comparison of Perl based on my knowledge of Python
# jemoji: '<img class="emoji" title=":ramen:" alt=":ramen:" src="https://assets.github.com/images/icons/emoji/unicode/1f35c.png" height="20" width="20" align="absmiddle">'
---
Note: I wrote a Powerball simulator in Perl! [Check it out here.](https://github.com/andrewmpierce/powerball-simuluator-perl)


Lately I've spent a good bit of time learning and playing with Perl. While I'm still
certainly a lot more comfortable with Python than Perl, I can write basic programs and
read Perl code decently well.

I started picking up Perl mostly because I kept on seeing it paired with Python on job boards (which does make sense since they're both pretty useful scripting languages) and I've frequently heard Perl referred to as "The duct tape of the internet", which certainly sounds interesting.

Learning a new language in general has taught me SO much about programming in a broad sense and I'm really glad I dove in. Perl sometimes seems to behave in ways that surprise me, but I can't really determine if that's Perl being a weird language, or just a thing that I didn't know much about before.

My biggest program so far in Perl has been a Powerball simulator. With all the Powerball mania lately I wanted to create a simulator that would allow a user to 1) buy multiple tickets per draw and 2) incorporated the PowerPlay multiplier if the user so chose. I haven't seen these features in any of the most popular online simulators and thought it would be a fun project.

I ran into quite a few problems I wouldn't have had in Python. First, having to declare the scope of my variables was a really interesting problem to have. Several times I tried to call local variables, or 'my' variables, from outside their scope and obviously this didn't work. I have to be conscious of where I'm going to be using these variables and consciously use 'our' if I think I'll need the variable in a global scope. The 'local' keyword was also a pretty interesting way to redefine existing global variables in a limited local scope. In Python, I never thought about my variable's scope, I knew variables called in functions or methods were obviously local and unknown outside of it, but having to actively say the scope made me revisit the whole concept.

Later on, I discovered an incredibly frustrating bug in my program. I was trying to pass two arrays into a subroutine and it wasn't defining the second array. This really perplexed me. I went through every line of code thinking that it must be an error I made in the creation of the second array. Ultimately I googled my problem and discovered that apparently you just can't do that in Perl. You can pass in multiple scalars no problem, or pass in a single array, but trying to pass in more than array results in a single combined array for the first value. The work around is to create a scalar reference to your arrays, pass those in to your subroutine, and then effectively unpack them back into arrays once back inside the subroutine.

Interestingly, the core idealogies of Python and Perl are very much in conflict. The Zen of Python is that there should be one obvious way to do something, or the most 'pythonic' solution, this lends itself to pretty clear cut and simple code in comparison to a language like Perl. One of Perl's mottos is TIMTOWTDI or The Is More Than One Way To Do It. This creates code that is often pretty ugly looking and Perl is notoriously hard to read for anyone who didn't have a hand in writing the code in question. However, this also gives Perl a lot of flexibility and there's a lot that you can do with it, which is pretty appealing. Overall, the comparison to duct tape, effective but potentially ugly, seems pretty fair for Perl.
