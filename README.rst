========
Spot SDK
========

.. image:: https://badge.fury.io/py/spot-sdk.svg
    :target: https://badge.fury.io/py/spot-sdk

.. image:: http://img.shields.io/badge/license-MIT-yellow.svg?style=flat
    :target: https://github.com/gregology/spot-sdk/blob/master/LICENSE

.. image:: https://img.shields.io/badge/contact-Gregology-blue.svg?style=flat
    :target: http://gregology.net/contact/

Overview
--------

Simple SDK for extracting messages from Spot's API

Installation
------------

``spot-sdk`` is available on PyPI

http://pypi.python.org/pypi/spot-sdk

Install via ``pip``
::

    $ pip install spot-sdk

Or via ``easy_install``
::

    $ easy_install spot-sdk

Or directly from ``spot-sdk``'s `git repo <https://github.com/gregology/spot-sdk>`
::

    $ git clone git://github.com/gregology/spot-sdk.git
    $ cd spot-sdk
    $ python setup.py install

Basic usage
-----------
::

    >>> from spot_sdk import Feed
    >>> api_key = 'abcdefghijklmnopqrstuvwxy01234567'
    >>> feed = Feed(api_key)
    >>> feed.collect()
    >>> feed.count()
    6
    >>> foo.messages
    [<spot_sdk.Message object at 0x10fd7f630>, <spot_sdk.Message object at 0x10fd7f6a0>...
    >>> feed.first().type
    'UNLIMITED-TRACK'
    >>> feed.last().battery_state
    'GOOD'
    >>> feed.messages[0].latitude
    42.000
    >>> feed.last().datetime
    datetime(2017, 1, 1, 0, 42, 0)


Basic usage for private feeds (requiring password)
-----------
::

    >>> from spot_sdk import Feed
    >>> api_key = 'abcdefghijklmnopqrstuvwxy01234567'
    >>> password = 'your-password'
    >>> feed = Feed(api_key, password)
    >>> feed.collect()
    >>> feed.count()
    6
    >>> foo.messages
    [<spot_sdk.Message object at 0x10fd7f630>, <spot_sdk.Message object at 0x10fd7f6a0>...
    >>> feed.first().type
    'UNLIMITED-TRACK'
    >>> feed.last().battery_state
    'GOOD'
    >>> feed.messages[0].latitude
    42.000
    >>> feed.last().datetime
    datetime(2017, 1, 1, 0, 42, 0)

Running Test
------------
::

    $ python spot_sdk/tests.py

Python compatibility
--------------------

Developed for Python 3. May work but not tested in Python 2.
