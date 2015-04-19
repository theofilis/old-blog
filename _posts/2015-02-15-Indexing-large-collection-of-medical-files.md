---
layout:     post
title:      "Indexing large collection of medical files"
date:       2015-02-15 12:00:00
author:     "George Theofilis"
header-img: "https://encrypted-tbn2.gstatic.com/images?q=tbn:ANd9GcR4MCX44uPRhcamIuBFE50vzS4zwTZvX6Bm6To2grw1NIkPC-to"
tags:
- solr
- information retrieve
---

We have a large collection of medical files and we want to search and find similar symptoms to give a diagnosis. The medical files are in
two languages greek and english, this is our main problem. Another problem we have is the meta information of the document are not well
document and we have to extract them from the document.

## Test Processing & Data Cleaning

## Data Indexing

### Solr on Docker

This repository triggers the [makuk66/docker-solr](https://index.docker.io/u/makuk66/docker-solr/) trusted build on the Docker index. To run:

{% highlight bash %}
docker pull makuk66/docker-solr
docker run -it -p 8983:8983 -t makuk66/docker-solr
{% endhighlight %}

Then go to [http://localhost:8983/solr](http://localhost:8983/solr) (adjust the hostname for your docker server).

### Configure collection index

#### Greek Language

{% highlight xml %}
<filter class="solr.GreekLowerCaseFilterFactory"/>
<filter class="solr.GreekStemFilterFactory"/>
{% endhighlight %}

## Evaluation of searching method
