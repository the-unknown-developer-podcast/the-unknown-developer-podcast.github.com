---
layout: post
title: "a chatbot of yourself"
date: "2019-05-12 00:22:25"
author: brunojensen
header-img: img/post-bg-06.jpg
---
Funny history, I was working for this company in Brazil and we were using a xmpp protocol based application as internal communicator and in that time I was very curious about chatbots and I was doing some tests with IBM Watson, was more a study than a actual project for the company.

So, yeah, sometimes I get bored and to put my mind to work I’ve started with the xmpp integration. Pretty simple, I’m java developer and there’s a java library for almost everything. Cool, next step... watson which was also easy as they provide a java library to integrate with the server.

I didn’t want to waste too much time, so I did a simple configuration in the NLP, everytime somebody asking me for help, the application will respond with a different way to say that I was busy. Isn’t really helpful when you’re focused in something else?

The problem was when I wired the application into the xmpp server, turns out that I didn’t know that the xmpp listener was called even when the other user joined the server without send me any message. :D

So, after one week I discovered that I was sending non-sense messages continuously to my co-workers. :D
Well my POC didn’t have any unit or integration test, so... Yeah, be careful before send something to production, I’ve learned my lesson.

[https://github.com/brunojensen/xmpp-chatbot](https://github.com/brunojensen/xmpp-chatbot)

[Comments here](https://github.com/brunojensen/brunojensen.github.com/issues)
