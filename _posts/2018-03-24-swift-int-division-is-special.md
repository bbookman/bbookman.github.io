---
layout: post
show-avatar: true
comments: true
social-share: true
title: Swift Int Division is special
date: 2018-03-24 00:00:00 +0000
tags:
- iOS
- Swift
- Int Division
- Math
---
Every print statement below yields 0.0

    var c:Double = 0.0
    let a:Int = 1
    let b:Int = 5
    print("a/b = \(Double(a/b * 100))")
    c = Double(a/b * 100)
    print("c = \(c)")

[Here's the fix](https://stackoverflow.com/a/48696698/5721803)
