---
layout: post
title: linux and my shift away from using windows at home
date: 2026-03-01 09:30:00
description: I want to move away from having Windows devices in my household if I can avoid it. The next step in that journey was my beloved gaming machine.
tags: software hardware tips
#categories: sample-posts
---

Lately Windows has really been getting on my nerves. 

Not only has their OS been responsible for the [outage](https://www.bbc.co.uk/news/articles/cpe3zgznwjno) of more than 8.5m devices in 2024, the company has been responsible for pushing out, and then retracting ['features'](https://www.bbc.co.uk/news/articles/c869glx8endo) which people hate, and are privacy intrusive. 

I've decided to take a stand and vote with my wallet and my usage habits. I've decided to make the transition to do the following to my home tech stack:

1. Dual boot Linux and Windows on my main gaming machine. I've chosen Manjaro Linux as my primary OS.
2. Lock down any telemetry running on the Windows OS if it still exists and disbale any bloatware if I havevn't done it already.
3. Transistion my main Thinkpad development/management machine (My Thinkpad X1 Carbon Gen 10) to a different flavour of Linux. I selected Fedora with KDE Plasma as my DE.

It's no secret that Windows has been Microsoft's golden goose for a while. It has a huge amount of global use, with some figures estimating the [percentage](https://en.wikipedia.org/wiki/Usage_share_of_operating_systems#Desktop_and_laptop_computers) of Windows machines on Desktop and Laptop computers to be more than 65%. This number has been coming slighly down in recent years, with the rise of Linux in gaming and increasing fatigue with Windows as an OS.

The [steam hardware survey](https://store.steampowered.com/hwsurvey) might be better indication of where these percentages sit, especially within the gaming community. It is 94% for Windows at the time of writing this. This is unsurpising as a lot of live-service games and games that rely on Kernel-level anticheat are Windows-only. 

There are a few games that I play which use Kernel-level anticheat software, so I have decided on a dual-boot approach to my problem of using Windows. I have decided to purchase a second Nvme drive, and I will boot Linux on that new drive. I decided to install grub and use this as my primary boot manager. I have prioritised the booting into my Manjaro OS unless I intervene with the boot selector at statup. This will enourage me to use the OS more often. 

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/blog/boot-selector.jpeg" title="GRUB boot selector menu" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    The GRUB boot selection menu. I'm using Manjaro as the default.
</div>

There were a few issues with doing this, which I resolved quite quickly. I noticed that Windows kept directly into itself after shutdown/restart. I saw that there was an option embedded within 'Power Options' and the advanced menu which needed to be changed to prevent this from happening. 

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/blog/fast-boot.jpeg" title="Option in Windows 11 power options: Fast boot" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    The marked option was selected by default, which forced Windows to boot directly after shutdown/restart, despite GRUB being installed correctly.
</div>

I've been using this set up for a few months now and I have really come to like it. I've been slowly shifting normal computing tasks and my light gaming over to my Linux OS, and I've kept my gaming on Kernel-level anti cheat games on my windows machine only. The only downside to this, is if I am in Linux for example and I wish to play Legaue of Legends, i have to reboot my machine to boot into Windows to do this. Bummer, but at least the OSes are physically and logically seperated, so not even a Windows update will break my set up, in theory. Yes, I have seen reddit posts about people's boot order being changed after an update (to make Windows the primary OS), despite having multiple OSes on different drives.

In other news, I've been Fedora with KDE Plasma on my thinkpad for around 6 months at this point, having used Linux Mint for several years. I grew tired of Cinnamon as a DE and this is a well needed upgrade. Almost every piece of hardware on this device worked perfectly out of the box and I am really happy with the switch. The DE is clean and highly customisable, which I really appreciate. I have a feeling that Fedora with KDE will be my go to OS moving forward. 

All in all, I think that this was a good swtich to my workflow, despite the cost needed for a new Nvme drive. It's a step in the right direction, so I can reduce my reliance on proprietary software like Windows. 