---
layout: page
title: Power Distribution Unit Firmware (Formula SAE Electric)
---

January 2025 - May 2025

## At a glance

_Skills: C, SPI, CAN bus, reading datasheets, SMT soldering_

**What:** Created firmware for the power distribution unit, a board that manages low voltage power on Olin College's Formula SAE Electric vehicle.

**How:** Developed C code from scratch to create hardware timers, send and receive CAN messages, read ADC inputs, control a 7-segment display, and interface with an IO expander via SPI.

**Why:** Enables team to instantly view vehicle status through visual indicators (LEDs and 7-segment display), allowing the team to identify and address issues faster. The firmware also controls the cooling loop, keeping electrical components at a safe operating temperature.

## Details

![Empty Power Distribution Board]({{site.url}}/assets/images/pdu-1.jpg)
_Power Distribution Unit (PDU) board before populating and soldering components_

<p> In my second semester at Olin College, I continued as an Integration Engineer on <a href="https://www.instagram.com/olinelectricmotorsports/" target="_blank">Olin Electric Motorsports</a>. This semester, I developed C firmware for the vehicle's Power Distribution Unit (PDU).</p>

The PDU is responsible for managing power for the vehicle's low voltage system, visually communicating the status of the car, and controlling the cooling loop. The PCB was designed by another engineer, so I was tasked with populating and soldering all electrical components, and writing C firmware for the ATmega16M1 microcontroller.

![Populated Power Distribution Board]({{site.url}}/assets/images/pdu-2.jpg)
_Power Distribution Unit (PDU) board after populating and soldering components (plus a big dog!)_

To be specific, my firmware had to accomplish the following tasks:

- Send and receive messages on the vehicle's CAN bus.
- Communicate (via SPI) with an IO expander IC to control LED status lights
- Communicate (via SPI) with an analog to digital converter (ADC) IC to measure current draw across vehicle
- Communicate (via SPI) with a display driver IC to show voltage of high voltage system on a 7-segment display
- Control the indicator light for the high voltage system
- Manage the cooling loop by powering the fan and controlling the coolant pump with PWM

![Whiteboard sketch of Power Distribution Board]({{site.url}}/assets/images/pdu-3.webp)
_Early whiteboard diagram of Power Distribution Unit (PDU) functions and layout_

This project was equally challenging and rewarding. A number of factors made this project difficult:

- The PDU project was brand new to our team, meaning that I had design all code from the ground up. Without any existing code to build off of, I had to read through the (very long!) technical datasheets to understand how to interface with the ICs on the board.
- With over 50 unique electrical components in the bill of materials, this was the largest board our team had ever produced, in terms of both physical size and number of parts. Populating and soldering all the components was time-consuming, but provided lots of SMT soldering practice! I also learned to use an oscilloscope to identify and isolate bugs in the system.
- This was my first time writing code in C, which meant I had to learn the C syntax, bitwise operations, and memory management principles as I went. Only having 3 months before the vehicle would compete in the national competition forced me to learn quickly!

Overall, I am satisfied with how the final product turned out. Our electrical system (including the PDU) passed electrical inspection at competition, certifying that we had met all rules requirements. Some of the board's functions that communicate vehicle status require further refinement and de-bugging, but as a whole, the firmware allows the vehicle to drive safely and reliably. This project developed my skills in firmware design with C, SMT Soldering, reading technical datasheets, and de-bugging electrical systems.

## Resources

<p><a href="https://miro.com/app/board/uXjVIaUf1E4=/" target="_blank">Digital Whiteboard</a> of PDU system</p>
<p><a href="https://github.com/olin-electric-motorsports/olin-electric-motorsports/tree/jacobkeller/pdu_firmware/vehicle/mkvii/software/pdu" target="_blank"> GitHub Source Code </a></p>

[<--- Return home]({{site.url}})
