---
layout:     post
title:      "Install Laravel Administrator on Laravel 5"
date:       2015-03-02 12:00:00
author:     "George Theofilis"
header-img: "img/post-bg-02.jpg"
tags:
- php
- laravel 5
- sql server
---

Administrator is an administrative interface builder for Laravel. With Administrator you can visually manage your Eloquent models and their relations, and also create stand-alone settings pages for storing site data and performing site tasks.

## Installation

To install Administrator as a Composer package to be used with Laravel 5, simply add this to your composer.json:

{% highlight json %}
"frozennode/administrator": "5.*"
{% endhighlight %}

..and run composer update. Once it's installed, you can register the service provider in config/app.php in the providers array:

{% highlight php %}
'providers' => [
    'Frozennode\Administrator\AdministratorServiceProvider',
]
{% endhighlight %}

Then publish Administrator's assets with **php artisan vendor:publish**. 

This will add the file config/administrator.php. This config file is the primary way you interact with Administrator. This command will also publish all of the assets, views, and translation files.

## Settings Configuration