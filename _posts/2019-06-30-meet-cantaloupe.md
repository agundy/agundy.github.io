---
layout: post
title: Meet Cantaloupe
---

This is a fun little project I built this winter and I haven't shown off here
yet. I have been itching to build a home server for a media center, network
attached storage and general nerd playground. One weekend I dragged Michelle to
Micro Center and grab threw together a pretty decent server for under $400.

![Desktop Picture](/assets/img/blog/cantaloupe.jpg)

For the people looking for specs:

**Case:** [Cooler Master Elite](https://www.coolermaster.com/catalog/cases/mini-itx/elite130/)

**Processor:** AMD Ryzen 3 2200G

**RAM:** 16GB

**Storage:** 120GB SSD + 2TB Hard Drive

Over all it's a relatively performant box to run as a Linux server. I really
dig the compact case and my only gripe was the noisy stock fans, but I replaced
them for $25 and have not been able to hear it since.


I have already gotten a chance to do projects with it:

- Backup Hub: I set up all my laptops and desktops to backup to Cantaloupe and
  then it backs up to remote locations.
- Git Mirror: I wrote a simple Ruby CLI tool
  [Crow](https://github.com/agundy/crow) to grab all code repositories and
download them to local for backups.
- Private Git Repos: Git works over plain SSH so I set up a git user with
  repositories for code I don't want to put on other servers.
- Plex Server: I set up my movies and music to be available locally on the
  network, next stop accessing outside my home network.


Anything else fun I should do with it? Would you have built it differently?
