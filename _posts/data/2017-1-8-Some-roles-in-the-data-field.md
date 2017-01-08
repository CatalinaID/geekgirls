---
layout: post
title: "Some Roles in the Data Field"
author: hayyu
description: "There are many roles in data field. Here is a brief explanation for some of the roles."
modified: 2017-1-8
category: data
tags: [data science, data engineer, data analyst]
thumbnail: gambar.jpg
fb-url: https://www.facebook.com/catalinageekgirl/posts/1481959778498208
---
In this digital era, every minute we produce data, e.g tweeting, updating Facebook status, sharing news or article, or even just clicking the like button on the social media. No wonder if the volume of digital data is so big and keep on growing at an exponential rate ([source: Business Insider](http://www.businessinsider.co.id/mind-blowing-growth-and-power-of-big-data-2015-6/?r=US&IR=T#cVH20AoPhJoVAiGO.97)). 

In business, data can be used to analyze the company performance and be the base for decision making by the stakeholders. It's important to refer to the data before deciding what action we'd take for our business. We shouldn't only rely on our feeling or common sense for such a serious decision, right? Even the CEO of an Indonesian startup wrote a post about the urgency of being a data driven organization [in his blog](http://achmadzaky.com/data-driven-organization/). 

The urgency of data processing in a company has raised some new roles or job titles such as data scientist, data analyst, and data engineer. My friend once asked me about the difference(s) between those roles. At that time, I wasn't sure how to answer the question. I was confused and couldn't clearly state the difference, too. So I passed the question to Google and skimmed some of the top results. In this post, I'll summarize the answer of this question for you.

-----

### Data Scientist

The main mission of a data scientist is to get insight from data at hand and give actionable recommendation to the stakeholders. To do this, data scientist need to have statistics and programming skills as stated [here](https://metamarkets.com/2012/data-scientist-profile-pete-skomoroch/) that data scientist is better statisticians than most programmers and better programmers than most statisticians. The statistics skills are required to process the data (to produce insight), meanwhile the programming skills are required to make the process reliable, scalable and less manual because oftentimes data scientist need to deal with a huge volume of data.

Some tools that data scientist use are data mining and machine learning tools (e.g. WEKA, Python/R packages), Apache Spark, and Hadoop ([source: Big Data University](https://bigdatauniversity.com/blog/data-scientist-vs-data-engineer/)).

### Data Analyst

Data analyst's job description covers reporting and data visualization. Data analyst should have the ability to use some data processing tools to provide reports and chart for the company. Besides, data analyst must have a good querying skill too, so they can get the appropriate data to satisfy the company needs. 

To distinguish between data analyst and data scientist, it can be said that data analyst focus on summarizing the past while data scientist focus on strategizing for the future ([source: Udacity](http://blog.udacity.com/2014/12/data-analyst-vs-data-scientist-vs-data-engineer.html)). Data analyst aren't required to have a strong statistics and programming background to develop algorithms like data scientist. Here is a Venn diagram which visualize the similarities and differences between data analyst and data scientist.

<figure>
    <img width="853" src="{{ site.github.url }}/assets/img/posts/analyst-vs-scientist.jpg" alt="Similarities and differences between data analyst and data scientist">
    <figcaption>Similarities and differences between data analyst and data scientist (<a href="https://www.import.io/post/data-scientists-vs-data-analysts-why-the-distinction-matters/">Source</a>)</figcaption>
</figure>

### Data Engineer

Data scientist and data analyst do not directly use data from production (data which always changing/updating). Usually, a company provides a separate environment to store clean data for analysis purposes. The job of data engineer is to prepare and maintain the environment. Data engineers have software engineering background to design and develop the data infrastructure.

Besides preparing data infrastructure, data engineers also do ETL (extract, transform, load) process. They will retrieve data from various sources, transform and clean the data, then load it to the data infrastructure to be consumed by data scientist or data analyst. Skills to use some tools, such as Hadoop, database management system (relational and non relational), and programming skill are more important for data engineers than machine learning or data analytical skills. 

-----

Yup, that's a brief explanation for data scientist, data analyst, and data engineer roles. I hope it can help you to understand the similarities and the differences between those roles. 

If you have any comments or questions, feel free to put your comments or questions on the comment box below ya :)