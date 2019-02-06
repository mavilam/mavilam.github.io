---
layout: post
title:  "What to read bot (II)"
date:   2019-02-05 22:43:48 +0100
categories: bot
---
More than a year ago I posted my first article about <span style=" font-weight: bold">[my book "recommender" bot (@What_to_read_bot)](http://telegram.me/what_to_read_bot)</span> 🤖 . In this article I'm going to explain the changes and the process form the point of view of the development and the user.

First of all, the code is open source now ✨✨ !! This is the <span style=" font-weight: bold">[link of the GitHub Repository](https://github.com/mavilam/what_to_read_bot)</span> if you want to check it.

## Interface and new functionality

There has been a few changes in the functionality that are also reflected in the interface. In the begining there was two sources from where the books info was obtained, Amazon and La casa del libro. Now Amazon was removed, because of its web did not let me scrap the book info and Fnac and Libreria La central was added.

The choices were so limited in the early version, this made me think about some kind of categories to choose in each source. All sources have several categories, after a short look I selected six categories identified as the mainly read. Obviously the interface had to change. In the current version, the selection of a type of book has two steps. First the category has to be chosen.

<center><img src="/img/botpost2categories.jpeg" title="What to read bot" alt="What to read bot interface" width="50%"></center>
<p/>

Then the three sources are displayed and the user can pick one of the or pick three in a row. If you want to go back and select another category just press the back button.

<center><img src="/img/botpost2sources.jpeg" title="What to read bot" alt="What to read bot interface" width="50%"></center>
<p/>

And the answer should look like this one:

<center><img src="/img/botpost2result.jpeg" title="What to read bot" alt="What to read bot interface" width="50%"></center>
<p/>

## Technical process

I'm going to try to shortly explain the interesting changes.

When I thought about of adding new sources I tried to avoid the same problem that I had to face with the web of Amazon. For this purpose I scrap now with some headers in the http GET request, for cheating the web trying to looks like a browser instead of a bot or a script. This headers looks like this:

```js
{'User-Agent': 'Mozilla/5.0 (Macintosh; Intel Mac OS X 10.14; rv:65.0) Gecko/20100101 Firefox/65.0'}
```

On the other hand the manual deployment could cause operational risk that can be avoided using a continuous integration development, so I added Travis CI for automatic deployment, running the tests (that should be more than what I made to be honest 😂) before deploying and more tasks that can be configurable. Travis provides you a free plan if the project is open source.

The bot is deployed in a free tier of Heroku, and lately that was a thing disturbing me, all months the free hours were used but the traffic was very low. Checking the logs could find the problem, the telegram api was doing a long polling every tiny time period from a queue to get the messages. To resolve this issue I checked the webhook method instead of the polling one. This method consists in register a web service endpoint to be called each time that a message is received in the telegram chat. This cause a lower traffic in the server.

Conclusion step by step my little bot is getting in shape 😀
