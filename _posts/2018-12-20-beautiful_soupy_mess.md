---
layout: post
title: One painful search for answers resolved for installing BeautifulSoup
comments: true
social-share: true
tags:
- Tech
- Python
- Beautiful Soup
- Error
---
![](https://cdn-images-1.medium.com/max/880/0*-xvbtrI9d5aRFYR4.png)
![](https://i.postimg.cc/VL8gKtF0/bowl-chopsticks-cooking-674576.jpg)

# The interwebs is full of 'answers' for this error
```
print "Unit tests have failed!"

   SyntaxError: Missing parentheses in call to 'print'. Did you mean print("Unit tests have failed!")?

   ----------------------------------------
Command "python setup.py egg_info" failed with error code 1 in /tmp/pip-install-r9yaqi1s/beautifulsoup/
```

Do a search and you will find the vast majority of solutions involve updating pip, or upgrading setuptools, or python-dev.

You might try one of these - **none of these worked for me**
```
pip install --upgrade pip
pip install --upgrade setuptools
apt-get install python3.6-dev libmysqlclient-dev
easy_install -U setuptools
```
# Worked for me
```
pip3 install BeautifulSoup4
```

# Contact Me

* [LinkedIn](http://linkedin.com/in/brucebookman) * [Sagan.one](http://sagan.one)
* [GitHub](https://github.com/bbookman)
* [Twitter @saganone1](https://twitter.com/saganone1)
* Mastodon: @brucebookman@mastodon.technology
* [Medium](https://medium.com/adventures-in-ios-mobile-app-development)
* [Blog](http://bbookman.github.io)
* [Codementor.io](https://www.codementor.io/bbookman)
* [Indie Hacker](https://www.indiehackers.com/bbookman)
* [Dev.to](https://dev.to/bbookman)
* [Reddit](https://www.reddit.com/user/Bbookman)
* [Youtube](https://www.youtube.com/channel/UCERHLEbt6fipRMiPRR4u3SQ)
* [Quora](https://saganone.quora.com/)


# Read Next Banner

Add banner at bottom with "Read Next" or "Previous/Next" suggestion point to own content

# Old Points to New

Once posted, edit other posts with _“If you enjoyed this piece, you might also like…”_
