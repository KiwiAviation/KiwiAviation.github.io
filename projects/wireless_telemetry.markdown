---
layout: page
title: Wireless Telemetry (Formula SAE Electric)
---

August 2024 - December 2024

## At a glance

_Skills: Python, CAN bus, serial (UART), radio frequency (RF) technology_

**What:** Designed software to enable wireless telemetry for Olin College's Formula SAE Electric vehicle.

**How:** Wrote Python code on vehicle's onboard RaspberryPi computer to serialize messages from the CAN bus and transmit to a ground station via UART radios.

**Why:** Enabled wireless telemetry for the first time in team history, allowing for real-time vehicle diagnostics while the vehicle is in motion.

## Details

![Radios used: Holybro SiK Telemetry Radio V3]({{site.url}}/assets/images/rft-.jpg)
_Radios used: Holybro SiK Telemetry Radio V3_

<p> In my first semester at Olin College, I joined <a href="https://www.instagram.com/olinelectricmotorsports/" target="_blank">Olin Electric Motorsports</a>, a team of undergraduate engineers designing, building, and racing an electric race car for the Formula SAE Electric competition.</p>

As part of the Integration sub-team, wireless telemetry was the first project I was assigned. This project had been attempted several times before on the team, but never made it on the vehicle since it was not mission-critical. The goal of the project is to allow the car to communicate with a computer-based ground station wirelessly. This enables real-time vehicle diagnostics while the car is driving, allowing the team to diagnose and resolve drive-time issues.

![Flowchart of telemetry system]({{site.url}}/assets/images/rft-2.jpg)
_Flowchart of telemetry system_

The team had already purchased USB UART radios, so it was my job to implement the necessary software. I developed Python code for both the vehicle's onboard computer (a RaspberryPi) and the laptop ground station.

The software on the car reads all messages that are sent on the CAN bus, converts the message into a serial object for transmission, then sends the message via serial to the UART radio for transmission. The software uses Python's _pickle_ library for serialization.

The software on the ground station runs within our team's existing CAN viewer app, so that the same app can be used for both wired and wireless diagnostics. The software reads serial data from the UART radio, deserializes the message, decodes the CAN message, and displays the message in our visual CAN dashboard.

![Olin Electric Motorsports MkVII vehicle]({{site.url}}/assets/images/rft-3.png)
_MkVII, built by Olin Electric Motorsports in the 2024-2025 academic year_

In my second semester at Olin Electric Motorsports, I focused on developing firmware for the power distribution unit, which you can read about [here]({{site.url}}/projects/pdu_firmware).

## Resources

<p><a href="https://coda.io/d/_dLTyp9cQyXS/RF-Telemetry-System_suVogLCA" target="_blank">Full documentation</a></p>

[Return home]({{site.url}})
