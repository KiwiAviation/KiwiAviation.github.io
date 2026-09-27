---
title: "Bare-Metal Bicycle Safety Light"
date: 2026-09-01
description: "Developed bare-metal embedded C firmware for STM32 to sequence through a finite state machine of lighting modes."
summary: "Developed bare-metal embedded C firmware for STM32 to sequence through a finite state machine of lighting modes."
categories: ["School Project"]
tags: ["Firmware", "Embedded C"]
featureimage: "images/bike-1.avif"
aliases:
  - "/bike"
  - "/projects/bicycle_safety_light"
---

## At a glance

_Skills: Bare-Metal C, STM32, Interrupts_

* **What:** Developed bare-metal embedded C firmware for STM32 to sequence through a finite state machine of lighting modes.
* **How:** Configured hardware and timer interrupts via memory-mapped registers for interrupt-driven state transitions.
* **Why:** Bare-metal programming shows exactly abstraction layers do "under the hood". This project also forced me to become very familiar navigating the documentation for the STM32G4.

---

## Details

![NUCLEO-F446RE development board used in this project](images/bike-1.avif)
_NUCLEO-F446RE development board used in this project_

This project is part of the Embedded Software course I took in Fall 2026. For this project, we were tasked with creating a bicycle safety light prototype using a Nucleo development board with an onboard STM32F446RE. 

Typically, an engineer would start by using the CubeMX software to configure the hardware, then implement the state machine and transition logic using ST's pre-packaged Hardware Abstraction Library (HAL). While this approach is the most efficient, it is important for engineers to understand what HAL does behind the scenes and peel back the layers of abstraction, since not all microcontrollers will have a robust HAL. To this end, one requirement for this project was to implement this functionality entirely in bare-metal C, through direct manipulation of memory-mapped registers.

To accomplish this, it required me to spend time learning how to use the documentation, including the reference manual, user manual, programming manual, datasheet, and Nucleo schematic. Building the hardware and timer-based interrupts from scratch was an interesting challenge, as it required finding and configuring the correct values for the RCC, GPIO, EXTI, NVIC, and TIM peripherals. 

The final project cycles through three distinct modes at the press of the onboard button (falling-edge interrupt):
1. Off
2. Solid
3. Blink (4Hz)

---

## Resources

[GitHub Link](https://github.com/KiwiAviation/bicycle_safety_light)

YouTube demonstration:

{{< youtube afLDy9tN0Yk >}}