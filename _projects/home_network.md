---
layout: page
title: home network upgrade and lab
description: I bought a new place. Naturally I had to kit it out with overkill networking. 
img: assets/img/projects/homenetwork/rack-closeup.jpg
redirect: false
importance: 3
category: fun
---

So I've recently done an adult thing and I've bought my first house. Go me. I decided that I want a well-connected household with gigabit internet. 

Luckily, I moved to a place which has it already rolled out. All it took was me selcting a provider that buult out Fibre to the Home (FTTH), and I would be off to the races. After selecting my provider I was yearning for an update to my home network. 

Before the move, my home netowrk was very simple setup of my ISP-provided router in bridging mode, connected to a pfSense box. My local internal network consisted of a Synology NAS device from around 2011, my Wifi AP, and my gaming PC. The NAS had a single-core 1.2 GHz processor, 256 MB of RAM, two internal 3.5 inch bays, each with maximum capacity of 3TB for a total of 6TB of storage. I chose to run it in RAID 1 (Disk mirroring). 

When building out my network I decided on a few key philosophies that I wanted to stick to during the build and deployment:

1. The network setup, topology and ongoing maintenence are to be as stressfree and simple as possible.
2. The hardware should be as quiet as possible and needs to fit inside te cupboard underneath the stairs for maximum stealth.


I also wanted to 
3. A redesign of my storage solution was needed with full parity built in. This needs to for



Network diagram

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/projects/homenetwork/network-diagram.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    A simplfied network diagram.
</div>



<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/projects/homenetwork/rack-closeup.jpg" title="Close up of server rack" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/projects/homenetwork/rack-power_comms.jpg" title="How the rack is set up from the wall" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    <b>Left:</b> A close up of the bits I have in my rack at the moment. <b>Right:</b> How the ONT and ethernet runs are set up.
</div>


<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/projects/homenetwork/rack-inposition.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    This is her in position. Isn't she a beauty?
</div>



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
