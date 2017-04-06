Fastest Cache
=============

An experiment ground for testing which cache backend is the fastest.


Sample Run
----------

Start the server:

    ./manage.py runserver

First run it a bunch of times:

    ab -n 10000 "http://127.0.0.1:8000/random"

Then to see which was the fastest:

    curl http://127.0.0.1:8000/summary

You'll get an output like this:

                             TIMES        AVERAGE         MEDIAN         STDDEV
    default                     73        0.034ms        0.033ms        0.005ms
    memcached                   59        0.297ms        0.261ms        0.144ms
    pylibmc                     89        0.222ms        0.211ms        0.039ms
    redis                       75        0.244ms        0.234ms        0.052ms
