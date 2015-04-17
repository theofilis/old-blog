---
layout:     post
title:      "How do I fix the GPG error “NO_PUBKEY”"
date:       2015-04-14 12:00:00
author:     "George Theofilis"
header-img: "img/post-bg-02.jpg"
---

The error message look like this:

{% highlight bash %}
W: GPG error: http://packages.elasticsearch.org stable Release: The following signatures 
couldn't be verified because the public key is not available: NO_PUBKEY D27D666CD88E42B4
{% endhighlight %}

Execute the following commands in terminal

{% highlight bash %}
sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys D27D666CD88E42B4
{% endhighlight %}

and then update 

{% highlight bash %}
sudo apt-get update
{% endhighlight %}