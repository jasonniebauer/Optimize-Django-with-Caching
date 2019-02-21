# Scaling Django with Memcached
Caching tutorial for Django web apps.

**Table of Contents**
1. [Get Started](#get-started)
2. [Install Memcached](#install-memcached)
3. [Run Memcached](#run-memcached)
4. [Configure Django](#configure-django)

## Get Started

## Install Memcached

**Windows**
```
memcached.exe -d install
```

## Run Memcached

`-d`
`-m`
`-v` verbose. (-v, -vv, -vvv)

**Memcached Help**
```
memcached -h
````

**Start Memcached**
```
memcached start
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

---

* [Reference 1](https://djangobook.com/djangos-cache-framework/)
