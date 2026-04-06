---
layout: post
title: Updating our wheels
date: 2026-02-11 17:30:00
description: Adding treads
tags:
categories: 
featured: false
---
As Kai and Thomason have been working on our autonomous navigation demo, they are running into some issues with the control of the robot. There is a small window for the nominal speed the robot should run at: too slow, and it can't overcome stiction, too fast, and the phone can't capture and process the sensor data quickly enough to develop a smooth map of the surroundings. With the old wheels, which were thin and used rubber bands for added traction, it was very difficult to control for this nominal speed.

Today, Anders and Olivia worked on updating the wheels. These new wheels will be wider, offering a larger contact surface with the ground, and also have treads. This should help the robot grip the ground better, and lower the speed required to overcome stiction.

<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/oldwheel.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    The old thin wheels with a hacky rubber band to try to add more traction.
</div>

<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/wheeltread.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    The new wheels designed which are wider, and also have built-in treads.
</div>

