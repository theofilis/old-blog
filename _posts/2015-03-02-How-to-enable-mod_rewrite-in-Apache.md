---
layout:     post
title:      "How to enable mod_rewrite in Apache?"
date:       2015-03-02 12:00:00
author:     "George Theofilis"
header-img: "img/post-bg-02.jpg"
---

To enable it the rewrite module, run "apache2 enable module rewrite":

{% highlight bash %}
sudo a2enmod rewrite
{% endhighlight %}

You need to restart the webserver to apply the changes:

{% highlight bash %}
sudo service apache2 restart
{% endhighlight %}

If you plan on using mod_rewrite in .htaccess files, you also need to enable the use of .htaccess files by changing AllowOverride None to AllowOverride FileInfo. For the default website, edit /etc/apache2/sites-available/default:

{% highlight bash %}
<Directory /var/www/>
    Options Indexes FollowSymLinks MultiViews
    # changed from None to FileInfo
    AllowOverride FileInfo
    Order allow,deny
    allow from all
</Directory>
{% endhighlight %}

After such a change, you need to restart Apache again.