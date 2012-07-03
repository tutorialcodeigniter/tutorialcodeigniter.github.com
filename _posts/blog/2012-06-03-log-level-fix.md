---
layout: blog
title: Log level fix for Codeigniter
category: blog
tags: ['codeigniter']
image: /images/blog/log-level-fix.jpg
summery: "Codeigniter's log levels are defined in the wrong order. Here's how we can fix It."
---

When writing quality applications, logging is one of the most important thing we need to look for. Just like every other framework Codeigniter has the logging facility and it works fine.

But the order of log levels defined in codeigniter is wrong. Here is the default log levels in codeigniter.

1. ERROR
2. DEBUG
3. INFO
4. ALL

## What is wrong here?
INFO level need to have more severity than DEBUG. And the order needs to be revised as follows

1. ERROR
2. **INFO**
3. **DEBUG**
4. ALL

Most of the popular log frameworks follow above standard and here is the [Log4j Wiki about it's Log Level.](http://en.wikipedia.org/wiki/Log4j#Log_level)

## Why is this wrong?

Someone might argue what is the problem here and argue that we treat it seperately. But the problem is not that. 

* Internally codeigniter does nearly **~10 DEBUG** logs for a simple page request. 
* And inside my controllers I do DEBUG and INFO logs seperately
* Normally we don't need DEBUG logs in the production and just only need INFO logs
* But the because of this strange log level order we can't just only filter out INFO logs

## The Fix - Core

I've worked on this and sent a [pull request](https://github.com/EllisLab/CodeIgniter/pull/1522) to [Codeigniter Github](https://github.com/EllisLab/CodeIgniter) repository and It is waiting for the approval. 

Hope it will be added in the future versions of codeigniter

## The Fix - Extending CI

I simply can't just wait for the core fix approve for this and I extend the CI Log library and fix this. Here is the steps how it can be fixed

* [Download this file](https://raw.github.com/arunoda/codeigniter-logfix/master/application/libraries/MY_Log.php)
* Save this file into your `application/libraries` folder
* With `MY_Log.php` ( If you've changed **Subclass Prefix** to something else, use it instead `MY_` )

Okay, this is my thoughts on this and If you've found this is interesting please find my [pull request](https://github.com/EllisLab/CodeIgniter/pull/1522) and express your opinion.





