---
layout: post
show-avatar: true
comments: true
social-share: true
title: Invalid element name in Main.storyboard
date: 2018-04-02 00:00:00 +0000
tags:
- iOS
- Swift
- Common Errors
- Storyboard
---
I recently decided to revert a merge because a feature needed to be replaced.  After carefully working through some conflicts, I brought up my branch post-revert and saw this interesting compile issue

> Line 584: StartTag: invalid element name

The compiler told me this issue was in Main.storyboard.

[Here is the fix](https://medium.com/@mzygar/resolving-storyboard-merge-conflicts-94eae558acb8)