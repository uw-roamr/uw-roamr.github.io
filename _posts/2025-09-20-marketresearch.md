---
layout: post
title: Market Research
date: 2025-09-20 14:52:00
description: Market research of existing products
tags:
categories: 
featured: false
---

| Product                                                                                                                                    | Notes                                                                   | Audience      | Price (CAD, official)                 | Hardware/Sensing                                                                                                                                                              | Programming                                                                     | Open-Source                                           |
| ------------------------------------------------------------------------------------------------------------------------------------------ | ----------------------------------------------------------------------- | ------------- | ------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- | ----------------------------------------------------- |
| [LEGO Education SPIK Prime](https://www.lego.com/en-ca/product/lego-education-spike-prime-set-45678)                                       | - Successor to Mindstorms<br>- Additional expansion kits<br>            | Grade 6-8     | $600                                  | - Sensors: Force, color/light, ultrasound ([see here](https://community.legoeducation.com/blogs/31/220))<br>- 2 small motors, 1 larger motor<br>- Proprietary programming hbu | Scratch-based blocks, Python                                                    | No                                                    |
| [Turtlebot4](https://ca.robotshop.com/products/clearpath-robotics-turtlebot-4-mobile-robot?qd=53f3de7248c438846d16649e6ce3d2e6)            | - Essentially iRobot Create 3 + sensors                                 | University/HS | $3142                                 | - Sensors: Oak-D-Pro Camera, RPLidar A1M8, IR cliff sensors, IR obstacle sensors, gyroscope, IMU, encoders<br>- Raspberry Pi 4                                                | ROS 2 (Python, C++), comes with Gazebo sim                                      | Yes, but not great                                    |
| [TurtleBot 4 Lite](https://ca.robotshop.com/products/clearpath-robotics-turtlebot-4-lite-mobile-robot?qd=53f3de7248c438846d16649e6ce3d2e6) | - Essentially iRobot Create 3 + sensors<br>- Fewer ports, no screen     | University/HS | $1910                                 | - Sensors: Oak-D-Lite Camera, RPLidar A1M8, IR cliff sensors, IR obstacle sensors, gyroscope, IMU, encoders<br>- Raspberry Pi 4                                               | ROS 2 (Python, C++), comes with Gazebo sim                                      | Yes, but not great                                    |
| [Bracket Bot](https://www.bracket.bot/)                                                                                                    | - Upright<br>- Tron 2025 capstone → startup (?)<br>- 3 hour set-up time | University/HS | $600                                  | - Sensors: Not included??<br>- Hoverboard motors<br>- Raspberry Pi 5                                                                                                          | Python                                                                          | Yes                                                   |
| [OpenBot](https://arxiv.org/pdf/2008.10631)                                                                                                | - Interesting policy training experiments in paper                      | University/HS | Android phone + $70                   | - Phone sensors + speed sensor, sonar sensor                                                                                                                                  | Some sort of android platform<br>- Focus on learning-based methods with TF Lite | Yes ([ob-f/OpenBot](https://github.com/ob-f/OpenBot)) |
| [JetBot](https://jetbot.org/master/)                                                                                                       | - Jetson Nanos are hard to get                                          | University/HS | $350, but assumes $99 USD Jetson Nano | - Options for camera (Leopard imaging camera, IMX219-160, RPi Camera)                                                                                                         | JetBot web programming environment (Jupyter-like), Jetbot API                   | Yes                                                   |


<br><br><br>
From OpenBot paper:
<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/openbot_research.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Comparison of wheeled robotic platforms from OpenBot paper.
</div>

Testimonials/Articles:
- (Anecdotal from Kai) On exchange term at HKUST, the school only had five Turtlebots, so the AMR class had to create many lab sections and make groups with large amounts of people.
- [Why ROS, wherefore base? (A cost/benefit analysis request) - GoPiGo - Modular Robotics Forum](https://forum.dexterindustries.com/t/why-ros-wherefore-base-a-cost-benefit-analysis-request/9123/9): "Giant void in the educational ROS platform market", TurtleBot is state-of-the-art for ROS-based solution (good ecosystem) but too expensive
- [Barriers and Facilitators of Robot-Assisted Education in Higher Education: A Systematic Mixed-Studies Review](https://link.springer.com/article/10.1007/s10758-022-09637-3): Hardware and software issues (cost, limitations, maintenance) are among the barriers to deploying robots in higher education
- [Educational Robot Market Size, Share & Growth Report, 2031](https://www.alliedmarketresearch.com/educational-robot-market-A31331): "The high costs associated with educational robots are one of the prime factors that restrain the educational robot market outlook"
- [The Design and Implementation of a Cost-effective Educational Robotics Platform for affordable ROS Based Mechatronics and Robotics Labs](https://juniperpublishers.com/raej/pdf/RAEJ.MS.ID.555677.pdf): “Affordable robots with poor quality” vs “highly capable platforms that are prohibitively expensive.”
- [Tiny Robot Learning: Challenges and Directions for Machine Learning in Resource-Constrained Robots](https://arxiv.org/abs/2205.05748): Low-cost robots are constrained by SWAP (size, weight, area, power) and limited sensors/compute