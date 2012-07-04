---
layout: blog
title: MVC is not dead and MOVE is too much
category: blog
tags: ['MVC']
image: /images/blog/mvc-is-not-dead.jpg
summery: "I've seen a blog post on Hacker News prompting as MVC is dead and it's time to MOVE. <br>I was curious at first to look at it and but once I read it I realized it is just a extended version of MVC. And it is too much. <br>This post is a innocent attempt to urge MVC is not dead"
---

![MVC is not dead](/images/blog/mvc-is-not-dead.jpg)

I've seen a blog post on Hacker News prompting as [MVC is dead and it's time to MOVE](http://cirw.in/blog/time-to-move-on). I was curious at first to look at it and but once I read it I realized it is just a extended version of MVC and it is too much. This post is a innocent attempt to urge MVC is not dead.

## Bit about MOVE
Before starting to answer it would be better to have a word on MOVE. Simply its an extension to MVC where you code in

* **M**odel - DB activities
* **O**peration - Does some core logics in the your app
* **V**iew - All the UI logics
* **E**vent - does routing and handling page requests

## Here is my answer
In this I wrote my answer based on [Codeigniter](http://codeigniter.com) (MVC framework for PHP) to make some of my points. But it can be applied with any MVC or HMVC framework available. All of these are my personal thoughts and I might be wrong :)

### Event is just a URL Router
You don't need special Event class because Controller already does it with the help of URL Router. 

### Operation can be handle in the Model
In these days people use ORM and Database abstraction libraries. So we can simply use model to code our logics too. So there is no need of Operation class to specially handle logics. 

### We don't need to confuse people
We can extends thing as many as we can. We can extend MOVE too. But what really matter is ease of use. If it is simple many will accept it. MVC is simple and many use it.

### We use libraries
We don't code each and every thing we need. We tend to use libraries. Still there is a problem with MOVE as where to use libraries. So use it suits where. Inside a controller, model or view.


## Use MVC with a discipline

People like flexibility. So It is upto you or your team to use MVC as you like. The essence here is use it with a discipline. Here is my discipline. 

* Model - Does all my logics (DB + Business Logic)
* View - Does all my UI
* Controller - Just glue Model and View to a URL request.

Hope I did a good job on proving "MVC is not dead" :)

[Continue the discussion on Hacker News](http://news.ycombinator.com/item?id=4197938)







