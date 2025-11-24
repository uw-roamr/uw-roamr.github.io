---
layout: post
title: Basic mapping and localization
date: 2025-11-03 14:40:00
description: Basic mapping and localization by Kai
tags: 
categories: 
featured: false
---

To validate our software architecture, Kai built a basic "mapping and localization" demonstration.

To recap, we are aiming to use minimize the need for users to do development in Swift/XCode and allow them to write code in C++, which is then compiled to WASM to run on the phone. To this end, we put together a basic demo with WASMKit.

[Video demo](https://www.youtube.com/watch?v=bPDcQqSxsOI)


<div class="row justify-content-center mt-3">
    <div class="col-sm-8 col-md-10">
        {% include figure.html path="assets/img/mapandloc.png" class="img-fluid rounded z-depth-1 w-100" %}
        <div class="caption text-center mt-2">
            Mapping and localization idea
        </div>
    </div>
</div>

In this demo, the sensor reading for LiDAR and IMU pose is done from Swift. Point cloud and pose information is then written to map form using a C++ backend (compiled to WASM). 

