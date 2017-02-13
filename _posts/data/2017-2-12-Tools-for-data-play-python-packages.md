---
layout: post
title: "Tools for Data Play: Python Packages"
author: hayyu
description: "Wanna play with data? Here are some tools you can use to play with data."
modified: 2017-2-12
category: data
thumbnail: image4198.png
tags: [python, pandas, numpy, matplotlib]
thumbnail: gambar.jpg
fb-url: https://www.facebook.com/catalinageekgirl/posts/1525810540779798

---
*"I got some datasets from [here](https://www.kaggle.com/datasets). Then what should I do to get insights from it?"*

Well, first you have to get to know the basic detail of the dataset such as the attributes contained in it, description or semantic meaning of the attributes, value type of each attributes, how many records (data rows) with certain criteria, etc. You can use some tools which have the ability to do data exploration / data analysis. In this post, I will give a brief explanation of some Python packages that may come in handy for you to gain insights from your dataset.

### 1. Pandas

Usually, datasets are distributed in the form of CSV (comma separated values) files. You can open CSV files using Microsoft Excel or text editor e.g Notepad, Sublime Text, etc. Or, if you want to explore the datasets using Python, you can use Pandas to load your datasets.

When I want to explore CSV files using Python, I usually load the files as Pandas `DataFrame`. What is `DataFrame`? I quoted `DataFrame` definition from [here:](http://pandas.pydata.org/pandas-docs/stable/dsintro.html)

> DataFrame is a 2-dimensional labeled data structure with columns of potentially different types. You can think of it like a spreadsheet or SQL table, or a dict of Series objects.

In other (simpler) words, `DataFrame` is like a table.

And here is a code snippet of Pandas usage to load and display data from CSV files:

```python
import pandas as pd
df = pd.DataFrame.from_csv('dataset.csv', index_col=None)

# show first 10 rows
print df.head(10)

# show first 5 columns of 10 first rows
print df.iloc[:10, :5]

# get rows with certain condition e.g value of column A more than 1000
print df[df['A'] > 1000]

# get the data type of a column
print df['A'].dtype
```

That's just a simple example of Pandas usage. If you'd like to see more example, you can visit [this web](http://manishamde.github.io/blog/2013/03/07/pandas-and-python-top-10/) and [this web.](http://dataconomy.com/2015/03/14-best-python-pandas-features/)

### 2. NumPy

Some datasets may contain numerical data. If you want to do scientific or numeric computing on the dataset, NumPy can be the tool of choice. Moreover, NumPy is well known of its ability to process multidimensional-array/matrix.

Let me show you some NumPy functionalities:

```python
import numpy as np

a = np.array([
    [1,2,3],
    [4,6,5]
])

b = np.array([
    [3,2],
    [5,8],
])

# get the mean of each columns
print a.mean(axis=0)
# get the mean of each rows
print a.mean(axis=1)
# get the median of each columns
print np.median(a,axis=0)
# merge two matrices
c = np.hstack((a,b))
print c
```

Again, that's just a little example of NumPy functionalities. If you want to dig deeper, you can visit [this web.](http://scipy.github.io/old-wiki/pages/Numpy_Example_List#hstack.28.29)

### 3. Matplotlib

Sometimes the size of the datasets is so huge that makes reading all data row by row is painfull. We don't need to waste our time to check all single rows in the dataset if we can create 'pretty summary' from it, right? Matplotlib can help you to generate some kind of chart to summarize your data.

<figure>
    <img width="853" src="{{ site.github.url }}/assets/img/posts/matplotlib.jpg" alt="Some charts created using Matplotlib">
    <figcaption>Some charts created using Matplotlib (<a href="http://pandas.pydata.org/pandas-docs/version/0.18.1/visualization.html">Source</a>)</figcaption>
</figure>  

I won't give you code snippet to generate chart using Matplotlib :P You can discover the code on [this documentation](http://pandas.pydata.org/pandas-docs/version/0.18.1/visualization.html), as well as all Matplotlib chart types.

### 4. Scikit-Learn

Done exploring some basic detail of your dataset? Want to feed your data to machine learning algorithm? You don't need to implement the algorithm from scratch. In fact, you can find many machine learning algorithms (e.g for Classification, Clustering, Regression) in Scikit-Learn. To use those algorithms, all you need to do is import the correct module from Scikit-Learn. 

*"But, how to use that module to produce the desired output?"*

Don't worry :) Scikit-Learn has a good [documentation.](http://scikit-learn.org/stable/index.html) Even there are some examples of how to use Scikit-Learn modules which can be found [here.](http://scikit-learn.org/stable/auto_examples/index.html)

### 5. NLTK (Natural Language Toolkit)  

Your dataset contains textual data? Want to do [text classification](http://www.scholarpedia.org/article/Text_categorization) or [sentiment analysis](https://en.wikipedia.org/wiki/Sentiment_analysis)? If yes, then you should check [NLTK documentation.](http://www.nltk.org/index.html) 

NLTK has the functionalities to do text processing, such as:

1. sentence tokenizer: split a paragraph into sentences
2. word tokenizer: split a sentence into words
3. [stemming](https://en.wikipedia.org/wiki/Stemming): get the root form of a word, usually by removing affix from the word
4. [lemmatization](https://en.wikipedia.org/wiki/Lemmatisation): get the dictionary form of a word
5. Part-of-Speech tagging: tag each words in a sentence according to the syntactic functions of the word (noun, pronoun, verb, etc)

-----
Actually there are many more Python packages that can be used to play with data. You can find a list of usefull Python packages for data science [here.](https://github.com/rasbt/pattern_classification/blob/master/resources/python_data_libraries.md) In this post, I only mention some basic packages which which are commonly used.

I intended to create a serial post about **Tools for Data Play**. This serial is based on my exploration/experience in using the tools, enriched with related information from some references. This post is my first post for this serial.   

If you have any comments, questions, or any thoughts about this post, please let us know by leaving your words on the comment box below ya :)
