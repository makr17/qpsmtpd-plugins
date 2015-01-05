qpsmtpd-plugins
===============

useful plugins for [qpsmtpd](http://smtpd.github.io/qpsmtpd/index.html) mta.

auto_whitelist
--------------

whitelisting plugin similar to whitelist and whitelist_soft.  grew out of periodic frustrations with greylisting, which I was trying to mitigate with manual whitelists.  found I was editing the whitelists more than I would like, wanted to automate as much as possible.

notable differences:

* automatically add rcpts from outbound emails to the whitelist so we can immediately receive reply
* use sqlite db instead of scanning text flatfiles (expecting auto whitelists to grow rather large, indexed db definitely preferable)
* attempts to import existing whitelist data from text configs at first run (currently broken)
* does not (yet) support per-recipient lists.  I don't use them, and the code to start was cleaner without it...
