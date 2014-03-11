---
layout: post
title:  "Imminent Initial Corgi Click Tracker Release!"
date:   2014-03-10 21:49:01
categories: jekyll update
---

I've been really interested in Akka and Spay lately and what better to
learn the frameworks than to utilizing them in real life! At this
point, I figure doing something simple is a good start. I call it
project __Corgi__!

Corgi's primary purpose will be to provide a scalable click tracker
service. Here are a list of features I'm thinking of including to reach
an initial milestone:
* Provide a tinyurl-like service for click events to be sent into,
  tracked, and then redirected to it's intended destination.
* Provide a admin page to administrate your links.
* Provide a reports page that will generate data in real-time.

It will be composed of the following components:

* The project will be written in [Scala](http://www.scala-lang.org/).
* [AngularJS](http://angularjs.org/) will take care of the UI.
* [Spray](http://spray.io/) / [Akka](http://akka.io/) will take care of
  the click serving and HTTP REST API.
* [Kafka](http://kafka.apache.org/) will aggregate the click events.
* [Summingbird](https://twitter.com/summingbird) /
  [Storm](http://storm.incubator.apache.org/) will process the click
  events and generate metrics.
* [NVD3](http://nvd3.org/) will be the charts library used to render
  the metrics.

I plan to release the code on
[GitHub](https://www.github.com/pcting/corgi) under the Apache v2
license.

I've already got some working code, but I'll release it once I've a
good point where Corgi can be demoed. If anyone else is interested,
shoot me an email!

In the meantime, stay tuned for more to come!
