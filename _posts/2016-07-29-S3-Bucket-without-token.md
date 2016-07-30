---
layout: post
title:  "Remove S3 Bucket authentication tokens"
date:   2016-07-29 17:13:31 +0200
categories: django
---

By default S3 bucket files served via Django using the [Django
Storages](http://django-storages.readthedocs.io/en/latest/)
application append an authentication token which expires after some time. This
can be a problem when sharing images hosted on the bucket via the URLs, as they
will disappear after some time. To prevent this, there's an option a bit hidden which can be added to
your `settings.py` :

```python
AWS_QUERYSTRING_AUTH = False
```

And the URLs of you files will be generated without token.
