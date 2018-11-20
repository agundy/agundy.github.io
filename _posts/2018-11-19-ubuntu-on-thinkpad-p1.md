---
layout: post
title: Ubuntu on Thinkpad P1
tags:
  - Linux
  - Ubuntu
---

I just set up the Thinkpad P1 as my new work computer. The new computer
involved some joys of Linux I haven't had to do in a long time. I had to do a
few workarounds so I decided to document them here. 

I was installing Ubuntu 18.04 on the P1 with the Nvidia Quadro P2000 and the 4k
display. On first run trying to install Ubuntu it errored out loading. I ended
updating Windows 10 completely and flashing an updated bios I found reference
to in [this thread](https://www.reddit.com/r/thinkpad/comments/9fep9s/linux_can_now_be_installed_on_thinkpad_p1_and_x1/)
see the direct Thinkpad driver link
 [here](https://pcsupport.lenovo.com/us/en/products/LAPTOPS-AND-NETBOOKS/THINKPAD-P-SERIES-LAPTOPS/THINKPAD-P1-TYPE-20MD-20ME/downloads/DS504958).

After that I got a little further, but ended up having issues installing while
running in hybrid graphics mode. I switched the bios setting to discrete and
could successfully install Ubuntu. But after the first boot I could not login.
Digging around it appears that something was not 100% with the graphics and
X11?. Choosing the option of logging in with Gnome and Wayland allowed me to get
to a terminal and updater. Where I promptly upgraded everything with a 

```
sudo apt update
sudo apt dist-upgrade
```

Performance during this was terrible though. Mostly due to gnome using > 100%
CPU, nice. To get the Nvidia graphics card working I ran
`sudo apt-get install nvidia-375 nvidia-settings`. After a reboot this did a
lot better.

After the annoying setup everything has been working well since. Overall the
laptop is pretty nice, good size and high quality screen. Extremely
dissapointed that the laptop came with a broken delete key though. It should
have two small clips to keep it attached but one is broken so hitting the
delete key on the right side pops off the key. Crazy for the brand once
renowned for their reliable keyboards. We should be giving Thinkpad a hard time
if Mac get's one for a less obnoxious reason. Performance wise it seems decent
but it definitely runs hot. I have the 4K screen upgrade, Intel® Core™
i7-8750H, 32 GB of RAM and the Quadro P2000 graphics card.  Together this makes
for a powerful computer but it's definitely not quiet, I need to do some tuning
so that I'm conserving battery and not running a fan on high frequently.
