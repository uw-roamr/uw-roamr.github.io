---
layout: post
title: New Electrical Design
date: 2027-01-12 12:30:00
description: New Electrical Design
tags:
categories: 
featured: false
---
Today, Thomason and Olivia came together to brainstorm the new electrical architecture, shifting away from OTS components to a custom designed PCB based on a modular design.

We decided to develop two PCBS - a power PCB that interfaces between the rest of the hardware and the battery, and the motor PCB, which will interface between the iPhone commands and the motors. With the exception of the power PCB, each subsequent PCB will have its own microcontroller, enabling a node-based approach to our goal of hardware extensibility.

<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/maze.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Inner and outer environment for the robot demo.
</div>