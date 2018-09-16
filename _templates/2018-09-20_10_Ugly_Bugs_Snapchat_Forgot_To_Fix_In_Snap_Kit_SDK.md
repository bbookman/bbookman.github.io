---
layout: post
title: 10 Ugly Bugs Snapchat Didn't Bother To Fix In Snap Kit SDK And The Bussiness Lessons They Teach
comments: true
social-share: true
tags:
- Tech
- Snapchat
- Snap Kit
- Mobile Development
---
![](https://installornot.com/wp-content/uploads/Snapchat-Snap-Kit-1024x544.jpg)
## Snap has many bussiness problems, including the poor roll out of Snap Kit SDK.
The bugs described are purposefully written in "Bug Style" with the hope that Snap Kit support will file these through modified copy/paste

# Snapchat Snap Kit SDK Primer
I'm an iOS Hobbyist develper and have been working with Snap Kit now for many months.  With over 10 Medium posts, I have been chronicalling my struggles and victories.

Snap Kit is Snap's attempt to go beyond its primary app offering.  To grow and stay relevant, Snap log in must be as prevalent as Facebook, Twitter, or Google log in.  Plus Snap could become the GIFY of the AR world through integrating Bitmoji, Filters and Lenses into the 3rd party app echosystem.

Snap Kit SDK is Snap's attempt to become sticky.

Some of the bugs documented below are nit-picky, however Snap is in no position to allow even the slightest developer friction to occur.  Snap's future is partly riding on the success of Snap Kit, and the bussiness has very little wiggle room to get things wrong.  Winning over the developer community is paramount to Snap Kit SDK adoption.

Also some of these could be considered feature requests, documentation requests or things that are "not bugs".  As someone with 20 years of software industry experience, I say these are "Failures" that need to be addressed (aka Bugs).

![](https://pixabay.com/photo-2123517/)

# Bugs
## 1 - Single Point Of Support
### Steps To Reproduce
1. Go to https://docs.snapchat.com/docs/
2. Note the text
> Feedback?
> We regularly update our documentation to give you everything you need for creative, easy integrations. If something’s not working for you, please report it to snapkit-support@snap.com."
3. Send an email to snapkit-support@snap.com as instructed in the text
4. Wait for an autorespnse and read it
### Result
Autorespnse text says:
>Hi there!" Learn more about Snap Kit by visiting support.snapchat.com/news/snapkit. If you have further questions please reach out to us at support.snapchat.com/i-need-help.  Thanks!

There are a few issues with the autorespnse:
* Tells the customer who is seeking customer support to look at the news blog.  The news blog is **not** designed as a customer support tool.
* Tells the customer if they need further assistance to go to "I need help".  Here again, this part of the Snapchat website is **not** designed to deliver developer nor customer facing support for Snap Kit.  A look at that URL will show that there is no way to report a specific Snap Kit SDK issue and the user will feel like anything they report there will end up in a black hole.
* The autorespnse does not say that anyone will actually read the email the customer sent nor help.  It only talks about where to go and what to read.  It is far from customer friendly.

### Suggested Mitigation
Reword the autorespnse:
> Thank you for contacting Snap Kit Support.  This autorespnse is to let you know we recieved your request and will be reaching out to you shortly

## 2 - Add Snap Kit SDK Support Options To I Need help
### Steps To Reproduce
1. Go to support.snapchat.com/i-need-help

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
Modify the bots/autorespnse on Snapchat Support Twitter account such that it handles Snap Kit queries appropriately.

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
It should not be Snap Photo Content...  it should be 'SCSDKPhotoSnapContent'
See SCSDKPhotoSnapContent.h

### Suggested Mitigation
Please correct the documentation.

Note there might be a larger issue with the SDK itself.  The naming is inconsistent - see bug 5

## 5 Naming Inconsistencies with Creative Kit
In Creative Kit there is a method with the name 'SCSDKSnapPhoto'

Carefully notice the pattern of the name.  The first word is **Snap** and second the word **Photo**

Creative Kit also has this method
'SCSDKPhotoSnapContent'

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

## 6 - Login Scopes Information Misplaced
### Steps To Reproduce
1. Go to https://docs.snapchat.com/docs/login-kit/

### Result
The entire section titled **Understanding Scopes** seems misplaced.  The section is the very first section for Login Kit.

Further the section provides code for iOS Info.plist **yet** this page is a generic page contains both iOS and Android instruction.  So starting the document off with strictly iOS information is odd at best.

### Suggested Mitigation
Move this text to the **Getting Started** section on this page.  Perhaps somewhere near the text describing Info.plist entries


## 7 - Embeded Binaries Info is Out of date
>In your app project in Xcode, add SCSDKCoreKit.framework and SCSDKLoginKit.framework into General - Embedded Binaries.

## Bonus

* Thank you for contacting us
* Portal badly designed
* Follow up email from "real" support is poorly templated
* VIDEO for each bug

## Bonus A -
1. Go to https://docs.snapchat.com/docs/
2. Note the text
>To stay up to date with our SDKs, see what’s new and follow @snapkit on Twitter.
3.  Review the tweets from @snapkit on Twitter

### Result
Although the twitter account @snapkit was established May 2018, and it is now September 2018, there are 4 total tweets.

### Suggested Mitigation
The marketing team or other team that owns this account needs to start producting and posting more content and the account should also post with information that reflects the "see what's new" statement in the documentation.

# Links
* Should look natural and inline (within sentences and not stand alone)
* Make sure to Canonicalize your original articles
```
<link rel="canonical" href="LINK TO ORIGINAL" />
```

Honest text for affiliate links

_This story contains some affiliate links. If you click through and decide to make a purchase, I will receive a small commission at no extra cost to you_

# Abbreviations
Don’t use an abbreviation unless the abbreviation is more widely understood than what it stands for

# Sentences
Err on the side of breaking long sentences and paragraphs down into shorter ones.
Use SEO keywords throughout your prose

# Stats to Shoot For
* Average Reading time of 8 minutes
* Medium = Average Word Count of 2075 | Google/SEO 1,140-1,285
* LinkedIn = Flesch-Kincaid readability score 80-89 (See tools below)

# Image(s)
Start considering images early in the writing process. And never publish without at least one image. Otherwise your story will be all but invisible in news feeds. You should break up long stories with images. Blog articles with images get 94% more views

* Big
* Beautiful
* High Resolution
* Popular posts have six images

## Image Resources
* [Royalty and Attribution Free at Unsplash](https://unsplash.com/)
* [Royalty and Attribution Free at Pexels](https://www.pexels.com/)
* [Humor at Somecards](https://www.someecards.com/)
* Google : Labeled for Reuse

Create image links (to your desired destination).  Click on an image in the editor and press Ctrl+K or ⌘+K to insert your link

[Consider editing the photo and adding your branding](https://medium.com/swlh/35-actionable-tips-to-grow-your-medium-blog-4e4017b89905)

# Post Timing
* LinkedIn: Thursday

# Post Distribution
* Syndicating is a great way to expand the reach of your content, however, when you’re re-posting content on LinkedIn and Medium, don’t give the readers the entire article -- especially if your goal is to drive referral traffic.
* [Postable quotes](http://getpikiz.com/)

# Tools

## Summary of Tools
* [Handpicked Blogging Tools](https://bloghands.com/tools)

## Content / Topic Ideas
* [Buzz Sumo](https://buzzsumo.com/)
* [Market Muse](https://www.marketmuse.com/)
* [Answer the Public](https://answerthepublic.com/)
* [Blog Topic Generator](https://www.hubspot.com/blog-topic-generator)
* [SEMRush](https://www.semrush.com/topic-research/), first two free


## Headline
* [CoSchedule Headline Analyzer](https://coschedule.com/headline-analyzer)
* [ShareThrough Headline Analyzer](https://headlines.sharethrough.com/)
* [Emotional Marketing Headline Analyzer](http://www.aminstitute.com/headline/
* [Headline Capitalization](https://headlinecapitalization.com/

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

## Other
* [Word Counter](http://wordcounter.net/)
* [Hemingway App](http://www.hemingwayapp.com/) makes your writing bold and clear
* [Import to Medium](https://medium.com/p/import)
* [Get reading level using Microsoft Word)(https://mk0blogacton3ngqa7ix.kinstacdn.com/wp-content/uploads/2018/03/3-21-18-1.png)
* [EpicBeat](https://epicenter.epictions.com/epicbeat/explore/)

# Where to Get Data
* [U.S. Census](https://www.census.gov/)
* [Statistica](https://www.statista.com/)
* [Pew Research](http://www.pewresearch.org/)
* [Google Scholar](https://scholar.google.com/)


# Tags

Many publishing sites limit to 5 tags. The most popular Medium ones are #tech, #life-lessons, #travel, #design, and #startup

# References (for this template)
* [How to get published in the freeCodeCamp Medium publication](https://medium.freecodecamp.org/how-to-get-published-in-the-freecodecamp-medium-publication-9b342a22400e)
* [How to Write Viral Headlines: New BuzzSumo Research](https://buzzsumo.com/blog/5-ways-create-amazing-viral-headlines/#gs.5AK_Nuo)
* [Analyzing Medium’s posts and building a simple prediction service for “Popular on Medium”](https://medium.com/polar-tropics/analyzing-mediums-posts-and-building-a-simple-prediction-service-for-popular-on-medium-d28615947ff4)
* [The Ultimate List of Marketing Statistics for 2018](https://www.hubspot.com/marketing-statistics)
* [5 Characteristics Of High Converting Headlines](https://conversionxl.com/blog/5-characteristics-high-converting-headlines/)
* [We Analyzed 100 Million Headlines. Here’s What We Learned](https://buzzsumo.com/blog/most-shared-headlines-study)
* [Your Blog Posts Need More Statistics: Why And How To Get Them](https://www.forbes.com/sites/jaysondemers/2018/05/10/your-blog-posts-need-more-statistics-why-and-how-to-get-them/#2dee6357355b)
* [10 LinkedIn Publishing Tips: We Analyzed 3000 LinkedIn Blog Posts](https://okdork.com/linkedin-publishing-success/)

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
