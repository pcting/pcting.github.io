---
layout: post
title:  "Hadoop 2.2.0 + Ubuntu 13.10 + OpenSSH Server Docker Image"
date:   2014-03-10 21:49:01
categories: jekyll update
---

Over the past several weeks, I've been reinstalling packages and tools
for doing Hadoop development. It bugs me that I have to go through the
same steps over and over again! At first I thought I'd just go with
[Vagrant](http://www.vagrantup.com/), but I didn't want to run it
because..

* It runs VirtualBox underneath and it sucks to have to wait so long
  for the instance to spin up.
* Virtualization is overkill for my needs as I just need isolation and
  a way to quickly reset my Hadoop environment.
* It eats up CPU time and RAM.
* I/O sucks in a VM.

Enter [Docker](https://www.docker.io/). I love this thing! I loved it
so much I decided to learn it by building our my first Docker image,
which is now available to use on [Docker Index](https://index.docker.io/u/pcting/ubuntu_hadoop_single_node/).
The source code can be found on [GitHub](https://github.com/pcting/docker-container-recipes).

With this image, I just have to run the following to get an instance
of Hadoop 2.2.0 going:

    mkdir -p /tmp/docker-hadoop-data/ /tmp/docker-hadoop-logs/ && \
    docker run -t -i -rm \
      -e "AUTHORIZED_SSH_PUBLIC_KEY=$(cat ~/.ssh/id_rsa.pub)" \
      -v /tmp/docker-hadoop-data/:/home/hduser/hdfs-data/ \
      -v /tmp/docker-hadoop-logs/:/opt/hadoop/logs/ \
      -p 22:22 -p 2181:2181 -p 39534:39534 -p 9000:9000 \
      -p 50070:50070 -p 50010:50010 -p 50020:50020 -p 50075:50075 \
      -p 50090:50090 -p 8030:8030 -p 8031:8031 -p 8032:8032 \
      -p 8033:8033 -p 8088:8088 -p 8040:8040 -p 8042:8042 \
      -p 13562:13562 -p 47784:47784 -p 10020:10020 -p 19888:19888 \
      pcting/ubuntu_hadoop_single_node

Once the container comes up, you can shell into the machine like so:

    $ ssh hduser@localhost

Shoutout to [Michael Noll](http://www.rohitmenon.com/index.php/how-to-install-hadoop-on-ubuntulinux-mint/)
and [Rohit Menon](http://www.rohitmenon.com/index.php/how-to-install-hadoop-on-ubuntulinux-mint/)
for providing great references to get me started. When I have more
time, maybe I'll even build one out for Corgi!
