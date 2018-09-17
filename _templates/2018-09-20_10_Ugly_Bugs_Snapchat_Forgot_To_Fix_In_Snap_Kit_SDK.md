---
layout: post
title: 10 Ugly Bugs Snap Didn't Bother To Fix In Snap Kit And Lessons They Teach
comments: true
social-share: true
tags:
- Tech
- Snapchat
- Snap Kit
- Mobile Development
---

!!!!! Add "Written By Bruce Bookman" to image !!!!!!!

![](https://installornot.com/wp-content/uploads/Snapchat-Snap-Kit-1024x544.jpg)
## Snap has many bussiness problems, including the poor roll out of Snap Kit SDK.
The bugs described are purposefully written in "Bug Style" with the hope that each will actually get filed against Snap Kit SDK 

# Snapchat Snap Kit SDK Primer
I'm an iOS Hobbyist develper and have been working with Snap Kit now for many months.  With over 10 Medium posts, I have been chronicalling my struggles and victories.

Snap Kit is Snap's attempt to go beyond its primary app offering.  To grow and stay relevant, Snap log in must be as prevalent as Facebook, Twitter, or Google log in.  Plus Snap could become the GIFY of the AR world through integrating Bitmoji, Filters and Lenses into the 3rd party app echosystem.

Snap Kit SDK is Snap's attempt to become sticky.

Some of the bugs documented below are nit-picky, however Snap is in no position to allow even the slightest developer friction to occur.  Snap's future is partly riding on the success of Snap Kit, and the bussiness has very little wiggle room to get things wrong.  Winning over the developer community is paramount to Snap Kit SDK adoption.

Also some of these could be considered feature requests, documentation requests or things that are "not bugs".  As someone with 20 years of software industry experience, I say these are "Failures" that need to be addressed (aka Bugs).

![snapchat-2123517_1920.jpg](https://i.postimg.cc/vmG3vz0s/snapchat-2123517_1920.jpg)

# Bugs
## 1 - Single Point Of Support
### Steps To Reproduce
1. Go to https://docs.snapchat.com/docs/
2. Note the text

> Feedback?
We regularly update our documentation to give you everything you need for creative, easy integrations. If something’s not working for you, please report it to snapkit-support@snap.com.

3. Send an email to snapkit-support@snap.com as instructed in the text
4. Wait for an automated response and read it

### Result
Automated response text says:
>Hi there!" Learn more about Snap Kit by visiting support.snapchat.com/news/snapkit. If you have further questions please reach out to us at support.snapchat.com/i-need-help.  Thanks!

There are a few issues with the automated response:
* Tells the customer who is seeking customer support to look at the news blog.  The news blog is **not** designed as a customer support tool.
* Tells the customer if they need further assistance to go to "I need help".  Here again, this part of the Snapchat website is **not** designed to deliver developer nor customer facing support for Snap Kit.  A look at that URL will show that there is no way to report a specific Snap Kit SDK issue and the user will feel like anything they report there will end up in a black hole.
* The automated responsedoes not say that anyone will actually read the email the customer sent nor help.  It only talks about where to go and what to read.  It is far from customer friendly.

### Suggested Mitigation
Reword the automated response:
> Thank you for contacting Snap Kit Support.  This automated response is to let you know we received your request and will be reaching out to you shortly

![](https://i.postimg.cc/hjxdpjhr/call-center-1015274_1920.jpg)

## 2 - Add Snap Kit SDK Support Options To 'I Need Help'
### Steps To Reproduce
1. Go to http://support.snapchat.com/i-need-help

### Result
Note the available options:

**What can we help you with?**
* My account login
* Report a safety concern
* My Snapchat isn't working
* My Snapstreaks disappeared
* I have a Filter or Lens question
* I have a business concern
* I have a Spectacles question
* I have a Snap Store question
* I have feedback
* I have a privacy question

None of the above are remotely clear options for someone seeking Snap Kit SDK assistance

### Suggested Mitigation
Add an option for Snap Kit SDK Support

![](https://cdn-images-1.medium.com/max/2000/1*gCTL9i4szIqePqvcSfRr2g.png)

## 3 - Snapchat Support On Twitter Needs Redirect Option for SDK questions
### Steps to Reproduce
1. Go to https://twitter.com/snapchatsupport
2. Ask a Snap Kit question such as "Do we ask this account for help with Snap Kit?"

### Result
A number of problematic results occur.  However, the key is that the team delivering support through twitter is clearly not staffed to handle Snap Kit SDK questions.

The initial response after step 2 above was a bot with a link to https://kit.snapchat.com/.  Clearly not a helpful response to the question.

The next response also seemed canned and perhaps a bot
>We'll need to look further into this.  Head over to spr.ly/help and select the options that match your issue . . .

That URL leads to the I Need Help page and yields bug #2 above and is somewhat related to bug #1 as well.

### Suggested Mitigation
Modify the bots/automated response on Snapchat Support Twitter account such that it handles Snap Kit queries appropriately.

![](https://i.postimg.cc/sX92MZvt/error-102075_1920.jpg)

## 4 - Code Sample Error in Creative Kit Documentation
### Steps To Reproduce
1. Go to https://docs.snapchat.com/docs/creative-kit/
2. Scroll down to this
```swift
/ swift

/* Main image content to be used in the Snap */
let snapImage = /* Set your image here */
let photo = SCSDKSnapPhoto(image: snapImage)
let photoContent = SCSDKSnapPhotoContent(snapPhoto: photo)
```

### Result
This line is not correct
```swift
let photoContent = SCSDKSnapPhotoContent(snapPhoto: photo)
```
It should be 'SCSDKPhotoSnapContent' rather than 'CSDKSnapPhotoContent' (see also bug 5 below)


### Suggested Mitigation
Please correct the documentation.

Note there might be a larger issue with the SDK itself.  The naming is inconsistent - see bug 5

![](https://i.postimg.cc/8ztB6jrf/man-932840_1280.jpg)

## 5 - Naming Inconsistencies with Creative Kit
In Creative Kit there is a method with the name 'SCSDKSnapPhoto'

Carefully notice the pattern of the name.  The first word is **Snap** and second the word **Photo**

Creative Kit also has the method 'SCSDKPhotoSnapContent'

Notice the naming method is not consistent.  Above the word **Snap** comes before **Photo**, but in this case the word **Photo** comes before the word **Snap**

SCSDK **Snap** _Photo_
SCSDK _Photo_ **Snap** Content

This same issue is repeated with these pairs of methods from Creative Kit:
'SCSDKSnapVideo' and 'SCSDKVideoSnapContent'

Here in 'SCSDKSnapVideo' the word **Snap** comes before **Video**, however here 'SCSDKVideoSnapContent' the word **Video** comes before the word **Snap**

### Suggested Mitigation
1.  Scan all documentation and sample code for accuracy
2.  Consider renaming such that the pairs are consistent
3.  If executing 2, provide multiple paths for developers to learn about the change and conduct a comprehensive documentation review

![](https://i.postimg.cc/156yXq2M/atlas-green-1507-unsplash.jpg)
## 6 - Login Scopes Information Misplaced
### Steps To Reproduce
1. Go to https://docs.snapchat.com/docs/login-kit/

### Result
The entire section titled **Understanding Scopes** seems misplaced.  The section is the very first section for Login Kit.

Further the section provides code for iOS Info.plist **yet** this page is a generic page contains both iOS and Android instruction.  So starting the document off with strictly iOS information is odd at best.

### Suggested Mitigation
Move this text to the **Getting Started** section on this page.  Perhaps somewhere near the text describing Info.plist entries

![](https://i.postimg.cc/Z54zqDrK/nousnou-iwasaki-45718-unsplash.jpg)

## 7 - Embeded Binaries documentation can be replaced or augmented to include Cocoapod
### Steps To Reproduce
1. Go to https://docs.snapchat.com/docs/login-kit/
2. Inspect the Getting Started section

### Result
>In your app project in Xcode, add SCSDKCoreKit.framework and SCSDKLoginKit.framework into General - Embedded Binaries.

The above text is correct, yet incomplete.  Snap Kit now offers a Cocoapod install solution.
### Suggested Mitigation
Add information about how to use the Cocoapod option for installing Snap Kit

![](https://i.postimg.cc/KYjVkX4F/nathaniel-shuman-396960-unsplash.jpg)

## 8 - Snap Kit SDK naming
### Steps To Reproduce
1. Go to https://github.com/SnapKit/SnapKit or http://snapkit.io/

### Result
The name of this well established code line is SnapKit, which can cause confusion with Snap Kit.

### Suggested Mitigation
Although it is late, it is important to note this issue.  This code base has existed for at least 4 years and is fairly popular with iOS developers.  A google search prior to choosing the name of Snap Kit would have been wise.  Further, if Snap is not using an outside name search service, it would be helpful to consider doing that for future naming

![](https://i.postimg.cc/Y2z3Hnqx/chuttersnap-478260-unsplash.jpg)

# 9 - UI of Developer Portal Confusing
### Steps To Reproduce
1.  With a user id and password log in at http://kit.snapchat.com

### Result
![](https://github.com/bbookman/Snapchat-Snap-Kit-DIY-Docs/raw/master/images/devportal1.png)
This UI does not lend itself to a clear understanding that there are two distinct areas.  The above image explains the problem best.  It is not very clear that there are two sections here.  There is no line between them and the title _App Info_ on the right side does not clearly denote the left side as applying to production (rather than development on the right side).  

### Suggested Mitigation
At minimum, place a vertical line between the two areas _App Onfo_ and _Development App Info_.
Also, change the titles of the OAUTH2 CLIENT ID fields so that they read **PRODUCTION OAUTH2 CLIENT ID** and **DEVELOPMENT OAUTH2 CLIENT ID**

![](https://i.postimg.cc/4NMhkVt5/milkovi-344432-unsplash.jpg)
# 10 - Unlink Sessions Methods Do Not Include Potential Thrown Errors
1.  Go to https://docs.snapchat.com/docs/login-kit/
2.  Inspect the information on unlinking Sessions
```swift
SCSDKLoginClient.unlinkCurrentSessionWithCompletion { (success: Bool) in
  // do something
}
```

### Result
Neither of the two method throw errors
* SCSDKLoginClient.unlinkCurrentSessionWithCompletion
* SCSDKLoginClient.unlinkAllSessionsWithCompletion

### Suggested Mitigation
Include code to throw errors

## Bonus
* Add image for each bug
* Follow up email from "real" support is poorly templated
* VIDEO for each bug
* Supply example code for each Kit / All kits (see bitmoji on GitHub)

## A - Snap Kit Twitter Account Not Active Nor Informative
### Steps To Reproduce
1. Go to https://docs.snapchat.com/docs/
2. Note the text
>To stay up to date with our SDKs, see what’s new and follow @snapkit on Twitter.
3.  Review the tweets from @snapkit on Twitter

### Result
Although the twitter account @snapkit was established May 2018, and it is now September 2018, there are 4 total tweets.

### Suggested Mitigation
The marketing team or other team that owns this account needs to start produc ing and posting more content and the account should also post with information that reflects the "see what's new" statement in the documentation.

## B - API Reference For iOS First Paragraph Seems Out Of Date
1. Go to https://docs.snapchat.com/docs/api/ios/
2. Note the text
>This documentation assumes you already made contact with us

### Result
I think this text was written when Snap Kit was in beta or had a small and managed audience.  And, the text is confusing.  There are no instructions here about how someone makes contact.  

### Suggested Mitigation
Remove the sentence or, if contact is required, explain how and why


## C - Snap Kit Support Boilerplate Not Helpful
1.  Send a support request to snapkit-support@snap.com
2.  After the initial automated response documented in Bug 1 above and others, wait for and then read the "live human" support response

### Result
>Chuck (Snap Connect)
Hello there,
Thanks for reporting this! In order for us to debug this better, could you please provide the following information:
Username
Client ID
Specific URLs or assets used
Info.plist (if there’s no sensitive information)
Code sample if possible
Screen recording and or screenshots
IP address

### Suggested Mitigation
I have sent a number of different requests to support and have seen this boilerplate response from Chuck.  Since every SDK engagement is different, this text is not helpful.  In face, I had asked a specific question about the developer portal and then saw this text.  It made me feel that my support issue was not even read, and that the support tech did not bother to read or care about my issue.

Either modify the text for inclusiveness, or change SOP such that support reps no longer use the boilerplate (or use it with greater thought)

## D - Missing Example Code
### Steps To Reproduce
1. Go to https://github.com/Snap-Kit

### Result
* No code samples for Android
* One sample for iOs, but only covers Bitmoji

### Suggested Mitigation
Supply Example Code For All Kits and both iOS and Android

## Keywords and SEO
* [KeywordTool.io](https://keywordtool.io/)
* [Google Trends]{https://trends.google.com/trends/}
* [Moz Keyword Explorer](https://moz.com/explorer)
* [SpyFu](https://www.spyfu.com/) - good for competitive analysis also)
* [LSI Graph](http://lsigraph.com/)
* [SEMRush](https://www.semrush.com/)
* [KeywordFinder](https://kwfinder.com/)
* [nTopic Keyword Writer](http://www.ntopic.org/writer.php)
* [nTopic for Chrome](http://www.ntopic.org/tools.php#chrome)
* [Textalyser](http://textalyser.net/)
* [Tag Crowd](https://tagcrowd.com/)

# Publish With the Big Guns
* [freeCodeCamp](http://bit.ly/how-to-submit)
* [Top Publications](https://toppub.xyz/)

# Social Share

Insert Share Images and links.  [Links can be generated here](http://www.sharelinkgenerator.com/)

# Newsletter Subscribe
[Generate your own here](https://upscri.be/)

This style link works with Medium: https://upscri.be/99b881/

# Contact Me

* [LinkedIn](http://linkedin.com/in/brucebookman) * [Sagan.one](http://sagan.one)
* [Twitter @saganone1](https://twitter.com/saganone1)
* [Medium](https://medium.com/adventures-in-ios-mobile-app-development)
* [Codementor.io](https://www.codementor.io/bbookman)
* [Indie Hacker](https://www.indiehackers.com/bbookman)
* [Blog](http://bbookman.github.io)
* [Quora](https://saganone.quora.com/)
* [GitHub](https://github.com/bbookman)
* [Dev.to](https://dev.to/bbookman)
* [Reddit](https://www.reddit.com/user/Bbookman)
* [Youtube](https://www.youtube.com/channel/UCERHLEbt6fipRMiPRR4u3SQ)

# Read Next Banner

Add banner at bottom with "Read Next" or "Previous/Next" suggestion point to own content

# Old Points to New

Once posted, edit other posts with _“If you enjoyed this piece, you might also like…”_

# References (for this template)
* [How to get published in the freeCodeCamp Medium publication](https://medium.freecodecamp.org/how-to-get-published-in-the-freecodecamp-medium-publication-9b342a22400e)
* [How to Write Viral Headlines: New BuzzSumo Research](https://buzzsumo.com/blog/5-ways-create-amazing-viral-headlines/#gs.5AK_Nuo)
* [35 Actionable Tips to Grow Your Medium Blog](https://medium.com/swlh/35-actionable-tips-to-grow-your-medium-blog-4e4017b89905)
* [MoZ Canonicalization](https://moz.com/learn/seo/canonicalization)
* [Why These 21 Headlines Went Viral (and How You Can Copy Their Success)](https://optinmonster.com/why-these-21-headlines-went-viral-and-how-you-can-copy-their-success)
* [According to a Study, There’s a Good Chance You’ll Click This Headline Because It’s 97 Characters](https://contently.com/strategist/2017/11/09/study-longer-headline-better/)
* [Do’s & Don’ts of Re-publishing Content on Medium or LinkedIn](https://www.impactbnd.com/blog/dos-donts-of-re-publishing-content-on-medium-or-linkedin)
