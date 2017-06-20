---
title: "Git Jr. - How Do I Use Git Branches?"
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
description: A basic example of how to use git branches
# jemoji: '<img class="emoji" title=":ramen:" alt=":ramen:" src="https://assets.github.com/images/icons/emoji/unicode/1f35c.png" height="20" width="20" align="absmiddle">'
---

Git is one of my favorite development tools. Version control is so important, and once
you get the hang of it, it will make your development life way easier. One of the key
features of Git is the idea of branches. What is a branch? How do I switch branches?
What is all of this?


The whole point of branches is to give developers the ability to work on new features or fix old features
without the risk of breaking the existing 'main' code. Basically you have an existing branch called master,
if you never touch anything or create a branch and are in a git controlled repository, you are on the 'master' branch. You can always check what branch you are on by using the command 'git branch'. You can also use the command 'git status' and it will show your current branch, but won't show all the existing branches in your project.

![An image showing the command git branch](../assets/images/git_branches/git-branch.png "The Git Branch command")

As you can see in the image above, there are two branches in the directory I'm currently in. There's a  master branch and a 'theme-redo' branch. I'm currently working on the master branch, so its highlighted in green with a star next to it. You can always check what branches you have and what branch you're currently working on by using the 'git branch' command.

Let's work through a small example to show how you might use a git branch.

Here is a small Javascript project:
![An image showing the first Hello World project](../assets/images/git_branches/hello_world1.png "Example Hello World")

If we do the command git init (to make this a git controlled project) and then try the command git branch again, we see this:

![An image showing the first git branch command](../assets/images/git_branches/hello_world_branch1.png "Hello World git branch")

We don't get anything back! That's because as of right now, we haven't created any new branches. There's just the master original branch that is our default.

If we run the 'git status' command I mentioned earlier, we can verify that we are indeed on the master branch:

![An image showing the first git status command](../assets/images/git_branches/git_status.png "Hello World git status")

So let's say that we want to work on a new feature on our mini project. Let's add a feature that shows the current date along with Hello World. Maybe I'm worried that as I'm working on my existing functional product, I'll break something. People make all kinds of mistakes, and it would be nice to know that as I'm playing with this new feature, I'm not in danger of breaking what I already have.

This is where branches come in. I can create a new branch that will be an exact copy of the master branch. Then I can do whatever I want with my newly created branch, without impacting my master branch. So if anything breaks as I'm working on this new feature, it's only broken on my new branch.

Here's an example:
I can create a new branch with the command git checkout -b, and then the name I want the branch to be. So for this example I would do 'git checkout -b add-date'. Git checkout is the command used to switch branches, and adding the -b flag means that I want to create a NEW branch and switch to it.

![An image showing the new git branch](../assets/images/git_branches/new_branch.png "First Git branch")

So now I'm on my new add-date branch and I can go ahead and add the date feature to it.
![An image showing the new Hello World date feature](../assets/images/git_branches/added_date.png "Added date to Hello World")

Awesome! We have our basic Hello World function, and it will now show the datetime as well. I've also added and committed the code so that git 'saves' the changes.

We've done all this on the add-date branch, so if we switch back to the master branch with the command 'git checkout master', it will show the branch as it was when we left it. Like this:
![An image showing checking out master](../assets/images/git_branches/git-checkout-master.png "Git Checkout Master")

Now we are on the master branch again. If we take a look at our code on the master branch, it looks like this:
![An image showing the first Hello World project](../assets/images/git_branches/hello_world1.png "Example Hello World")

Notice that we don't see our Date feature. That feature doesn't exist on the master branch yet. We created the add-date branch and then added the feature.

Okay so all of that is awesome, we can make any change we want on a different branch without being too worried about messing anything up on master. Remember, master is the branch that we generally have deployed, aka it's the branch that our users are usually seeing. We really want to make sure that its always working. If I had made some error that would make my code not compile while working on the date feature, my master branch wouldn't be affected. When I finish the date feature, I can test my code and make sure I'm happy with it. Then I can merge it into the master branch, and all my users can use my awesome new feature.

So let's talk a little about merging before we finish up. Branches are all well and good, and a really fundamental aspect of Git, but without the ability to take the code we've been working on in a feature branch and put it into the master branch, it doesn't do us a lot of good. That's where merging comes in.

Merging just means that git will take all the changes from one branch and apply them to another. Git is usually pretty good at figuring out what stuff you've added or edited and will apply the changes.

The way that you merge code is with the 'git merge' command. Make sure you are on the branch that you want changes merged INTO. So if I was on the master branch, and ran the command 'git merge add-date', it would apply the changes from add-date into master. The add-date branch would NOT be affected by this, only the master branch.

So it would look like this in your terminal:
![An image showing the merge command for add-date](../assets/images/git_branches/git-merge-add-date.png "git merge add-date")

Then if we look at the code on our master branch, it will look like this:
![An image showing the newly merged Date feature](../assets/images/git_branches/added_date.png "Added date to Hello World - merged")

It looks exactly like our old add-date branch! Sweet! We could then go through whatever process we wanted to deploy the updated master branch and let our users use this new feature.

Git branches are a really great way to keep your master branch working smoothly, while allowing you to break as many things as you need to in the development process in order to ultimately fix or add something new. As long as anything you break is on your feature branch (add-date in this case), it won't affect master unless you consciously merge it.

This was a pretty straightforward example with a pretty simple merge process, but every now and again you'll get a merge conflict, which just means that Git can't figure out how these two files are intended to merged together. [I'll save that discussion for my next post.](http://andrewmpierce.io/fixing-merge-conflicts/)

I hope this post was helpful for anyone using Git branches for the first time or trying to get a handle on why you might want to use them, if something doesn't make sense here, please let me know. Leave a comment or hit me up on Twitter. I'd love to help you out.




Note:
You may have noticed I have my terminal tricked out to show the current git branch I'm on. This isn't a default so don't worry if you don't see this on your machine, thats okay. [Here is a link to a pretty easy guide if you're interested.](https://martinfitzpatrick.name/article/add-git-branch-name-to-terminal-prompt-mac/)
