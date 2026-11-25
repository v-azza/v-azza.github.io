---
layout: post
title: offsite backup and disaster recovery
date: 2026-11-10 21:00:00
description: I realised that my storage server didn't really have any geographical redudancy built in. Luckily I had a NAS running Linux that I could use to help me.
tags: linux software hardware tips
#categories: sample-posts
---

At this point, I have had a storage server running on my home netowork for a few years now, with a decent amount of capability. Not only does it give me a place to put all of my old pictures and memerories, it runs my docker containers and my VMs. I then realised that my storagge server is in need of a decent backup solution. 

Then began the phase of thinking about how to approch this backup problem. I wanted proper redudancy without hvaing to pay a company or seervice to give this to me. Ideally, I wanted to leverage what tech I already have. This immedately removed the possbility of using cloud backup solutions such as [Backblaze](https://www.backblaze.com) and [Datacore](https://www.datacore.com/). 

I then considered what was in my tech stack at the moment, and what tech I've retired. My homelab infrastructure is documented in my [Home Network project](/projects/home_network/), which covers my network architecture, hardware and configuration. It has changed somewhat since the writing of the post, but the foundation, purpose and premise remains the same. I knew my production storage storage sevrer has replaced my old Synology DS212j NAS device pictured below.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/blog/synology-ds212j.jpg" title="A Synology DS212j NAS device" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    An example of a Synology DS212j. This particular device was my backup solution, prior to the build and deployment of my storage server.
</div>

This device was pretty low perforance at the best of times, and it didn't have the capability I was looking for. However, for a low cost and efficent storage device for backups only - this seems to be a good choice for my needs. 

Then I needed to consider redudancy. I am not a major cloud provider, nor am I hosting business critical workloads. However, the data itself is highly valuable to me. Despite being so valuable to outsiders, the personal cost of complete data loss would be immense. Therefore, I decided to impliment geo-redudancy into my backup plan. This meant I had to deploy this device somewhere physically located elsewhere. This covered me for cases of fire or theft at the primary site, for example. 

So I did what any tecchie does when they need off-site storage capability, without relying on cloud: I called my parents. 

They were happy to help but had concerns about power. After explaining to them that this device will consume only about £23 of electricity a year - they were happy to oblige. 

Then I needed to undestand how I would design the control plane and the backup locations. I decided on [Backrest](https://github.com/garethgeorge/backrest) which provides a clean UI built on Restic, and an easy to use control plane for these backups to operate.  

Connectivity was established using Tailscale, with SSH/SFTP providing secure repository access. Initial backups experienced intermittent SSH disconnections, broken pipes, and repository locking issues. Troubleshooting included verifying SSH authentication, testing SFTP connectivity, examining Tailscale DERP versus direct connections, and configuring a Hybrid Outbound NAT rule on my firewall to preserve UDP source ports for the Unraid server (192.168.100.10). 

Stale Restic locks were cleared after confirming no backup processes remained active. Both backup plans, the secure repo (35.03 GiB) and the main backup repo (1,009.15 GiB), eventually completed successfully. The larger backup took approximately 3 days and 16 hours, processing 219,480 files and adding 620.44 GiB to the repository. A single-file recovery was also tested successfully, confirming that backed-up data could be retrieved and matched against the original.

I subsequently established a consistent backup schedule, with the secure repo running every Saturday at 02:00 (0 2 * * 6) and the main backup repo every Sunday at 02:00 (0 2 * * 0). Both plans use a retention policy of four weekly, twelve monthly, two yearly, and three latest snapshots. 

I found that a test restore produced errors, which was because the Backrest container timezone was  misaligned. It was corrected from America/Toronto to Europe/London, ensuring schedules account for GMT/BST changes. I found that the ds212j was running some flavour of Linux, so I was able to diagnose and fix very quickly. 

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/blog/backrest-prod.png" title="Screenshot of the Backrest dashboard" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    This is backrest running in production. I've decided to call it 'Mnemosyne'.
</div>

An incremental backup of the secure share completed successfully in just 3 minutes and 16 seconds.

Once an inccremental backup was proven over 2 cycles, I considered this backup solution finished. Both backup plans and the repository now show healthy status indicators. 

The remaining work is to finalise my own purpose-built the disaster recovery playbook, and conduct a full recovery exercise.