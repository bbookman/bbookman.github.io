---
layout: post
title: Unloved Cancel Button
date: 2018-03-21 00:00:00 +0000
show-avatar: true
comments: true
social-share: true
tags:
- iOS
- Swift
- FirebaseAuthUI
- ViewController
---
I decided to use FirebaseAuthUI for my app and ran into something that could be helpful for others.  If you go this route, you will end up with a `ViewController` that has a `Cancel` button where you don't want one.  Since this is Google's code, it is next to impossible to track down where this button is coming from.  However, there is a [fix](https://stackoverflow.com/questions/43411117/firebaseui-ios-remove-cancel-button)

`extension FUIAuthBaseViewController{
  open override func viewWillAppear(_ animated: Bool) {
    self.navigationItem.leftBarButtonItem = nil
  }
}`
