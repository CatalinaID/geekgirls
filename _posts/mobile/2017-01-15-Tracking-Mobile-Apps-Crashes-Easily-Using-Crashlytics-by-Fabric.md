---
layout: post
title: "Tracking Mobile Apps Crashes Easily Using Crashlytics by Fabric"
author: alifa
description: "Just sleep geeks, Crashlytics will alerts you on every new crash "
modified: 2017-01-15
category: mobile
thumbnail: fabric-dashboard-copy.png
tags: [mobile apps, android, ios, crash, analytics]

---

Have you ever published a mobile app? Or have you ever developed it? Or if not, I am sure at least you ever tried Android or iOS apps. If yes, you must be familiar with crashes. On Android app (sorry I’m not an iPhone user :p, I dont have example on it), crash or also known as force close is seen by user with a dialog told like “Unfortunately, [App Name] has stopped” or in Indonesia is like “Sayangnya, [Nama Aplikasi] telah terhenti”. 

<div class="row">
  <div class="large-5 columns">
    <figure>
      <img width="375" src="{{ site.github.url }}/assets/img/posts/crash-example.png" alt="Fabric on Android Studio">
      <figcaption>Crash on Android</figcaption>
    </figure>
  </div>
  <div class="large-7 columns">

    <div class="row">

      <br/>

      <strong><span style="font-size: 25px; line-height: 1; ">Why should we care to crashes?</span> </strong>

      <br/>
      <br/>

      <span style="font-size: 18px; line-height: 1.5; "> Those are serious problem because mostly crashes trigger users to give bad rating or review. So how to handle it? If you’re in development, it’s simple. On Android, you only needs to look at logcat and there will be stacktraces related to the crash. However be careful, if the dialog appears, don’t press OK (to close) first, just let it appears while you checking on the logcat. </span>

    </div>
    <div class="row">

      <br/>
      <br/>

      <strong> <span style="font-size: 25px; line-height: 1;">Then, how to handle crashes on production? How we know the cause of crashes on every user session?</span> </strong>

      <br/>
      <br/>

      <span style="font-size: 18px; line-height: 1.5; "> Did you think users want to send feedback report if the apps crash happened? I think there is a big no, or just a little user care about it. But don’t worry, some people there already made it. Till now it’s free. Free for your app even it used by millions users. </span>

    </div>
  </div>
</div>

<br/>

## Introducing Crashlytics by Fabric by Twitter
-----
They said: “Crashlytics is a powerful and lightweight crash reporting system with detailed reports and real-time alerts.” Yeah it’s true. We only needs to integrate Crashlytics plugin on your mobile app (Android and iOS) project that takes only some minutes, and then we have a dashboard showing the crashes on your app and the number each crash happened. We can get the full stacktraces to fix the crash later. It saves our time a lot to think the cause of every crash then focus to fix it. You even can get notifications with email or other kind like Slack if there is new kind of crash. Take a first look on [fabric.io](https://fabric.io/).


### 1. Installation

Spare some minutes to follow this set-up link on your native [Android](https://fabric.io/kits/android/crashlytics/install) or [iOS](https://fabric.io/kits/ios/crashlytics/install) projects. If you uses common IDE i.e. [Android Studio](https://fabric.io/downloads/android-studio) or [XCode](https://fabric.io/downloads/xcode). On Android, we will see Fabric’s plugin on the right side (by default) on your Android Studio like below. This embedded fabric kits make you easier to use them.

<figure>
  <img width="800" src="{{ site.github.url }}/assets/img/posts/android-studio-fabric.png" alt="Fabric on Android Studio">
  <figcaption>Easily add-on Fabric Kits on Your IDE</figcaption>
</figure>

### 2. Dashboard

Fabric dashboard, as you seen, is a summary of every crash event on your selected app. Fabric will sort it by number-of-crashes as priority, then you can filter it by users’ device, app build version, times, and status as you can close any crash if it has been fixed. 
 
<figure>
	<img width="800" src="{{ site.github.url }}/assets/img/posts/fabric-dashboard-copy.png" alt="Crashlytics Dashboard">
	<figcaption>Crashlytics Dashboard on One My On-Development App</figcaption>
</figure>

### 2. Stacktraces

Choose any crash on your dashboard. Take a look on the crash detail page. There, you will see the full stack traces on all the threads. You can download the raw and place it back to your IDE. You even can create comments on it, then after fix the crash, you can close it.

<figure>
  <img width="800" src="{{ site.github.url }}/assets/img/posts/fabric-stacktraces.png" alt="Crashlytics Stacktraces">
  <figcaption>Full Stacktraces to make your fix easier</figcaption>
</figure>


## Finally
-----

Actually there are some other functionalities that Crashlytics could help your mobile app team. Moreover, there are also other kits offered by Fabric beside Crashlytics. Explore it to get more valuable-free tools to assists your mobile apps project. Fyi, I really appriciate Crashlytics, and have no idea how they give it free for us. So try it if you haven’t geeks !


