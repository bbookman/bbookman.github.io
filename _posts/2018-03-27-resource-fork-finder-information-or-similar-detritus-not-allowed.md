---
layout: post
show-avatar: true
comments: true
social-share: true
title: resource fork, Finder information, or similar detritus not allowed
date: 2018-03-27 00:00:00 +0000
tags:
- iOS
- Swift
- Common Errors
---
Now this one is **painful**.  It takes a lot of digging and false starts, but I believe the solution for most is super simple.

> resource fork, Finder information, or similar detritus not allowed

To fix this, at your project root directory, run the command

    xattr -cr "path to .app file

[Here's the longer StackOverflow story](https://stackoverflow.com/questions/39652867/code-sign-error-in-macos-high-sierra-xcode-resource-fork-finder-information?utm_medium=organic&utm_source=google_rich_qa&utm_campaign=google_rich_qa)