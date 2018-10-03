---
layout: post
title: Snapchat Snap Kit for Android Sinks Into Quicksand
comments: true
social-share: true
tags:
- Tech
- Android
- Snapchat
- Snap Kit
---
![](https://cdn-images-1.medium.com/max/880/0*-xvbtrI9d5aRFYR4.png)
![](https://i.postimg.cc/W4VM8X0q/snapdroid.png)
# Now, for the Android Saga
I have been writing about [Snapchat's Snap Kit SDK for iOS](https://medium.com/adventures-in-ios-mobile-app-development).  It's delivery to market has been anything but a shining example of solid business process.  Here, I will take a look at the Android documentation, technical support, SDK and more to see if the same is true.

# Bug style
I'll be writing critique in "bug style" with steps to reproduce.  I'm doing this with the hope that Snap files each of these as bugs.

Note, I am calling these bugs.  You might not.  I argue that a failure is a failure and a failure is a bug.

Documentation issues are bugs.  Support delivery failures are bugs.  A bug, in my view, is something that has gone wrong and must be tracked and fixed/mitigated.

# To badly go where documentation has gone before
The iOS documentation is less than stellar, and falls particularly flat for Login Kit.  Android's is no better.

# Scopes array format is not clear
## Steps to reproduce
1. Go to https://docs.snapchat.com/docs/login-kit/#android
2. Note the text and code below

>Finally, add your application’s client ID, redirect URL, and scopes to the appropriate meta-data tags in your application’s AndroidManifest.xml. The SDK automatically fetches these values to enable deeplinking from your app to Snapchat. For a list of available scopes, please see the Understanding Scopes section of this document
```xml
<uses-permission android:name="android.permission.INTERNET" />

<application ...>
   <meta-data android:name="com.snapchat.kit.sdk.clientId" android:value="your app’s client id" />
   <meta-data android:name="com.snapchat.kit.sdk.redirectUrl" android:value="the url that will handle login completion" />
   <meta-data android:name="com.snapchat.kit.sdk.scopes" android:resource="@array/snap_connect_scopes" /> <!-- This should be a string array of scopes !-->
```
### Result
It is not at all clear what the syntax / formatting should be for the string array of scopes.

The documentation does give some information

>Login Kit offers the following scopes:

>https://auth.snapchat.com/oauth2/api/user.display_name: Grants access to the user's Snapchat display name
>https://auth.snapchat.com/oauth2/api/user.bitmoji.avatar: Grants access to the user's Bitmoji avatar; toggleable by user

However, this does not help.  It does not make clear the exact text one would use to define the array.

Should the array look like this?

```xml
<meta-data android:name="com.snapchat.kit.sdk.scopes" android:resource="@array/https://auth.snapchat.com/oauth2/api/user.display_name,https://auth.snapchat.com/oauth2/api/user.bitmoji.avatar " />
```

Should it look like this?

```xml
<meta-data android:name="com.snapchat.kit.sdk.scopes" android:resource="@array/user.bitmoji.avatar, user.display_name"
```

### Suggested mitigation
Use the examples in the results section above as a guide and re-write the documentation so that it is crystal clear the exact format / syntax to use.

### Business lesson
Documentation must be treated as part of the product.  It is as much code as any computer code.  It must be tested by professionals.  Release of documentation should follow the same iteration path as software, because documentation is software.

Put the documentation through a number of review cycles.  Get a diversity of eyes on it.  Have people use the documentation just like the end customer would.

Customers use documentation because they have an end goal.  Pick your use cases as end goals and then use the documentation to try to meet those end goals.  This approach will improve clarity, reduce typos, catch technical errors, and improve documentation flow and readability.

# Newsletter

https://upscri.be/99b881/

# Contact Me

* [LinkedIn](http://linkedin.com/in/brucebookman)
* [Sagan.one](http://sagan.one)
* [GitHub](https://github.com/bbookman)
* [Twitter @saganone1](https://twitter.com/saganone1)
* [Medium](https://medium.com/adventures-in-ios-mobile-app-development)
* [Blog](http://bbookman.github.io)
* [Codementor.io](https://www.codementor.io/bbookman)
* [Indie Hacker](https://www.indiehackers.com/bbookman)
* [Dev.to](https://dev.to/bbookman)
* [Reddit](https://www.reddit.com/user/Bbookman)
* [Youtube](https://www.youtube.com/channel/UCERHLEbt6fipRMiPRR4u3SQ)
* [Quora](https://saganone.quora.com/)


# If you liked this you may also like

* [16 Ugly Bugs Snap Didn’t Bother To Fix For Snap Kit And Lessons They Teach](https://medium.com/adventures-in-ios-mobile-app-development/16-ugly-bugs-snap-didnt-bother-to-fix-for-snap-kit-and-lessons-they-teach-4dd6c1aa567)
* [Snapchat Snap Kit SDK Tutorial for iOS Swift](https://medium.com/adventures-in-ios-mobile-app-development/snapchat-snap-kit-sdk-tutorial-for-ios-swift-311863074bab)
* [he Customer Development Life Cycle](https://medium.com/adventures-in-ios-mobile-app-development/the-customer-development-lifecycle-2dec7ac59c30)
