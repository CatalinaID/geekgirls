Catalina Geek Blog
=========================

## Initial
 - Clone this repository

## How to post
 - Place an image in `/assets/img/posts/`
 - Create posts using the follow as an example, and put it in directory `/_posts/{{category}}`:
 - Don't forget to use this convention as file name `yyyy-mm-dd-{title separated by dash}.md`

```txt
---
layout: post
title: Theme Elements
author: hayyu
description: "Just about everything you'll need to style in the theme: headings, paragraphs, blockquotes, tables, code blocks, and more."
modified: 2013-05-31
category: data
tags: [sample post]
imagefeature: cover6.jpg
thumbnail: cover5.jpg
---
```
 - Commit and push it to github

## Local Preview
 - Install Jekyll [http://jekyllrb.com]
 - `cd` to the project directory
 - Run command `bundle install`
 - Run command `bundle exec jekyll serve`
 - Go to `http://127.0.0.1:4000/` in your browser

## How to work with draft
 - Create post and put in directory `/_drafts`. File name convention is `{title separated by dash}.md`
 - Local preview by run command `bundle exec jekyll serve --drafts`
