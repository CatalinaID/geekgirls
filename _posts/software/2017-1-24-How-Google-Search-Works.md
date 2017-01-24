---
layout: post
title: "How Google Search Works"
author: icha
description: "Have you ever wondered how Google Search works? Like, how a single search could bring millions of results in seconds? How do Google find all of these pages?"
modified: 2017-1-24
category: software
thumbnail: screen-shot-google.png
tags: [search engine, google, how it works]
---

Have you ever wondered how Google Search works? Like, how a single search could bring millions of results in seconds? How do Google find all of these pages? We have known that the web is already big a long time ago, even bigger nowadays. Google [said]( https://googleblog.blogspot.de/2008/07/we-knew-web-was-big.html) that it found 1 trillion unique URLs in 2008, now around 130 trillion individual pages. With these fascinating numbers, Google Search is still trying to keep our search results relevant enough from tons of junk out there. Let us explore the story behind it.

## The History of Search
-----
In 1990, the first internet search engine called Archie (or “Archive” without the “v”) was written. The World Wide Web (WWW) didn’t exist yet at that time (it came alive by the end of 1990), so the internet was a network of connected public FTP servers which hosted a number of files. The Archie was a simple search engine on a FTP site which kept an index of directory listings that we could download.

In the early age of WWW, 1992, the WWW founder Berners-Lee set up a directory of web called VLib. In 1993-1994, primitive web searches were built, just a matched search on indexed titles and URLs along with description of the page which the site owner could submit. AltaVista was the first web search to allow natural language queries. In the same year, Lycos went public with ranked relevance and prefix matching. Google launched in 1998 with its unique algorithm which had made it to be the most popular search engine of all time. ([source]( https://www.wordstream.com/articles/internet-search-engines-history))

## Main Tasks of Search Engine
-----
Before the search is performed by us, the search engine has to build databases of pages all over the web. Why? For an illustration, if we come to a library and want to find a certain article, we could ask the librarian there. But if the librarian doesn’t know or doesn’t have knowledge of what books are there in the library, then it would be a wasted. So, the search engine must have a knowledge or databases that stores the information of web pages. How does the search engine find all of these pages?

Search engine runs special software robots, called <strong>spiders</strong>, to travel over the Web and look at a lot of pages in automated manner. The spiders start looking at a set of popular pages which contain some links on it. Then the spiders will follow the links mentioned on the page to the new pages. Then follow links on the new pages to other new pages, and so forth. This way, it looks like the spiders building its web. The process of the spiders travel and spreading across the Web, following links from page to page is called <strong>Web crawling</strong>.

While the spiders are crawling each pages, they feed on the necessary information of the page and store it in some place called <strong>the index</strong>. The index may store the full page, the content, or just some important words of the page. Of course, it also keeps the URLs of the page. 

The last task of the search engine, besides web crawling and indexing, is to search and show the results of queries. When the user gives a query, whether it is a title of an article, a sentence or phrases, the search engine should bring the relevant pages to the user. The search engine will go through its index and find which pages are relevant to the user’s query. 

## Google Architecture Overview
-----
This section tells the story of Google prototype based on the study of Sergey Brin and Lawrence Page in 1998 ([source]( http://infolab.stanford.edu/~backrub/google.html)). Be aware that it may contain technical terms.

As mentioned before, the first task of a search engine is to do web crawling. Google used several <strong>crawlers</strong> which receive list of URLs from the <strong>URL Server</strong>. The crawlers then sent information of the web pages to the <strong>Store Server</strong>. The store server compressed the full HTML of the web page and stored it in a <strong>repository</strong>.

In the repository, the compressed web pages were stored one after another and prefixed by docID, length, and URL. The <strong>indexer</strong> read the document in repository, uncompressed it, then parsed it.  After the document is parsed, every words on it are converted into wordID using hash table called <strong>Lexicon</strong>. The occurrences of words in current document along with the position and wordID are written into <strong>barrels</strong>. The <strong>sorter</strong> sorts the barrels by wordID.

While the indexer is parsing the document, it also parses each links on the page and store it (link from, link to, and text) in an <strong>anchors</strong> file. The <strong>URL Resolver</strong> reads the anchors file and put the URL together with its docID in the <strong>Doc Index</strong>. URL Resolver also generates <strong>Links</strong> database which contains pairs of docID (from-to link). The Links database is used for compute the <strong>PageRanks</strong>. The <strong>searcher</strong> is run by a web server and uses the lexicon together with PageRanks to answer queries.

<figure>
	<img width="500" src="{{ site.github.url }}/assets/img/posts/over.gif" alt="High Level Google Architecture b(source: The Anatomy of a Large-Scale Hypertextual Web Search Engine, Sergey Brin and Lawrence Page">
	<figcaption>Figure 1: High Level Google Architecture</figcaption>
    <figcaption>(source: The Anatomy of a Large-Scale Hypertextual Web Search Engine, Sergey Brin and Lawrence Page)</figcaption>
</figure> 


## The Googlebot
-----
There were several distributed crawlers called Googlebots which did the web crawling in Google. Typically they ran 3 crawlers, which each one of these kept around 300 connections and maintained its own DNS cache. Each of the connections could be in a different states: looking up DNS, connecting to host, sending request, and receiving response. These were necessary to crawl the web pages fast enough. Four Googlebots could crawl over 100 web pages per second. ([source]( http://infolab.stanford.edu/~backrub/google.html))

The crawl process began with a list of URLs from past crawls and sitemaps that were provided by site owners. The Googlebots paid special attention to new sites, changes to existing sites, and dead links. However, site owners have a choice to not allow their site to be crawled by Googlebot. They also can give special instructions of how their pages should be processed by the Googlebot. These restrictions and instructions are written in a file called robots.txt. ([source](https://www.google.com/insidesearch/howsearchworks/crawling-indexing.html))

## The Google Index
-----
As Google gathers the web pages while crawling, it stores the web page in such a way that it knows how to look things up. It creates an indexing system which includes the information about words and its location on the web page. In a complicated manner, it also takes note of many aspects of the page, such as the publish time, the pictures and videos contained in the page, and much more. ([source](https://www.google.com/insidesearch/howsearchworks/crawling-indexing.html))

As it keeps the track of it all in the Google index, the Google index now is over 100 million gigabytes :O

## The Google Searching
-----
> “The perfect search engine would understand exactly what you mean and give you back exactly what you want,” 
Larry Page, Co-founder & CEO of Google.

Google wants to deliver the best search results as possible. So, the Google engineers work hard to improve the algorithm as you type your query as well as showing the results. They are looking for these clues to better understand what your query means:

* <strong>Spelling</strong>: It's about the spelling of query that you typed. Google identifies the spelling error, then guess the corrects spelling and provide the alternatives of your query.
* <strong>Autocomplete</strong>: The words or terms we use may have multiple meanings. Google tries to understand what you mean and predicts what you might be searching for.
* <strong>Synonyms</strong>: Different words may have the similar meaning. Google makes use of these to choose which pages are relevant.
* <strong>Search Methods</strong>: Google improves the way we search using images and voices.

Based on these clues, Google can search the pages on the Google index and return the relevant documents. There could be millions of documents which are relevant, so Google needs algorithms for page ranking to help you get the most relevant results at the top. (They know that we don't like to open up links more than 2 pages)

The basic yet important yet unique algorithm that Google use to produce high precision reults, is <strong>PageRank</strong>. This algorithm calculates quality ranking of web pages based on citations and backlinks to the page. But it doesn't count links from all pages equally, it normalizes the number of links on a page. The detail of the algorithm is explained in the next section.

Along with those clues and ranking algorithm, totally Google uses 200 factors to guess what you might really be looking for. The complete list of these 200 factors goes [here](https://id.pinterest.com/pin/94012710945342439/).

## PageRank
-----

Assume that `page A` has pages `T1 ...Tn` which links to it. The parameter `d` is the damping factor. `C(A)` is number of links that are contained on page A. The PageRank of page A is:

{% highlight css %}
PR(A) = (1-d) + d ( PR(T1)/C(T1) + ... + PR(Tn)/C(Tn) )
{% endhighlight %}

Intuitively, we can think of PageRank as follows:

Assume that there is a <strong>Random Surfer</strong> who visits an initial random page, then keep follows the links on the page but never going back. He keeps doing this until he gets bored and starts another initial random page again.

PageRank is the probability of the random surfer visits a page. The damping factor d is the probability of a page which the random surfer may get bored.

This calculation means that if there are many pages links to a page, then the page will get high PageRank. If there is only one page but a popular page links to a page, then the page will also get high PageRank.
 
## Conclusions
-----
And that is how Google Search works, in a way that I understand. With its simple front page and results page, Google helped us to have access on information that we want. It was built as a complex system to begin with and is still improving until now. 

Honestly, there are many interesting things in the study of Sergey Brin and Lawrence Page that I could share to you. But I think this post is long enough for you to read (you can read the paper by yourself btw). Thank you for reading until the end, hope you didn't get bored of my writing :)


