---
layout: post
published: true
---
## Today I simulated intelligence

I just finished what I think has been the coolest project we have done so far in
my Python course. We programmed a pretty basic Game of Sticks, where the game is
played by setting a number of sticks, then each player picks between 1-3 sticks in
each round. Whoever picks the last stick loses. The two human player version was
pretty easy to program (who would have thought I would be saying that in less than
two weeks?) and I finished it quickly. The fun part was creating a computer player
that 'learned' after every game.

The setup was surprisingly simple. Our AI, we'll call them HAL, starts the game
session with a dictionary where every key is a possible remaining number of sticks
and the corresponding value is a list of the options it will choose from randomly.

So at the beginning our first game, HAL's playbook is filled with a bunch of [1, 2, 3]
entries. That's all they can do. A simple random.choice() function helps HAL decide
what to pick. However the fun part is in making a second dictionary of HAL's choices
for each game, so something that looks like:

<pre><code>
{19:3, 14:2, 10:3, 6:3, 2:1}
</code></pre>

Then we decide that if HAL wins(like in this example), they will update their
playbook to include these options and therefore be more likely to randomly pick
these 'winning' moves. If HAL had lost, they would take away one instance of these
moves (but always keeping at least [1,2,3]) to be less likely to pick 'losing'
moves. So HAL's updated playbook after winning looks like this:

<pre><code>
{19:[1, 2, 3, 3], 14:[1, 2, 2, 3], 10:[1, 2, 3, 3], 6:[1, 2, 3, 3], 2:[1, 1, 2]}
</code></pre>

The idea is that while HAL learns slowly, eventually they will learn all the best
moves. Although it may be more accurate to say that HAL gets much better at
randomly guessing the best move.

All in all, this was a pretty interesting project and while I found it difficult
at first to wrap my head around how to make this work, I ended up really enjoying
the project and feeling pretty good about it.

If you want to check out my code, it's on Github.

(https://github.com/andrewmpierce/game-of-sticks)
