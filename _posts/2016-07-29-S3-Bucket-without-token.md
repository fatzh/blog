---
layout: post
title:  "Remove S3 Bucket authentication tokens"
date:   2016-07-29 17:13:31 +0200
categories: tech
---

By default S3 bucket files served via Django using the Django Storages
application append an authentication token which expires after some time. This
can be a problem when sharing images hosted on the bucket via the URLs, as they
will disappear after some time. To prevent this, there's an option to add to
your `settings.py` :

{% highlight python %}
AWS_QUERYSTRING_AUTH = False
{% endhighlight %}

And the URLs of you files will be generated without token.
