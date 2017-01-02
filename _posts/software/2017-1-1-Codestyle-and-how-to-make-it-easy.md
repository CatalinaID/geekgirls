---
layout: post
title: "Code Style: Why and How to Make It Easy"
author: afik
description: "I used to hate code style but I'll tell you why it's important"
modified: 2017-1-1
category: software
tags: [code style, linter, best-practice-software-engineering]
imagefeature: code-style.png
fb-url: https://www.facebook.com/catalinageekgirl/posts/1481959778498208
---
Hi, Happy new year geeks! 

The first time I know about code style is when I was on my internship 1,5 year ago. I coded in Java and my mentor asked me to try Maven Checkstyle. Of course, it gave me a lot of errors on the first run. I remember complaining to my friends about why we should fix all the whitespaces that being stated wrong by checkstyle. We ended up omitting all the rules that we think unimportant (like all that whitespace). And almost one and half year later, I faced the same problem. My first pull request in my current job was full of comments about whitespace problem. I spent almost a day for setting up linter and fixing my codes. 

I started to wonder, why code stye matters? Why should I put a space after an anonymous function in javascript when it already works without that? I read some articles ([1](http://blog.arkency.com/2014/07/code-style-matters/)) ([2](https://www.smashingmagazine.com/2012/10/why-coding-style-matters/)) ([3](http://paul-m-jones.com/archives/34)) and found a conclusion about this stuff. Code style really matters when you work in a team. Code style is about how your code looks. It becomes important when you work on a team because the code itself should be your communication tools with your teammates. People said that we can easily understand the code when it looks familiar and well structured. 

I have an experience to prove that the statement is definitely correct. Back then in college, I joined a robotics team. Our robot was using single board computer which had a very limited resource. If we used code editor like sublime or even notepad, it would be really slow. That's why we used nano to code. We didn't even bother thinking about how the code looks like because sometimes finding an opening bracket can be a pain in the ass. We didn't realize that it would be a really big problem for our juniors who receive our codes as a legacy. I myself spent almost a week only for tidying up the codes before really understood how it actually worked. The case was really different from when I looked at my company codes for the first time. It is really easy to understand and they look nice as if it was written by the same person. 

<figure>
  <img width="700" height="600" src="{{ site.github.url }}/assets/img/posts/crappy code example.png" alt="Crappy code example">
  <figcaption>This is one example of the code thet we used to made (copyright: Battle ITB)</figcaption>
</figure>

Okay, that's an extreme example. The point is, when you work in a team, it's important to have standards on how your codes look like. And obey those standards. You don't need to have a meeting to discuss will you add space after anonymous function or not. Just use the existing style guide like [googlestyle](https://google.github.io/styleguide/). The other important thing to note is you don't need to check and format your code manually. 

<figure>
  <img width="700" height="600" src="{{ site.github.url }}/assets/img/posts/style-sample.png" alt="Linter ftw">
  <figcaption>I installed eslint and jshint package in my SublimeText and they become my code style assistant instantly</figcaption>
</figure>

There's a lot of static code analysis tools or linter as well as code formatter/beautifier that you can choose. Your team only need to use the same linter and pick the same rules. And voila your repository will look like it was made by one person. You can find a comprehensive list of linter for every language [here](https://github.com/mcandre/linters). 

<figure>
  <img width="853" src="{{ site.github.url }}/assets/img/posts/code_quality.png" alt="code quality">
  <figcaption>Nice comic by xkcd (https://xkcd.com/1513/)</figcaption>
</figure>
