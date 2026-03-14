---
layout: page
title: software
permalink: /software/
nav: software
nav_order: 4
---

 **Software:** roamr’s software architecture is designed to make autonomous robot development accessible, cross-platform, and easy to use. Rather than requiring developers to build directly for iOS, user autonomy code is written in any WASM-compatible language and compiled into a WebAssembly module that runs safely inside the iPhone app. The roamr app provides the WASM runtime with sensor data from the cameras, LiDAR, IMU, and GPS, receives drive commands in return, and forwards those commands to the motor microcontroller over Bluetooth Low Energy (BLE), enabling efficient low-power onboard control. For monitoring and teleoperation, the phone also connects to a web-based interface over Wi-Fi using websockets, allowing bidirectional streaming of commands, video, and telemetry. Together, this architecture leverages the iPhone’s built-in sensing and compute while keeping the system low-cost, extensible, and accessible to developers without requiring macOS or native mobile app expertise.

<div class="row justify-content-center mt-3">
    <div class="col-auto">
        {% include figure.html path="assets/img/sw-arch.png" class="img-fluid rounded z-depth-1" style="max-width:700px;" %}
    </div>
</div>
<div class="caption text-center" style="font-size: 0.95em;">
    roamr software architecture.
</div>