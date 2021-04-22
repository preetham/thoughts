---
title: "Verify Tweet"
date: 2019-06-07
slug: "verify-tweet"
description: "Verify if a tweet is made by the said author using ML"
keywords: ["projects", "blog", "verify", "twitter", "verifytweet"]
draft: false
tags: ["projects", "comsci"]
math: false
toc: false
---

 Fake tweet images can be generated using a preset meme template from websites like: [TweetGen](https://www.tweetgen.com/), [Prank Me Not](http://www.prankmenot.com/?twitter_tweet) and [Simitator](http://simitator.com/generator/twitter/tweet) . Verification of such tweets takes a manual work to find the user, scroll through their timeline and maybe find the tweet.

A fake tweet screenshot looks very convincing, misleading the general public. For example:

| Fake        | Original           |
| ------------- |:-------------:|
|![Fake](https://i.imgur.com/NLClbbD.png "Fake")| ![Original](https://i.imgur.com/p95eAId.png "Original")|

Using a combination of image processing and Twitter API, verifytweet can successfully verify if a twitter user actually made the tweet.

## Limitation

Due to Twitter API search limitations in a free tier, maximum of 3 days old tweets can be searched in a single request.
