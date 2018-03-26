---
layout: post
title: Working Effectively with Legacy Code
redirect_from: "/working-effectively-with-legacy-code/"
tags:
  - Learning
  - Programming
  - Reading
---

I have started working my way through the book Working Effectively with Legacy Code. I have been recommended this book multiple times and purchased it a while ago but hadn't gotten around to reading at. A few take-aways I got from the first few chapters:

## What is a unit test?

According to the author a unit test isn't a 'unit' if:

1. It talks to a database
2. Makes network calls
3. Touches the file system
4. Relies on a special environment configuration/setup

## Rules for changing legacy code
The author identifies the following steps to making changes.

1. Identify change parts
2. Find the test points
3. Break the dependencies.
4. Write tests for this code
5. Make changes and refactor
