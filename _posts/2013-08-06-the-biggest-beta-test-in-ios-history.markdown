---
layout: post
title: "The Biggest Beta Test in iOS History"
date: 2013-08-06 01:20
comments: false
category: blog
author: riley
tag:
- GBA4iOS
- developer
- personal
---

I created my Twitter account in February 2009. By June 6 of this year, I had amassed a grand total of 268 followers. Exactly two months later, here are my new Twitter stats:

![Follower Count](/assets/images/posts/Follower_Count.png)

While I've enjoyed watching my follower count grow tremendously, I've been having trouble keeping up with the ever increasing number of people asking about GBA4iOS. It's become clear that I need a more centralized place where I can provide information and support for those who need it, which is why this website was born. Eventually, this will be where I'll post on a great range of topics primarily dealing with iOS Development, but for now I plan on using it to post updates on my progress with GBA4iOS 2.0. As such, this first post will focus primarily on the backstory of GBA4iOS, and will be longer than what I'll typically write. If you're just interested in the future of GBA4iOS, feel free to skip to the end of this post, but in doing so you'll miss some important information that may answer your questions.

Shall we begin? I think so!
<!-- more -->

First of all, I need to correct a common misconception. I did not write the underlying emulation system that powers GBA4iOS; it is in fact a semi-modified version of the code found in gpSPhone 1.8, a version of exophase's gpSP ported to iOS by [Zodttd](http://twitter.com/zodttd). Upon finding the source on Github (which has since been taken down), I immediately cloned it to my computer and began tinkering with it. My first attempt to compile it resulted in 999+ errors, so I knew I had some work to do. After a month of trial and error, I finally got it to compile, and after building a quickly hacked-together UI I released [the very first version of GBA4iOS](https://github.com/rileytestut/GBA4iOS/commit/82fc08f3b58b9ffe961ca5e51ae7ab279d0d18e4).

Due to the nature of the App Store, there was absolutely no chance I could submit it for review, so by open sourcing it I hoped other developers would be able to download it and play it for themselves. Unfortunately, it's rather hard to get your work noticed when you're essentially a nobody developer, so GBA4iOS lived a rather uneventful life for the first half-a-year-or-so of its existence. I still continued to update it, but mostly for my friends who I could simply give it to in person (we're all rather into Pokemon, but then again who isn't?).

