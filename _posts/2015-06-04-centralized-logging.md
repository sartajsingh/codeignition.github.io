---
layout: post
title: "Centralized Logging in Distributed Systems using ELK"
description: "Get centralized logging using Elastic search, Logstash & Kibana."
tags: ['loggings','server logs','saas','open source','elastic search','logstash ','kibana ','chef ','puppet ','ansible','docker','big data','real time analytics','intrusion detection']
author: sumit
---
{% include JB/setup %}
An integral part of any system, logging maintains live records of everything that happens in that system. Logging is helpful in solving often mission critical issues like identifying performance bottlenecks, detecting intrusions or threats, analyzing & identifying trends or patterns, and doing a thorough audit whenever the need arises.

But despite its clearly important role, many logging mechanisms are riddled with problems. We won't go into why they arise, but rather touch on what they are, and how implementing centralized logging solves these problems. 

### Problems with Logs

**Plain Text Format**

Many systems write logs in flat files and the format is often in plain text. This is an obvious no-no, as the plain text log format limits the log’s usage to do grep and search for events, and also require custom scripts to do some sort of reporting or aggregation.

**Different Forms**

Typical systems today consist of many moving parts which generate logs in their own format and in their own files. So when you have to identify root cause of a problem the system is facing or any kind of investigation, your job is more difficult since you have to refer to multiple log files of different forms.

**Scattered**

Recently we have seen a rising trend of micro services based architectures & distributed systems. Any medium sized system following this trend consists of many layers like load balancers, proxies, app/web server and databases. Every layer has different logging patterns, different log files and also different nodes. 
All these problems make it very difficult to tail or grep the logs in an individual machine, and make centralized logging all the more necessary.

### Centralized Logging solves these problems

**Single Location**

Centralized logging stores all the logs generated by all the different layers in a single location, making search or processing fast and easy.

**Processing**

You can also process & parse the logs to the key value pair of format & tags.

* Format: Parse the plain text to structured data like JSON and extract the keys for the application environment, IP, host or time
* Tagging: Tag the logs to make it easy to search, identify and correlate

**Storage**

Store the generated & processed logs in your storage system optimized for search or data analytics like HDFS or Elastic search.

### Stack Configuration

There are many Open Source or Paid SaaS tools which help you configure, deploy & manage centralized logging, but our recommended stack is ELK.

The ELK stack consists of 3 main systems:

* **Logstash** is the router for logs which runs key structuring processes like grok and conversion of the logs to JSON
* **Elastic Search** fulfils all your search requirements, especially if you want to be thorough
* **Kibana** makes managing the centralized logging system easy by letting you build interfaces for search, analytics & other dashboards

Additionally there are Chef cookbooks, Puppet modules, Ansible playbooks & Docker images that will help you set up the ELK stack in your infrastructure.

### Further Reading

Check out these links to learn more about Centralized Logging with ELK & how to get started.

* [https://github.com/kurtado/elk-puppet](https://github.com/kurtado/elk-puppet)
* [https://github.com/bakhti/ansible-elk](https://github.com/bakhti/ansible-elk)
* [https://github.com/rackspace-cookbooks/elkstack](https://github.com/rackspace-cookbooks/elkstack)
* [https://github.com/willdurand/docker-elk](https://github.com/willdurand/docker-elk)
