# Optimize Django with Caching
Caching tutorial for Django projects.

**Table of Contents**
1. [Get Started](#get-started)
2. [Install Memcached](#install-memcached)
3. [Run Memcached](#run-memcached)
4. [Configure Django](#configure-django)
    * [Cache View by Route](#cache-view-by-route)

## Get Started

## Install Memcached
Open Command Prompt, change to the memcached directory, and execute the install command.

**Windows**
```
memcached.exe -d install
```

## Run Memcached

| Flag | Description |
|:-----|:------------|
| `-d` |             |
| `-m` |             |
| `-v` | verbose. (-v, -vv, -vvv) |

**Memcached Help**
```
memcached -h
````

**Start Memcached**
```
memcached start -v
```

**Stop Memcached**
```
memcached stop
```

**Start Memcached Daemon**
```
memcached -d start
```

**Stop Memcached Daemon**
```
memcached -d stop
```

## Configure Django

**Install Package**
```
pip install python-memcached
```

**settings.py**
```
CACHES = {
    'default': {
        'BACKEND': 'django.core.cache.backends.memcached.MemcachedCache',
        'LOCATION': '127.0.0.1:11211',
    }
}
```

**views.py**
```

```

### Cache View by Route
**urls.py**
```
from django.views.decorators.cache import cache_page
...
url(r'<route>', cache_page(60 * <minutes>)(<view>))
```

Example:
```
from django.views.decorators.cache import cache_page
...
url(r'^$', cache_page(60 * 1440)(views.index))
```

---

* [Django docs](https://docs.djangoproject.com/en/2.0/topics/cache/)
* [Django’s Cache Framework](https://djangobook.com/djangos-cache-framework/)
* [Clearing specific cache in Django](https://stackoverflow.com/questions/8784400/clearing-specific-cache-in-django)
* [Memcached: List all keys](https://www.darkcoding.net/software/memcached-list-all-keys/)
* [Check the content of a Django cache with Python memcached](https://stackoverflow.com/questions/8512842/how-do-i-check-the-content-of-a-django-cache-with-python-memcached)
* [python-memcached-stats](https://github.com/dlrust/python-memcached-stats)
* [Source code for django.views.decorators.cache](https://docs.djangoproject.com/en/2.1/_modules/django/views/decorators/cache/)
* [Per-view Cache docs](https://docs.djangoproject.com/en/1.11/topics/cache/#the-per-view-cache)
* [Specifying per-view cache in the URLconf](https://docs.djangoproject.com/en/1.11/topics/cache/#specifying-per-view-cache-in-the-urlconf)
* [Get many cached keys in one go](https://stackoverflow.com/questions/46241407/how-use-django-cache-in-view-without-cache-all-page)
* [How to cache views in django](https://stackoverflow.com/questions/37691589/how-to-cache-views-in-django)
* [Django caching](https://www.tutorialspoint.com/django/django_caching.htm)
* [Memcached for Django](https://medium.com/@netfluff/memcached-for-django-ecedcb74a06d)
* [Caching and querysets](https://stackoverflow.com/questions/23976476/what-steps-are-needed-to-implement-memcached-in-a-django-application)
* [Memcached Implementation for Django](https://micropyramid.com/blog/python-memcached-implementation-for-django-project/)
* [Optimizing Django Through Caching](https://jeffknupp.com/blog/2012/02/24/django-memcached-optimizing-django-through-caching/)
* [Caching websites with Django and Memcached](http://www.ilian.io/caching-websites-with-django-and-memcached/)
* [Real Python tutorial](https://realpython.com/python-memcache-efficient-caching/)
