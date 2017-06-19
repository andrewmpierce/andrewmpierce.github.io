---
title: "Git Jr. - How Do I Fix Merge Conflicts?"
layout: post
date: 2017-06-15 09:01
image: /assets/images/markdown.jpg
headerImage: false
tag:
- Git
- Technical
- How to
category: blog
author: andrewpierce
description: A basic example of how to fix merge conflicts in Git
# jemoji: '<img class="emoji" title=":ramen:" alt=":ramen:" src="https://assets.github.com/images/icons/emoji/unicode/1f35c.png" height="20" width="20" align="absmiddle">'
---

If you read my [most recent post on Git branches](http://andrewmpierce.io/Git-Branches/), you'll remember that I mentioned the idea that sometimes when you're merging two branches together, Git can't quite figure out what should and shouldn't be there. When this happens, you'll get the (unnecessary) dread of many developers, the aforementioned merge conflict.

It will look something like this:
![An image showing a merge conflict in the terminal](../assets/images/fixing-merge-conflicts/merge-conflict.png "A Git Merge Conflict")

So first let's talk about why we get merge conflicts. Merge conflicts generally happen when the branch you created your feature off of has changed since you made the branch. Git is surprisingly good at figuring out most things when this kind of stuff happens, but generally if there's an edit to the same line, Git will throw a merge conflict so that you have to manually go in and specify what that line of code should look like.

You'll really only see merge conflicts when you're collaborating with other people and they're working in the same functions and files as you. It's very rare to get into a scenario where you have merge conflicts if you're the only person working in that particular repo.

Let's walk through a scenario that would cause a merge conflict, and then see how to resolve it.

Here is our starting project:

![An image showing a Hello World Javascript function](../assets/images/fixing-merge-conflicts/original_project.png "Original Project")

In this scenario, your boss asks you to add a comment to this function. We want future developers to know whats going on in this function, and you happily oblige. You create a branch called 'adding-comment' and merrily go about your way. When you finish, your code looks like this.
![An image showing a Hello World Javascript function with added comment](../assets/images/fixing-merge-conflicts/added_comment.png "Added comment to original project")

Unbeknownst to you, your boss also asked another developer to change that console.log to a console.info. The other developer made their change and merged it in. What that means is that now master is different from when you originally made your branch.

Anyway, you don't know this yet, so you go to merge your branch in to master and you get this:
![An image showing a merge conflict in the terminal](../assets/images/fixing-merge-conflicts/merge-conflict.png "A Git Merge Conflict")

Well, crap. What do we do now?

Have no fear, merge conflicts really aren't too crazy to deal with. Git is even nice enough to tell us exactly what file the merge conflict is in. We only have one file we're working with in this particular instance, but Git still tells us the issue is in hello.js.

Anyway, we go to checkout hello.js and we see this:
![An image showing a merge conflict in the editor](../assets/images/fixing-merge-conflicts/merge-conflict-code-info.png "A Git Merge Conflict")

Git is pretty clear about where the issue is. It adds these <<<<<<<< and ======== characters to show us exactly what its confused about.

Git shows us both the version of the code thats in the branch we're merging into (master in our case) and the feature branch that we are working with (adding comment). Git uses the word HEAD to describe the branch we are merging into, shows the relevant code, then splits the two versions with a row of ============. Finally it denotes the branch that the second version of code comes from, adding-comment in this case.

Okay, so how do we fix this?

Basically Git just needs us to make a commit with the version of code that we want to exist in the master branch that we are merging into. Git isn't sure what we want and doesn't want to decide for us.

Bear in mind that we shouldn't commit the <<<<<< or ====== characters that Git adds. It will make our code fail to compile, which is exactly why Git adds it.

Anyway, so we know what we need to do in order to fix the conflict, but what should the code actually look like? Nobody told you that they wanted the console.log changed to a console.info. This is the really critical part of merging conflicts, making sure that the code you commit is actually the code that should be there.

So how do figure this out? The easiest way is to talk to the person who made the code change thats giving you grief. You can do this one of two ways:

1) Yell across your office or Slack room "Who changed my console.log to a console.info?!?!?!?!?!?".

2) Utilize the Git log to see the commit that changed the code, and get context for the full code change they did and then message them directly.

I recommend option 2.

The easiest way to see all the commits for a branch are to run the command 'git log'. We could also use something like git blame to find what we need, but to keep things as straightforward as possible, we'll use git log for now. Git log will provide you a nice log of all the commits. If we run it now we get this output:

![An image showing the git log](../assets/images/fixing-merge-conflicts/git-log.png "git log")

A minor note about git log before we move on, it will open the log into a vi window. Vi is an editor that you'll probably do at least small tasks in at various points in your career. It doesn't behave like Atom or Sublime though, and your mouse won't work to click around in the window and move the cursor.

For the purposes of interacting the git log, you don't need to know much besides that entering in ':q' will exit the window, the j key will move the cursor down, and the k key will move the cursor up. There's a LOT more you can do with vi, as it's a lot of people's main editor, but for our purposes you can get by with only knowing that much. It's good to remember that Git will often open vi windows, and the same rules applies.

Now that we've been over a tiny bit of vi, let's move on. There are two commits here. The first initialized the project with the Hello World console.log, this would have been where the project was when you came in and were asked to add a comment. Notice that all of these commits are dated and show the commit author, which is frequently helpful. You can also see the commit message that the developer added. This is where being in the habit of writing helpful and relevant commit messages comes in really handy as well.

The commit thats causing the problem seems to be something that this Andrew Pierce guy put in on Friday, June 16th. The commit message even mentions console.info, so this seems right. We can look at the whole commit by using the command 'git show 750cedd9a3c7170d42775f373926025072d9e986'.

![An image showing the usage of git show](../assets/images/fixing-merge-conflicts/git-show-terminal.png "git show")

You may be asking yourself what that string of letters and numbers came from. Without getting too deeply into it, it's called a SHA1 and is a [unique identifier](https://www.theregister.co.uk/2017/02/23/google_first_sha1_collision/) for each commit. We can use this to signal to Git that we want to access something about that particular commit.

The command git show will just show us the commit. It will again open in a Vi window and look like this:

![An image showing a git commit](../assets/images/fixing-merge-conflicts/git-show.png "git show")

Awesome. This definitely confirms that this commit is doing something weird, and we can see that our other developer hasn't changed anything else.

Okay so at this point you talk to this Andrew guy and sync up about what the function is supposed to actually look like. Turns out, your boss wants it to be a console.info line with a comment. Thats no problem though, we just go in and delete the extra characters that Git added and make our code look like how everyone agreed it should actually look.
![An image showing the final code version](../assets/images/fixing-merge-conflicts/final-code.png "The final code version")

So you make your code look like this, and then commit your code like you've done before. You will always need to make a new commit after fixing a merge conflict.
![An image showing the final commit to finish our merge](../assets/images/fixing-merge-conflicts/final-commit-terminal.png "Final Commit")

After that, the merge is complete! You can push to whatever you need to and consider this task done.

If you have other burning questions about merge issues, feel free to reach out to me on Twitter or with a comment here. I'd love to talk to you about it.
