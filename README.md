[![Build Status](https://travis-ci.org/stargazer/django-deserializer.png?branch=master)](https://travis-ci.org/stargazer/django-deserializer)
[![Coverage Status](https://coveralls.io/repos/stargazer/django-deserializer/badge.png?branch=master)](https://coveralls.io/r/stargazer/django-deserializer?branch=master)
[![PyPI version](https://badge.fury.io/py/django-deserializer.svg)](http://badge.fury.io/py/django-deserializer)
[![PyPI](https://img.shields.io/pypi/dm/django-deserializer.svg)](https://pypi.python.org/pypi/django-deserializer/)

# Django Deserializer

A Django Mixin capable of deserializing a request's body into python data
structures. It works for requests with Content-type either
``application/json`` or ``application/x-www-form-urlencoded``.

Tested in ``Python 2.7`` and ``Python 3.2`` against ``Django >= 1.5``.

## How to install

    pip install django-deserializer

## How to use

Simply have your Class-Based View inherit from the
``deserializer.mixins.DeserializationMixin``. From that point on, the view has
inherited the ``deserialize`` method. When invoked, that method deserializes
and returns the request's body.

    from deserializer.mixins import DeserializationMixin
    from django.views.generic.base import View

    class MyView(View, DeserializationMixin):
        def post(self, request, *args, **kwargs):
            body = self.deserialize()


