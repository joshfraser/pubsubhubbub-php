pubsubhubbub-php
================

A PHP client for [PubSubHubbub](https://code.google.com/p/pubsubhubbub/) (also known as PuSH and PSHB).

**Update 7/5/09:**

This library has moved and is now being maintained as part of the main PuSH code base. You can find the latest version in the client libraries directory at [http://code.google.com/p/pubsubhubbub/](http://code.google.com/p/pubsubhubbub/)

**Usage**

    // specify which hub you want to use. in this case we'll use the demo hub on app engine.
    $hub_url = "http://pubsubhubbub.appspot.com/";

    // create a new pubsubhubbub publisher
    $p = new Publisher($hub_url);

    // specify the feed that has been updated 
    $topic_url = "http://www.onlineaspect.com";

    // notify the hub that the specified topic_url (ATOM feed) has been updated
    // alternatively, publish_update() also accepts an array of topic urls
    if ($p->publish_update($topic_url)) {
        echo "$topic_url was successfully published to $hub_url";
    } else {
        echo "Ooops...";
        print_r($p->last_response());
    }

**Credits & license:**

* [Read more about PubSubHubbub and this library](http://www.onlineaspect.com/2009/05/25/the-protocols-powering-the-real-time-web/) by [Josh Fraser](http://joshfraser.com)
* Released under Apache 2.0 license