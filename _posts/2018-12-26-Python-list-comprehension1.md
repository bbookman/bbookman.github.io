---
layout: post
title: 10 Python List Comprehension Practice Exercises That Will Make You A Hiring Manager's Dream
comments: true
social-share: true
tags:
- Tech
- Python
- List Comprehension
---
![python image](https://i.postimg.cc/8zFGpcLR/hitesh-choudhary-666995-unsplash.jpg)
# How can a python newbie can stand out in a sea of competition?  Show your list comprehension

As a Software Quality Assurance Engineer, I use python as one tool in my test automation tool chest.  List comprehension is one of the python techniques that not only adds flair to your code, it also saves cpu cycles and is considered 'Pythonic'.

## What is list comprehension?
The list comprehension syntax is somewhat of a compressed 'for' loop.

### Classic 'for' loop
Given a list of numbers, remove all odd numbers from the list:
```Python
numbers = [3,5,45,97,32,22,10,19,39,43]
result = []
for number in numbers:
  if number % 2 == 0:
    result.append(number)
print(result)
```

### The list comprehension way
```Python
result = [number for number in numbers if number % 2 == 0]
print(result)
```
So glorious, so pretty, so pythonic ;)

## List comprehension syntax
The trickiest part of learning list comprehension for me was really understanding the syntax.  The best method of explaining IMO is from [Tutorial – Python List Comprehension With Examples](https://www.analyticsvidhya.com/blog/2016/01/python-tutorial-list-comprehension-examples/)

A traditional for loop:
![for loop](https://i.postimg.cc/HLrqv6gg/forloop.png)

Translated to list comprehension:
![list comprehension visual](https://i.postimg.cc/TPn9Pbjb/listcomp.png)

And another great visual
![list comprehension visual aid](https://python-3-patterns-idioms-test.readthedocs.io/en/latest/_images/listComprehensions.gif)


## Examples
### Given a list of numbers, remove floats (numbers with decimals)
```python
original_list = [2,3.75,.04,59.354,6,7.7777,8,9]
only_ints = [number for number in original_list if type(number) == int]
print(only_ints)
```

## Practice
I needed practice, so I used this list.  Each challenge below links to a solution gist.

* [Find all of the numbers from 1-1000 that are divisible by 7](https://gist.github.com/bbookman/949b8fd32f432d4ee7feb1010fa82e47)
* [Find all of the numbers from 1-1000 that have a 3 in them](https://gist.github.com/bbookman/1a98da47a1a6d1ceffdd3bae7be36abe)
* [Count the number of spaces in a string](https://gist.github.com/bbookman/f0d36dfee6f6b3aa861fb026f1d5eb83)
* [Create a list of all the consonants in the string "Yellow Yaks like yelling and yawning and yesturday they yodled while eating yuky yams"](https://gist.github.com/bbookman/7d09a66ffdec60d5a55d167751f64175)
* [Get the index and the value as a tuple for items in the list "hi", 4, 8.99, 'apple', ('t,b','n').  Result would look like (index, value), (index, value)](https://gist.github.com/bbookman/1bd5d6ef798e1c56cd00db70e8661759)
* [Find the common numbers in two lists (without using a tuple or set) list_a = 1, 2, 3, 4, list_b = 2, 3, 4, 5](https://gist.github.com/bbookman/aca5b890a1f5ad64487594780301f82f)
* [Get only the numbers in a sentence like 'In 1984 there were 13 instances of a protest with over 1000 people attending'](https://gist.github.com/bbookman/ad4a1d6e9e9c752bf5ec899de0ca82dc)
* [Given numbers = range(20), produce a list containing the word 'even' if a number in the numbers is even, and the word 'odd' if the number is odd.  Result would look like 'odd','odd', 'even'](https://gist.github.com/bbookman/b75ae13049a0fc53aa6f27ddd8610f96)
* [Produce a list of tuples consisting of only the matching numbers in these lists list_a = 1, 2, 3,4,5,6,7,8,9, list_b = 2, 7, 1, 12.  Result would look like (4,4), (12,12)](https://gist.github.com/bbookman/de9cae671eb144d7011768999470242b)
* [Find all of the words in a string that are less than 4 letters](https://gist.github.com/bbookman/e5c6030a9e2624bbdb85e1e5e2efa37f)
* [Use a nested list comprehension to find all of the numbers from 1-1000 that are divisible by any single digit besides 1 (2-9)](https://gist.github.com/bbookman/c5cf0516e9fcf0c1fdbdcff7cd43867a)


# Contact Me

* [LinkedIn](http://linkedin.com/in/brucebookman)
* [GitHub](https://github.com/bbookman)
* [Twitter @brucebookman](https://twitter.com/brucebookman)
* [Blog](http://bbookman.github.io)
* [Medium](https://medium.com/adventures-in-ios-mobile-app-development)
* [Codementor.io](https://www.codementor.io/bbookman)
* [Indie Hacker](https://www.indiehackers.com/bbookman)
* [Dev.to](https://dev.to/bbookman)
* [Reddit](https://www.reddit.com/user/Bbookman)
* [Youtube](https://www.youtube.com/channel/UCERHLEbt6fipRMiPRR4u3SQ)
* [Quora](https://saganone.quora.com/)
