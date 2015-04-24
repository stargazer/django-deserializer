# Django Deserializer

A Django Mixin capable of deserializing a request's body into python data
structures. It works for requests with Content-type either
``application/json`` or ``application/x-www-form-urlencoded``.

Tested in ``Python 2.7`` and ``Python 3.2`` against ``Django >= 1.5``.

## How to install

    pip install django-deserializer

## How to use

Simply have your Class-Based View inherit from the
``deserializer.mixins.DeserializerMixin``. From that point on, the view has
inherited the ``deserialize`` method. When invoked, that method deserializes
and returns the request's body.

    from deserializer.mixins import DeserializerMixin
    from django.views.generic.base import View

    class MyView(View, DeserializerMixin):
        def post(self, request, *args, **kwargs):
            body = self.deserialize()


