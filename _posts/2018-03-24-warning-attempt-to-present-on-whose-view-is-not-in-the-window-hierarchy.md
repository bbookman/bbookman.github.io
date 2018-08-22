---
layout: post
show-avatar: true
comments: true
social-share: true
title: 'Warning: Attempt to present <*> on <*> whose view is not in the window hierarchy'
date: 2018-03-24 00:00:00 +0000
tags:
- iOS
- Swift
- Odd Warning
---
It is only a warning, but I like not to have warnings.  And this one just got me curious so I wanted to fix it.

The bottom line issue is that you have a view controller that did not finish loading and another view controller is presenting.  

The fix that worked for me was to present the secondary view controller here..

    override func viewDidAppear(_ animated: Bool) {
    self.present(authViewController, animated: true, completion: nil)
        }
