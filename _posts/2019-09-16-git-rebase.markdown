---
layout: post
title: "Git"
date: 2019-09-16 
---

#Git's most basic concept

Git's commits are snapshots. A snapshot is to a repository as screenshot is to a video. Git knows how to apply the changes to the code such as to add the snapshot on or roll it back.

#Repository's

##Local

Your local repo consists of three "trees": Working Directory, Index and HEAD.

Your working directory contains the actual files that you're working on. Your index is where the changes to the working directory are stored. HEAD points to the last commit you've made.

###Analogy

Git is a photo manipulator. It wants a way to track changes it makes to its various photos. Git ADD adds a photo to be tracked. Git COMMIT saves the changes made to the local copy (specifically by tracking delta's between commits), and git push uploads and applies the COMMIT history to the server Git stores the photo's on.

##Branches

So now git wants to be able to make changes to its photos. But imagine that it had a website where it would display those photos. It wouldn't want for every experimental change made to be immediately uploaded, and it still wants to store the changes as it makes them.

So it would probably create a new folder a store the changed photo's there, and after it was happy with them it would put them into the master folder for display.

Imagine as well that maybe another photographer wants to join the team. He would have to get his own folder separate from the master folder to do his work. This would be the same as a branch.

#Snapshot as of now

These websites are what I'm at atm:

atlassian.com/git/tutorials/using-branches/git-merge
https://medium.com/@talgoldfus/better-understanding-gits-work-flow-in-order-to-properly-deal-with-merge-conflicts-part-i-760a366fc997
http://onlywei.github.io/explain-git-with-d3/#commit
https://developer.ibm.com/tutorials/d-learn-workings-git/
https://git-scm.com/book/en/v2/Git-Branching-Rebasing
