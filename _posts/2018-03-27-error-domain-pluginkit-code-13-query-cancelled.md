---
layout: post
show-avatar: true
comments: true
social-share: true
title: Error Domain=PlugInKit Code=13 "query cancelled
date: 2018-03-27 00:00:00 +0000
tags:
- iOS
- Swift
- Common Errors
---
So subtle yet so vexing.

> **Error Domain=PlugInKit Code=13 "query cancelled**

To fix this, I changed one tiny piece of code, [but there are a number of related issues to check](https://forums.developer.apple.com/thread/82105)

**Original**

        func imagePickerController(_ picker: UIImagePickerController, didFinishPickingMediaWithInfo info: [String : Any]) {
            let chosenImage = info[UIImagePickerControllerOriginalImage] as! UIImage
            userChosenPhotoFromGalleryOrCamera.image = chosenImage
            self.dismiss(animated: true, completion: nil)
    
            userChosenPhotoFromGalleryOrCamera.isHidden = false
        }

Get rid of **self**.dismiss and replace with **picker**.dismiss

**New**

        func imagePickerController(_ picker: UIImagePickerController, didFinishPickingMediaWithInfo info: [String : Any]) {
            let chosenImage = info[UIImagePickerControllerOriginalImage] as! UIImage
            userChosenPhotoFromGalleryOrCamera.image = chosenImage
            picker.dismiss(animated: true, completion: nil)
    
            userChosenPhotoFromGalleryOrCamera.isHidden = false
        }.