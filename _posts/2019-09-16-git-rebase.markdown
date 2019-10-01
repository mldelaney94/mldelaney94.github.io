---
layout: post
title: "Git"
date: 2019-09-16 
---

# Git's most basic concept

Git's commits are snapshots. A snapshot is to a repository as a screenshot is to a video. Each commit is a 'snapshot' containing the information necessary to apply or rollback the changes between snapshots.

# Repository's

So with that Git organises its snapshots via Repositories (repo's). You will typically work with one local repo and place your code onto a remote server to save it properly.

## Local

Your **local** repo consists of three **trees**: Working Directory, Index/Staging area and HEAD.

Working directory is where the files live. Index is what files from the working directory are being tracked. And HEAD is a pointer to a recording of the latest changes to these files.

**Git add** adds a change to the staging area, telling git you want to include that change in the next commit. **Git commit** records the changes from the last commit to this one. And **Git push** pushes that commit to the remote.

## Branches

We're gonna start off with the motivation for branches.

Lets say that you wanted to add a feature to your software, but it would take several weeks to make. What would you do to continue working on your software without changing its quality to an end user in the meantime?

You would make a copy. Then work on that copy until the feature was fully implemented and tested. And when you where done, you would overwrite the old code and make the copy the main source file.

There are multiple different ways to achieve this, and they have to address questions about development in parallel with other programmers and how to address reverting your changes.

This is the motivation behind branches. A way to do all that said above in a convenient, less risky way.

### How do they work?

Branches work by keeping a list of the codes savestates (commits). If you remember from before, each commit contains the information necessary to rollback the changes to the last commit. This is tracked through a pointer called the HEAD. When a branch is created, a new HEAD is created pointing to the commit you branched from (likely to be the latest commit to the master branch in many scenarios). As commits are added to the branch, the HEAD is updated to point to the latest commit. 

Remember that the commits themselves contain all the necessary information to actually revert changes or apply changes. As such, making a new branch should be relatively cheap, as you are not actually having to copy any files or anything like that.

### Merging Branches

So when you create a new branch, your first 'commit' for that branch is the commit you branched from in the original branch.  This becomes your common ancestor between the two branches.

Merging basically takes the information from the last common ancestor between the two branches and blends it all together to create a new commit to the branch being merged to.

It does this (often) by doing a three way merge. So it compares your code to the common ancestor, and the code from the other branches latest commit to the common ancestor, to determine if you both edited the same line. If you haven't, it should add all the changes at once and create a new commit for the HEAD of that branch to point to. If you have, then you will get a MERGE conflict which needs to be resolved.

Fast forward merging occurs when there are no changes from anyone else to the branch you're merging into. As such, its HEAD points to a direct ancestor in your branch. Therefore all you have to do is update the HEAD to point to the HEAD of the branch you're merging, as if you'd added all those commits to it itself.

### Rebasing

There is one **Git merge** variant worth discussing called **Git rebase**. Rebasing basically changes the 'last common ancestor' between two branches. For instance if you've been working off the master branch for a while and the master branch has been changed, you can rebase to the latest commit on the master branch so that your eventual merge will be smoother.

#### Why rebase?

It just allows for a cleaner Git history. The Git history will show far fewer commits. So as such it will be easier to go back through the commits if you are looking for where a bug was introduced.

# Remotes

A remote is just a separate place from your local repo that hosts a version of the project that you're working on. Origin (the original place you cloned from or the first remote you added to the project) is the most common one.

# Websites I collated info from:

Basically a bibliography:

atlassian.com/Git/tutorials/using-branches/Git-merge
https://medium.com/@talgoldfus/better-understanding-Gits-work-flow-in-order-to-properly-deal-with-merge-conflicts-part-i-760a366fc997
http://onlywei.Github.io/explain-Git-with-d3/#commit
https://developer.ibm.com/tutorials/d-learn-workings-Git/
https://Git-scm.com/book/en/v2/Git-Branching-Rebasing
https://git-scm.com/book/en/v2/Git-Basics-Working-with-Remotes
