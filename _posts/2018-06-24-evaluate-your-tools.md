---
layout: post
title: Evaluate Your Tools
tags:
  - Learning
  - Workflows
---

How often do you take a step back and ask yourself if you are doing things the
most efficiently? I am in a terminal a large part of my day; running tests,
editing in Vim, running git commands, checking files, etc. Over the years I've
built up shortcuts and workflows to keep me fast and focused on what I need
done. But I still have lots to learn and sometimes it takes getting really
annoyed with a repitious action before we finally realize there might be the a
better way. 

The other day I discovered `CTRL+W` and `CTRL+U` for the first time. `CTRL+W`
deletes the last word in the prompt. `CTRL+U` will clear the current line.

Some other tips and tricks I have found helpful.

- Use `TAB` to autocomplete commands/files etc.

- Use `CTRL+R` to search previously entered commands.

- You can repeat the last command you typed with `!!`, this is useful if you
forget `sudo`, i.e. `apt-get update` can be re-run with `sudo !!`.

- Want just the last arg you entered? Use `!$`. A good example of this typing `ls
~/Documents/folder` and then wanting to change to that directory. You can do
this with `cd $!`.

Am I missing any good shortcuts? This is your reminder to keep learning and
evaluating your tools.
