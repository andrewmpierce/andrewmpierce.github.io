---
layout: post
published: true
---
#The Process of Learning What I Thought I Understood

I had an interesting experience the other day. I was working on an assignment that
as part of the rules, did not allow me to use any kind of loop. We had gone over
list and dictionary comprehensions and it seemed like a clear assignment to work
on these elegant new structures. I thought I had them figured out! Really they
didn't seem too complicated, just a restructured version of a loop to fit on one
line of code versus 3+ lines.

Ah, I was wrong. Close, but no cigar. My code still blew up all the same and it
literally took me hours to figure out a single line of code. Otherwise I had finished
the assignment. Let me show you the loop and the comprehension I was trying to
replace it with.

<pre><code>
  for arg in args
    if len(arg) != length:
      raise ShapeException


  [raise ShapeException for arg in args if len(arg) != length]
</code></pre>

The loop works! If the length of this arg does not equal the length I want it to
be, it raises an exception. Imagine my distress when the comprehension that I
thought would be interchangeable, doesn't actually work!

The reason it doesn't work, the reason that took me far more time than I care to
admit, is that a comprehension != a restructured loop. Programmers better than I
was at the time of my distress will realize the error easily. The first part of
a comprehension is a 'collection' and I was essentially trying to do a call to action
to raise an exception error. The code I ended up actually using looks like this:

<pre><code>
valid_args = [arg for arg in args if len(arg) == length]
    if len(valid_args) != len(args):
        raise ShapeException
</code></pre>

In this piece of code, I'm working with a comprehension in a more correct way.
This first step is adding the arg in the sequence of args to a string called
valid_args, it's 'collecting' it. Then I can do a simple if statement and raise
the same exception if the lengths of all the args and the valid_args doesn't match.

It was a very frustrating way to learn how comprehensions actually work, but I have
to say, I think I get it now.
