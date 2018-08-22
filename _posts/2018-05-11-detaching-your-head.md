---
layout: post
show-avatar: true
comments: true
social-share: true
title: Detaching your head
date: 2018-05-11 00:00:00 +0000
tags:
- Xcode
- iOS
- Git
- Common Errors
---
Xcode is a joy and a curse.  And the git integration sometimes goes wonky.  About every month I get a detached head.  [Here's a great fix](https://ilikekillnerds.com/2014/05/how-to-fix-a-detached-head-on-a-git-repository/) that I'll add one more small teak to..

* **Step 1.** Create a branch called “temp” by typing: git branch temp
* **Step 2.** Switch over to your new branch by checking it out: git checkout temp
* **Step 3.** Point the master pointer to the temp branch pointer (the-f means force): git branch -f master temp . _//here 'master' would be any branch that has a head that you want to realign_
* **Step 4.** Check out master _(or whatever the problem branch was)_
* **Step 5.** Now we delete our temp branch: git branch -d temp
* **Step 6.** Push our new changes to the remote repository: git push origin master _//or whatever the problematic branch was_