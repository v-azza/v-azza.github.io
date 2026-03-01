---
layout: page
title: home network upgrade and lab
description: I bought a new place. Naturally I had to kit it out with overkill networking. 
img: assets/img/projects/homenetwork/rack-closeup.jpg
redirect: false
importance: 3
category: fun
---

So I've recently done an adult thing and I've bought my first house. Go me. I decided that I want a well-connected household with gigabit internet. I also decided that I wanted a complete revamp of my home network, with all the bells and whistles of a homelab.

Before the move, my home netowrk was very simple setup of my ISP-provided router in bridging mode, connected to a pfSense box. My local internal network consisted of a Synology NAS device from around 2011, my Wifi AP, and my gaming PC. The NAS had a single-core 1.2 GHz processor, 256 MB of RAM, two internal 3.5 inch bays, each with maximum capacity of 3TB for a total of 6TB of storage. I chose to run it in RAID 1 (Disk mirroring). 

Luckily, I moved to a place which has it already rolled out. All it took was me selecting a provider that buult out Fibre to the Home (FTTH), and I would be off to the races. After selecting my provider I was yearning for an update to my home network. 

Then came another interesting debacle: Where shoud I put all the hardware? There were a few candidates, ranging from all levels of difficulty - but I ended up selecting the cupboard underneath the stairs. There were no power sockets here, so I ended up hiring a qualified electrican to add some sockets there. Once done, I ensured that the ONT installation for my Fibre line terminated in that same place. I also paid a professional company to add CAT6 ethernet runs to all the bedrooms and the living room.

When building out my network I decided on a few key philosophies that I wanted to stick to during design, build and deployment:

1. The network setup, topology and ongoing maintenence are to be as stressfree and simple as possible.
2. The hardware should be as quiet as possible and needs to fit inside the cupboard underneath the stairs for maximum stealth.
3. Power consumption should be kept to a minimum.
4. If I need to move the hardware to a different location, or remove and disconnect everything for whatever reason: I can do so with very little effort. 
5. The hardware selected needs to become more modular. I've grown tired of a mass of boxes and wires.

During this home network revamp - I wanted to get some quick wins/improvements:
1. A redesign of my storage solution was needed with parity, error checking and RAID built-in. This needs to be a permanent change, and certain file storage connection protocols needs to be supported out-of-the-box, such as SMB and NFS. This will become my primary backup provider. 
2. I wanted to onboard a device that can allow me to spin up and spin down VMs and Docker containers quickly and easily. This can give me some labbing potential, should I need to use it.


Regarding parts selection, I found that I had several PC parts lying around and I decided to repurpose these, for use in my network. I selected a gateway device that could run pfSense, as I am familiar with the software and I am confident enough to administer it well and securely. 

With this in mind, I started by designing everything else. I found that I can hit philosophy point #1 and both my quick wins in network redesign, by having a dedicated machine running an OS that can serve as my storage server, but has VM and docker capabilties. I researched a lot of OSes and ways of doing this cleanly until I came across [Unraid](https://unraid.net/). It seemed to hit every requirement I needed, and there was only a one off licensing fee to use the software for life. There is ample doucmentaiton and online resources for it, and a massive online community using the tool. Unfortunately it is closed source and not FOSS. I decided to select this for my network.

I drew up a quick network diagram, to see how it would all fit together and this helped me design the interfaces and networks I intended to use for everything. I find that drawing everything out helped me connect things correctly first time with little to no troubleshooting.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/projects/homenetwork/network-diagram.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    A simplfied network diagram.
</div>

Then I took the plunge. The point of no return. The moment that all homelabbers remmeber dearly. I decided to buy a server rack. 

I decided to get a [Startech 15U Open Frame Server Rack](https://www.startech.com/en-gb/server-management/4postrack15u). It included some casters (wheels) which I really appreciated. It was a great purchase and I think that it will last me for a very long time - and I have ample space to build out my estate should I choose to. Given that I decided to repurpose my desktop PC components and PC case, I kitted it out with a high-strength support base for the lowermost rack slot so I can my PC case on the bottom of the rack. Have a look at later pictures if you need to see what I mean. If I choose to get a UPS with heavy batteries, this shelf should be more than enough to handle that. This selection hits my philosophy points #2, #4 and #5 quite nicely. 

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/projects/homenetwork/rack-closeup.jpg" title="Close up of server rack" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/projects/homenetwork/rack-power_comms0.jpg" title="How the rack is set up from the wall" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    <b>Left:</b> A close up of the bits I have in my rack at the moment. <b>Right:</b> How the ONT and ethernet runs are set up.
</div>

I purchased an old PoE Netgear switch from Ebay that's long out of service. I stuck that in, and it helped me wire everything (including the ethernet runs) up. In the future I will use it to add some security cameras about the house.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/projects/homenetwork/rack-inposition.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    This is her in position. Isn't she a beauty?
</div>


In the future, I want to:

1. Get a server mounting kit for ATX PCs so that instead of a large PC case sitting at the bottom of the rack, I can have the computer bits slot into the rack instead. 
2. I want to see if there are any FOSS alternatives to Unraid that just works well out of the box, and is as feature-rich - but I am not there yet. 
3. Add a home security network, and use a running VM as a NVR server to control all the cameras. It should be straight forward to wire via. PoE connections.



To give your project a background in the portfolio page, just add the img tag to the front matter like so:

    ---
    layout: page
    title: project
    description: a project with a background image
    img: /assets/img/12.jpg
    ---



<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/projects/homenetwork/rack-power_comms.jpg" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/projects/homenetwork/rack-stairs.jpg" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>
</div>
<div class="caption">
    <b>Left:</b> Set up.
    <br><br>
    <b>Right:</b> Where I put it.
</div>




<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/1.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/3.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/5.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Caption photos easily. On the left, a road goes through a tunnel. Middle, leaves artistically fall in a hipster photoshoot. Right, in another hipster photoshoot, a lumberjack grasps a handful of pine needles.
</div>

You can also put regular text between your rows of images.
Say you wanted to write a little bit about your project before you posted the rest of the images.
You describe how you toiled, sweated, _bled_ for your project, and then... you reveal its glory in the next row of images.



The code is simple.
Just wrap your images with `<div class="col-sm">` and place them inside `<div class="row">` (read more about the <a href="https://getbootstrap.com/docs/4.4/layout/grid/">Bootstrap Grid</a> system).
To make images responsive, add `img-fluid` class to each; for rounded corners and shadows use `rounded` and `z-depth-1` classes.
Here's the code for the last row of images above:

{% raw %}

```html
<div class="row justify-content-sm-center">
  <div class="col-sm-8 mt-3 mt-md-0">
    {% include figure.liquid path="assets/img/6.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
  </div>
  <div class="col-sm-4 mt-3 mt-md-0">
    {% include figure.liquid path="assets/img/11.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
  </div>
</div>
```

{% endraw %}