The first time GBA4iOS got any real exposure was this past January. [Steve Streza](http://twitter.com/stevestreza), former iOS developer at Pocket and avid brony, [tweeted about Gearboy, a fantastic new Xcode-buildable Game Boy emulator](https://twitter.com/SteveStreza/status/293149532643024897). Seeing this as my chance to gain some visibility, [I tweeted back with a link to GBA4iOS](https://twitter.com/rileytestut/statuses/293267381789274112). I put my phone down for a little while, and when I finally picked it up again I was astounded to see I had [been bombarded with notifications](/assets/images/posts/Steve_Streza.png), and a follow by Steve Streza himself. After this, GBA4iOS became just bit more well known, and I was content with that. A decent number of people were playing with the app I had written, and that alone gave me the motivation to keep working on it.

Despite this brief bit of exposure, most people who had heard about it were not developers themselves, so they had no way to install it short of asking a developer friend to do it for them. Hell, I even gave away some of my 100 device slots one day to my followers so they could join in the fun. It was unfortunate that so many people would be unable to download the app, but I had no intentions of submitting to the Cydia store because Zodttd's own gpSPhone continued to be sold there, and it had seen many updates since the 1.8 codebase I was using. (In fact, for the gpSPhone 8.0 update zodttd and I collaborated in order to update the UI and give it a style more akin to GBA4iOS. Check it out in the Cydia store if you're jailbroken!). However, when a new service known as [MacBuildServer](http://try.macbuildserver.com) was created, it immediately piqued my interest. A system that could allow side-loading of apps on non-jailbroken devices? This was exactly what I was looking for! Needless to say, it wasn't long before I updated GBA4iOS with support for the service, and this is what I consider the beginning of GBA4iOS' rise in popularity.

Lots of people don't understand how this was possible, so I'm going to take a brief moment and explain the magic that was happening behind the scenes. Apple provides three ways for apps to be distributed to users:

- App Store: Generally the most important way, this is how developers get their apps into the hands of their customers, and hopefully manage to make a profit in doing so. To get into the store, however, the app must go through the infamous Apple App Store review process. This prevents malicious apps from ever entering the store, but also prevents apps such as GBA4iOS from entering as well.
- Ad Hoc (Beta Testing): Every developer is allowed to install their apps on up to 100 devices. This allows developers to send pre-release versions of their apps to designated testers, thus allowing them to get feedback and bug reports before submitting to the App Store. Every time a device slot is used, however, it cannot be reclaimed until the developer's annual membership is up, which is why developers tend to be conservative over who gets these slots.
- Enterprise Distribution: Probably the least well known of the three, but by far the most open (at least on a technical level). Because many companies have far more than 100 employees, if they want to have all or most of their own employees test their apps, they would be unable to do so. To compensate for this, Apple allows large companies to enroll in the Enterprise Program, which grants them the ability to install any number of apps on any number of devices, without having to register each one.

As you can probably guess, MacBuildServer was using the Enterprise Distribution method to allow installation on non-jailbroken devices. Because GBA4iOS was open-sourced on Github, MacBuildServer was able to download a copy of the code to its servers, compile it into an app, and then distribute it under their own Enterprise Certificate. As long as this certificate was valid, any user could download GBA4iOS to their device, and most importantly it was *super* easy to use. A GBA emulator that could be installed hassle-free on any iOS device? It was unheard of, so it wasn't long before news of this began to spread.

[Tweets](https://twitter.com/search?q=GBA4iOS&src=typd). [YouTube videos](http://www.youtube.com/results?search_query=GBA4iOS&oq=GBA4iOS&gs_l=youtube.3..35i39j0l9.182.1429.0.1610.6.6.0.0.0.0.205.685.1j4j1.6.0...0.0...1ac.1.11.youtube.ShFrjrqI8AY). [Reddit posts](http://www.reddit.com/r/iosgaming/comments/1g6wze/working_gba_emulator_just_download_from_site_no/). I watched day by day as more and more people learned about GBA4iOS, all the while not truly believing it. What had started as a small project to share with my friends and other developers was now getting more exposure than I ever thought possible. I knew MacBuildServer could easily be shut down, but while GBA4iOS had certainly gained noticeable popularity, it was far from known by Apple.

That is, until [this happened](http://readwrite.com/2013/07/16/super-mario-zips-through-a-loophole-in-apples-app-restrictions). [Nick Statt](https://twitter.com/nickstatt), reporter at CNET and former editorial assistant at ReadWrite, wrote an article for the latter over GBA4iOS, and gave an excellent overview of the technology behind it (but more importantly, called the situation as a whole "the biggest beta test in iOS history", which I liked so much I used it as the title of this blog post). This one article paved the way for *massive* exposure. Soon, other well-known publications such as [TUAW](http://www.tuaw.com/2013/07/16/how-a-game-boy-emulator-app-snuck-past-apple-restrictions/), [Gizmodo UK](http://www.gizmodo.co.uk/2013/07/heres-a-gameboy-emulator-your-can-download-on-any-iphone-without-jailbreaking/), [GamePolitics](http://gamepolitics.com/2013/07/18/gba4ios-uses-programming-loophole-emulate-gba-games-ios-devices#.UgC73RZdX8t) (and subsequently [GoNintendo](http://www.gonintendo.com/?mode=viewstory&id=207834)), and [iMore](http://www.imore.com/how-gameboy-emulator-finding-its-way-non-jailbroken-devices) began to post 
about GBA4iOS, and it was this sudden surge in popularity that finally put it on Apple's radar. 

That very day, Apple did what it could to stop this: they revoked MacBuildSever's enterprise certificate. While it initially seemed that this meant no more downloads of GBA4iOS, it has since been discovered that setting an iOS' device date to before July 16 (the day Apple revoked the certificate) allows users to download the app again, and after the download they are free to set the date back to the current date. Unfortunately, this is far from a permanent solution, as once in a while iOS checks to see whether the certificate is valid, and if it finds it isn't, GBA4iOS will no longer open, forcing the user to set their device's date back again.

These are rather big inconveniences, but there's an even bigger one: while it may be possible to install GBA4iOS with the expired certificate, it is impossible to sign any new apps with it. Put simply, this means I can't release any future versions of GBA4iOS using MacBuildServer's certificate.

**The Future of GBA4iOS**

I've said this before, and I'll say it again: GBA4iOS is not dead. In fact, it's far from it. 2.0 is coming, and it's a complete rewrite of the app; not a single line of code was reused. It also no longer uses gpSPhone as the emulation core, allowing me to fix many of the issues plaguing previous versions (such as audio skipping), as well as much better ROM compatibility (looking at you Mystery Dungeon). While I'm not revealing a full feature list just yet, I will say I've been listening *very* closely. Plus, if you just can't wait to see what's in 2.0, I've been known to reveal new features in pre-release screenshots via [my Twitter account](http://twitter.com/rileytestut).

But how am I going to release it now that MacBuildSever is dead? For now, that's a secret. But I can say it definitely will not require a jailbreak, and it will *not* exploit a security bug in iOS (as jailbreaks tend to do). It will be as simple as tapping a button on your iOS device and installing, just as before.

So to sum up, GBA4iOS has traveled a long road to get to where it is now, but it has far from reached the end of its journey. I can't give a definite timeframe for the 2.0 release, but I can assure you all it'll be worth the wait. 

In the meantime, I hope you enjoy playing your Pokemons and Marios on the current version of GBA4iOS.
