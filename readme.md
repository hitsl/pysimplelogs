Version: __0.1.0__

About
=====

__pysimplelogs__ is a python client library for [Simplelogs] [sl] logging system.


Requirements
============
  * [Requests] [requests]


[sl]: https://github.com/SkyFox/simplelogs
[requests]: http://docs.python-requests.org/en/latest/

Config-file description
=======================

Before using this lib in your code, please change settings in config.py:

    SLEEP_TIME = 0.1 # Time between attempts for sending log entry.
    NUMBER_OF_ATTEMPTS = 5 # Attempts.
    CONNECTION_TIMEOUT = 3 # Connections timeout in seconds.
    URL = "http://127.0.0.1/" # Main API URL.


How to use
==========

Very simple!

    from pysimplelogs import simplelog
    simplelog.warning({'ip': '127.0.0.1', 'name': 'Jon'}, "Hello, world!", ["core", "client"])

__Message format__:

    simplelog.level-name(owner, data, tags)

__Description__:

  * __level-name__ - any level, that server returns by URI http://host/api/level/. It can be customized in
  [simplelogs] [sl] config-file.
  * __owner__ - entry owner. String or dictionary. [Required]
  * __data__ - entry owner. String or dictionary. [Required]
  * __tags__ - list only.