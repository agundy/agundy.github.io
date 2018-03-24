---
layout: post
title: My First Gem
tags:
  - Elasticsearch
  - Programming
---

Lately I have been working on upgrading Elasticsearch from 1.5.x to 5.1.x. Here are a few commands I've found myself using.

## Elasticsearch Version Number
To find what version of Elasticsearch you are running
```
$ curl localhost:9200/
{
  "name" : "1OgvfFN",
  "cluster_name" : "elasticsearch",
  "cluster_uuid" : "aoTJMozXSkOIyqG2CIf6wQ",
  "version" : {
    "number" : "5.1.2",
    "build_hash" : "c8c4c16",
    "build_date" : "2017-01-11T20:18:39.146Z",
    "build_snapshot" : false,
    "lucene_version" : "6.3.0"
  },
  "tagline" : "You Know, for Search"
}
```
##Health of your Cluster
```
$ curl localhost:9200/_cat/health
1493150160 19:56:00 elasticsearch yellow 1 1 20 20 0 0 20 0 - 50.0%
```
Red - no good
Yellow - pending or only node in cluster
Green - Good

##Aliases
To see a list of aliases on a node:
```
$ curl localhost:9200/_aliases/
{"series-test":{"aliases":{"series_read-test":{},"series_write-test":{}}},"authors":{"aliases":{"authors_read":{},"authors_write":{}}},"authors_1493148178_2148082-test":{"aliases":{"authors_read-test":{},"authors_write-test":{}}},"books-test":{"aliases":{"books_read-test":{},"books_write-test":{}}}}
```

