---
layout: post
title: Reflections on PCB bringup
date: 2026-02-22 20:02:00
description: PCBA bringup post-mortem
tags:
categories: 
featured: false
---
We have finally finished bringup of both PCBs and have a lot of learnings to take away.

### Power Board

Issues:

- TVS diode on the 12V battery input side was flipped anode/cathode, meaning that upon plugin the input voltage was being driven low (i.e. 12V rail was consistently reading ~0.7V). Nathan and Olivia identified this as a schematic/part selection mistake (long story short, schematic symbol was bidirectional but the chosen part was unidirectional, meaning the pins were wrong). **Solution**: replaced the unidirectional diode with a bidirectional one we had extra of from the motor board.
- PFET for the fault indication of the USB-C output current limiter IC was drain/source flipped, so it turns on incorrectly (turns on when there isn't a fault). **Solution**: The component has since been depopulated since it isn't necessary.
- The current limiter IC is showing a weird latching behaviour, where if we switch the USB-C output to "on", the phone will start charging, but when we switch the charging to off, the phone continues charging. Olivia thinks this is because the enable pin is put in a high-z state when switched off instead of pulled down to ground, so it's not decisively being turned off. **Solution**: we stopped debugging since this is not top priority and moved on. Olivia predicts the solution to be putting a pull-down resistor between the enable/fault pins and GND.

Wins:

- 12v to 5v buck no issues

Conclusion: 

Power board is reliable for 12V and 5V. Won't investigate the charging latching issue for now. Debugging finished for now. Power board is usable 👍 

### Motor Board

Issues:

- When we first powered the board on, the motor drivers weren't responding to SPI. Nathan and Olivia found that the nSLEEP pin on the driver was left floating (not connected) but actually needs to be pulled up to logic high else the driver is in permanent sleep mode. **Solution**: We tied nSLEEP to the VSYS_3v3 rail woke the driver up. Driver is now responding to SPI status requests.
- The driver is reporting a hardware fault through the nNFAULT pin and BUCK status fault when queried with SPI. We debugged this to be an electrical issue since the built-in-buck pins were left floating on the driver when they should've been tied to RC even if unused; however, we should be able to tell the driver through SPI to disable the buck, which should clear this fault. However, the driver is NOT responding to SPI write but IS responding to SPI read (we are able to get status requests). As a result, we aren't able to drive the motors because:
   a. We can't set the correct PWM mode (mode3) - this is done through a SPI write command. This means that the esp32 pwm signals to the driver AREN'T being read correctly.
   b. We can't clear the buck fault since we can't disable the buck through SPI (uncleear if this is actually a gating fault to getting the motors to spin).
   **Solution**: We needed to set a specific SPI condition before clearing faults and setting the PWM mode. This ensured that the fault state wouldn't reset and would stick to being "unfaulted".

Wins:

- USB-UART bridge works perfectly, we able to talk from computer <-> ESP32 with no issues
- 5V to 3V3 LDO has no issues
- SPI communication between motor encoders <-> ESP32 has no issues
- We are able to flash basic bluetooth demo to the board and communicate ESP32 <-> phone through BLE using the NRFconnect app with no issues
- ESP32 able to output PWM using the FOC library on the correct pins

Conclusion: 

Motor board is able to drive the motors and communicate with the phone. The motor board is usable 👍 