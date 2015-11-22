---
layout: post
published: false
title: Switching Gears and Starting Fresh on Projects
comments: True
---
## I Deleted Everything and Started Over

Okay, I admit, I didn't delete EVERYTHING. I did however wipe out 90% of my
existing code after hitting a massive wall on Saturday night with my weekend
project. Our assignment was to take a fairly large dataset of 100,000 movie reviews
and do all kinds of fun data projects. I created a top 50 best reviewed movies, then
made a top 50 list based on movies that a particular reviewer (any reviewer)
hadn't reviewed yet. Then I started playing with recommending movies that similar
users had rated highly. I did some euclidian distance magic with a list of movies
that both users had reviewed and was able to find a list of similar users. Around
this mark somewhere (with my project tantalizingly close to being done) I hit a
pretty big problem.

My code started blowing up around 5pm and by 11pm I knew this was a problem that
may well not get worked out before Sunday night when my code was due. There is
definitely some part of the relationship between class objects and their 'memory'
that I'm missing. I
