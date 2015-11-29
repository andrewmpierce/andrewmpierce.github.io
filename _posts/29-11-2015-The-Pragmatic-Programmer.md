---
layout: post
published: True
title: The Pragmatic Programmer
comments: True
---
Over the week of Thanksgiving, I read The Pragmatic Programmer. I've heard it recommended
over and over again and decided I would take the plunge. I'm very glad I did. It
was a really good experience for me, after spending three months furiously coding, to
spend a few days just _reading_ about best practices and letting some of the concepts
sink in. I learned an incredible amount from reading The Pragmatic Programmer, but I'll just highlight three of my biggest take homes.

1) No broken windows

According to TPP, one of the definitive signs of a decaying neighborhood is a broken
window. Literally one broken window that goes unfixed instills a sense of neglect,
and the neighborhood starts to decline. In code, there are a lot of parallels. I remember
many times I would write code and think "This is okay." or "It does what I want it to." but not being totally happy with it's conciseness or the flow of my code. Then when I continued to build on that code, what started as a small problem or even just a less ideal solution, quickly became a bigger and bigger pain to deal with and usually required the original code being rewritten anyway.

2) Testing is more cultural than technical

Testing is important. Obviously. Unfortunately, a solid test suite is one of the first things many developers leave out in a serious time crunch. However, as I and many other people experience, six hours later when I'm hunting down an error in my code, I really wish I had written tests as I went. It's important to think of testing as a cultural commitment to your code base. I want my code to _work_. When my code has a problem, I want to be able to identify it as soon as possible so I can fix it as soon as possible. Even if my test suite isn't the model of perfection, having it and incorporating tests into every piece of code you write is vital and will pay dividends in the long run. If I make testing a priority in my code, 1) my code will be better than it was before even with an okay test suite but 2) I will get better at writing tests over time.

3) Java and Concurrent Processing

So this one is a little different. The principles of concurrent processing are not
covered in detail in TPP. However, it is mentioned and it's not a topic that I was introduced to in either The Iron Yard or the one Java course I took in college. Apparently Java and languages that run on the JVM (Clojure, Scala, Groovy, etc...) support concurrency (having several processes going on) and parallelism (executing several processes at once), from the ground up and that is what accounts for the speed and ability of these languages to handle massive applications.

To be more accurate, apparently concurrency is _possible_ in other languages if you manually manage threads, but parallelism is not. In any case, the concurrency seems to be not as ideally suited because these languages were not written with that in mind.

The idea here is not that TPP taught me these things, I did a fair amount of research and bugging more experienced developers about these concepts, but it did _expose_ me to them and led me on a furious google spree. I was never really interested in Java or JVM based languages before, but understanding the basics of concurrency definitely has piqued my interest in the process.

The Pragmatic Programmer was one of the best things I've done for my personal growth as a developer. It's done a very good job of convincing me to really think about every line of code I write. Programming should not be mechanical, we should be continually attempting to put out the best code possible and ruthlessly testing it to make it sure it continues to be the best code we could have written. I'm also excited to reread it in another year or so. While I definitely learned a lot reading it, I feel very confident that I will glean much more from it in another year with more experience under my belt.
