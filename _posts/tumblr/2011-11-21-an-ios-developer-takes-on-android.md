--- 
title: An iOS Developer Takes on Android
tags: 
layout: post
---
[nfarina](http://nfarina.com/post/8239634061/ios-to-android):

> ![](http://cl.ly/34182G3F1r1L2r0K1M0N/Untitled-1.png)

>

> Recently, we released the [Android
version](https://market.android.com/details?id=meridian.app) of
[Meridian](http://www.meridianapps.com), our platform for building location-
based apps.

>

> We didn’t use one of these “Cross Platform!” tools like
[Titanium](http://www.appcelerator.com). We wrote it, from scratch, in Java,
like you do in Android.

>

> We decided it was important to keep the native stuff native, and to respect
each platform’s conventions as much as possible. Some conventions are easy to
follow, like putting our tabs on the top. Other conventions go deep into the
Android Way, like handling `Intents`, closing old `Activities`, implementing
Search Providers, and being strict about references to help the garbage
collector.

>

> Now, our platform leverages HTML5 (buzzword, sorry) in many places for
branding and content display, so we got a fair amount of UI for free. But
there was much platform code written in Objective-C that needed translation
into Java, such as map navigation, directions, and location switching.

>

> So, we rolled up our sleeves, downloaded the Android SDK, and got to work.

>

> [Read More](http://nfarina.com/post/8239634061/ios-to-android)
