---
title: "CAN API"
date: 2026-05-01
description: "Refactored legacy CAN API (C, Bazel) to transition from 8-bit AVR to 32-bit ARM architecture (STM32)."
summary: "Refactored legacy CAN API (C, Bazel) to transition from 8-bit AVR to 32-bit ARM architecture (STM32)."
categories: ["FSAE"]
tags: ["Firmware", "Embedded C", "Python"]
featureimage: "images/can-1.png"
aliases:
  - "/can"
---

## At a glance

_Skills: Embedded C, Python, YAML, Jinja2, STM32_

* **What:** Refactored legacy CAN API (C, Bazel) to transition from 8-bit AVR to 32-bit ARM architecture (STM32). CAN API generates send/receive functions for CAN messages and builds a DBC file for our CAN bus.
* **How:** Replaced previous memory-mapped registers with STM32 HAL for CAN peripheral configuration and control. Used Jinja2 templates to convert readable YAML description files into CAN send/receive functions.
* **Why:** Eliminates repetitive and error-prone individual CAN implementations and supports team-wide transition to STM32.

---

## Details

![CAN API Software Diagram](images/can-1.png)
_CAN API Software Diagram_

Several years ago, Olin Electric Motorsports developed a custom CAN API for use in the team's development of firmware for custom PCBs designed by our team. The project aims to provide a standardized and organized way for individual nodes in our CAN network to interact with each other. The library centralizes interactions with the CAN peripheral on the microcontroller to one place to avoid repetitive and error-prone code across our repository.

The CAN API does the following:

1. A DBC file can be generated from the individual YAML files
2. All message collisions are detected at compile-time
3. A .c and .h file are generated for each YAML file that include send and receive functions for each of the messages sent and received by the MCU as specified by the YAML file

This year, our team decided to undergo a complete transition to a STM32 microcontroller architecture, replacing the ATmega16M1, which (as far as I can tell) we have used since the team was founded. In spring of 2026, I took on the complete rebuild of the CAN API from the ground up, replacing memory-mapped registers with STM32 HAL for greater readability and maintainability. 

---

## Resources

{{< youtube PU33wApXG5s >}}

{{< youtube b5lodbnx-aE >}}

[View source on GitHub](https://github.com/olin-electric-motorsports/oem-monorepo/tree/main/common/can_api)