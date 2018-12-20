---
layout: post
title: One fun blogpost on how to use python virtual environments that will save you a lot of googling
comments: true
social-share: true
tags:
- Tech
- virtualenv
- Python
- programming
---
![python book](https://i.postimg.cc/26vkvWPb/python-achievement-adult-book-1181671.jpg)
![written by bruce bookman](https://cdn-images-1.medium.com/max/880/0*-xvbtrI9d5aRFYR4.png)

# Python virtual environments
I'm good at forgetting syntax.  And when working in Python, and creating virtual environments - I can never seem to remember the key steps.

And it seems that when I look things up, for some reason I have to put 3 different resources together to be successful.

# Python 2
## Check if it is already installed
Check to see if virtualenv is already installed
```
virtualenv --version
```
The result, if installed, will be a version number such as 16.1.0

## Check for pip install
Before installing virtualenv, make sure you have pip (which comes standard with most modern releases of Python).
```
pip --version
```
The result,if installed, will be a version number such as 'pip 18.1'

Don't have pip? [Follow these instructions](https://pip.pypa.io/en/stable/installing/)

## If virtualenv is not installed, use pip to install
```
sudo pip install virtualenv
```
## Set up directories
I like to have all my virtual environments under a main directory.  I suggest creating a directory named 'python_virtual_environments'

```
mkdir python_virtual_environments
```
## Which version of python
Many development environments will come standard with at least one version of Python, usually many versions.  

Get a list of Python versions with this command
```
ls /usr/bin | grep python*
```
## Create virtual environment
To create a virtual environment, you need to choose a version.

The syntax is:
```
virtualenv -p /usr/bin/python## my_virtual_env_directory
```

So if you wanted to create a virtual environment for a project named 'scooby_duby_app', and needed Python 3, this would be the command set

```
cd my_virtual_env_directory
virtualenv -p /usr/bin/python3 scooby_duby_app
```

This will create a directory ''/my_virtual_env_directory/scooby_duby_app'

Lastly, activate the virtual environment
```
cd scooby_duby_app
source bin/activate
```

# Python 3
Python 3 comes with venv, which works like virtualenv for Python 2.

## Create virtual environment
```
python3 -m venv <name_of_virtual_environment>
```

# Contact Me

* [LinkedIn](http://linkedin.com/in/brucebookman)
* [GitHub](https://github.com/bbookman)
* [Medium](https://medium.com/adventures-in-ios-mobile-app-development)
* [Blog](http://bbookman.github.io)
* [Codementor.io](https://www.codementor.io/bbookman)
* [Indie Hacker](https://www.indiehackers.com/bbookman)
* [Dev.to](https://dev.to/bbookman)
* [Reddit](https://www.reddit.com/user/Bbookman)
* [Youtube](https://www.youtube.com/channel/UCERHLEbt6fipRMiPRR4u3SQ)

# More good reads
If you enjoyed this piece, you might also like:
* [16 Ugly Bugs Snap Didn’t Bother To Fix For Snap Kit And Lessons They Teach](https://bbookman.github.io/2018-16Bugs/)
* [Detaching your head](https://bbookman.github.io/detaching-your-head/)
* [Swift int division is special](https://bbookman.github.io/swift-int-division-is-special/)
