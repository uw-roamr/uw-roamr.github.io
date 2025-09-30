---
layout: post
title: Nathan's Brainstorming
date: 2025-09-29 21:30:00
description: Individual Work
tags:
categories: 
featured: false
---

<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/systemdiagram.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

## Brain Storm
**Wheeled Configuration:**

| Feature | Geared DC Motor | BLDC Motor |
|---------|-----------------|------------|
| **Pros** | High Torque<br>Affordable<br>Easy to control | Long lifespan<br>High RPM<br>Highly efficient |
| **Cons** | Short lifespan<br>Low RPM<br>Low Efficiency | Expensive<br>Requires ESC |

* I believe we should use a geared DC motor for the wheeled configuration because it meets system specs at the most affordable price.
* Use an external encoder for closed loop feedback.
    * Input: Shaft position
    * Output: PWM duty cycle

<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/nathan_roughsketch.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>


**Legged Configuration:**
* Fundamentally different motor architecture
* A quadruped requires more motors, and each requires higher rated torque than wheeled configuration.
* Makes more sense to use servos since they're affordable, have built in angle feedback, and are easier to integrate
* I propose design that the wheeled configuration be the base version, with an additional legged motor controller board that can be plugged in
* The legged motor controller board will have the motor drivers necessary to the servos.