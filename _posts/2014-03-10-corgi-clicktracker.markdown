---
layout: post
title:  "Imminent Initial Corgi Click Tracker Release!"
date:   2014-03-10 21:49:01
categories: jekyll update
---

I've been really interested in Akka and Spay lately and what better to
learn the frameworks than to start a new project utilizing them! It
will be a simple click server written in Scala with the following
frameworks:

* [AngularJS](http://angularjs.org/) to take care of the UI.
* [Spray](http://spray.io/) / [Akka](http://akka.io/) to take care the HTTP REST service.
* [Kafka](http://kafka.apache.org/) to aggregate the click events.
* [Summingbird](https://twitter.com/summingbird) / [Storm](http://storm.incubator.apache.org/) to read the click events and generate metrics.

I plan to call the project Corgi and plan to release the code on
[GitHub](https://www.github.com/pcting/corgi) under the Apache v2
license.

Stay tuned!
