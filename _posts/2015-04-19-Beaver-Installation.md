---
layout:     post
title:      "Beaver Installation"
date:       2015-04-19 12:00:00
author:     "George Theofilis"
header-img: "img/post-bg-02.jpg"
---

## Introduction

Beaver provides an lightweight method for shipping local log files to Logstash. It does this using redis, zeromq, tcp, udp, rabbit or stdout as the transport. This means you’ll need a redis, zeromq, tcp, udp, amqp or stdin input somewhere down the road to get the events.

Events are sent in logstash’s json_event format. Options can also be set as environment variables.

## Installation

### Requirements

* Python 2.6+
* Optional zeromq support: install libzmq (brew install zmq or apt-get install libzmq-dev) and pyzmq (pip install pyzmq==2.1.11

### Distribute & Pip

Installing Beaver is simple with pip:

{% highlight bash %}
sudo pip install beaver
{% endhighlight %}

## Usage

###Create configuration folders

{% highlight bash %}
sudo mkdir /etc/beaver
sudo mkdir /etc/beaver/conf.d/
sudo cd /etc/beaver/
{% endhighlight %}

###Create configuration files

#### /etc/beaver/conf
{% highlight bash %}
[beaver]
format: json
logstash_version: 1
{% endhighlight %}

#### /etc/beaver/conf.d/syslog
{% highlight bash %}
[/var/log/syslog]
type: syslog
tags: sys,main
{% endhighlight %}

### Start beaver daemon
{% highlight bash %}
beaver -c /etc/beaver/conf -C /etc/beaver/conf.d
{% endhighlight %}