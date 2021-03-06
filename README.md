Alpine Apache ActiveMQ Docker
===============

[![Build Status](https://travis-ci.org/CodingInfinity/docker-alpine-activemq.svg?branch=master)](https://travis-ci.org/CodingInfinity/docker-alpine-activemq)
[![ZenHub](https://raw.githubusercontent.com/ZenHubIO/support/master/zenhub-badge.png)](https://raw.githubusercontent.com/ZenHubIO/support/master/zenhub-badge.png)

[Docker](https://www.docker.io/) file for trusted builds of [ActiveMQ](http://activemq.apache.org/) on https://hub.docker.com/r/codinginfinity/alpine-activemq/.

Run the latest container with:

    docker pull codinginfinity/alpine-activemq
    docker run -p 61616:61616 -p 8161:8161 codinginfinity/alpine-activemq

The JMX broker listens on port 61616 and the Web Console on port 8161.

Image Tags
----------

    codinginfinity/alpine-activemq:latest
    codinginfinity/alpine-activemq/activemq:5.13.3

Port Map
--------

    61616 JMS
    8161  UI
    5672  AMQP
    61613 STOMP
    1883 MQTT
    61614 WS

Customizing configuration and persistence location
--------------------------------------------------

ActiveMQ checks your environment for the variables *ACTIVEMQ_BASE*, *ACTIVEMQ_CONF* and *ACTIVEMQ_DATA*.
Just override them with your desired location:

    docker run -p 61616:61616 -p 8161:8161 -e ACTIVEMQ_CONF=/etc/activemq/conf -e ACTIVEMQ_DATA=var/lib/activemq/data codinginfinity/alpine-activemq

As an alternative you can just mount your persistent config and data directories into the default location:

    docker run -p 61616:61616 -p 8161:8161 -v /opt/activemq/conf:/opt/activemq/conf -v /var/activemq/data:/var/activemq/data codinginfinity/alpine-activemq
    
# Sponsorships
## ZenHub 

<a href="https://zenhub.com"><img src="https://raw.githubusercontent.com/ZenHubIO/support/master/zenhub-badge.png"></a>

**ZenHub is how the world's best development teams work together.** ? 

As the only project management tool integrated natively in GitHub's UI, ZenHub helps you stay in your workflow without distractions. There are no new queues to check, entries to update, or priorities to manage outside GitHub. 

Because ZenHub's features are powered by native GitHub issues, it doesn't create more process - it gets out of your way so you can focus on shipping awesome products.

Download the ZenHub extension for Firefox or Chrome [here](http://www.zenhub.com). It's free for public, academic, and personal repositories. 
