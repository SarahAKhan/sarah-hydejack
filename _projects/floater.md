---
layout:      project
title:       Floater
date:        2024-06-01
image:
  path:       /assets/img/projects/floater/floater_3imgs_1920w.png
  srcset:
    1920w:   /assets/img/projects/floater/floater_3imgs_1920w.png
    960w:    /assets/img/projects/floater/floater_3imgs@0,5x.png
    480w:    /assets/img/projects/floater/floater_3imgs@0,25x.png
full_width: true
caption:     Floatation device performing automated vertical profiles with temperature, depth, and pressure data collection and transmission.
description: >
  This floatation device was our team's submission for the MATE Floats task of the 2024 MATE ROV Competition.  It performs fully automated vertical profiles consisting of sensor temperature, depth, and pressure data collection, and subsequent transmission upon profile completion.  The data received on deck is automatically written to a csv file and plotted in the float device's controls GUI.
links:
  - title:   Live Demo
    url:     https://youtu.be/YV_wWue1qB8?si=MFaLaOyuOkbI08f6
featured:    false
---

## Floater
During the 2024 MATE ROV Competition, we successfully completed the Floater Task with our device at 15' depth.  I was the lead software developer for the device (in addition to being the Software Team Lead) and wrote the embedded software in C++ based Arduino for the Arduino Nano microcontroller and the Python based controls on the command station laptop.  The laptop relayed commands to the device via Bluetooth; the floater would conduct its vertical profiles, while collecting temperature, depth, and pressure sensor data, and upon completion transmit all collected data to the command station via Bluetooth.  The data would automatically write to a csv file and plot in a mutli-y-axis graph on the GUI.  

<div class="videoWrapper">
  <iframe width="560" height="315" 
    src="https://www.youtube.com/embed/YV_wWue1qB8?si=MFaLaOyuOkbI08f6" 
    frameborder="0" 
    allowfullscreen>
  </iframe>
</div>

![Image description](/assets/img/projects/floater/floater_interior_700w_600h.png){:.lead width="700" height="600"}

Floater interior design.
{:.figcaption}

## Implementation Details
The device emitted unique LED color patterns to convey internal state changes as it performed the vertical profile, as it loses Bluetooth connection once submerged in water.  The internal state machine consists of pumping water into the floater bladder on a timed interval, just until it begins to sink, then it automatically shuts off the pump and freefalls.  It registers when it has reached the bottom, sits there for an additional timed interval, and then begins pumping water out to return to the surface and automatically shuts the pump off when emptied.  Throught this profile, it is displaying different colors indicating these internal changes, as well as collecting temperature, depth, and pressure data.  

It transmits all of the collected data via Bluetooth to the command station laptop, which then gets written to a csv file and plotted on the GUI automatically. 

## Results
Our team was one of the few teams in the competition to collect all of the Float Task points.  It is a category in the MATE ROV Competition that is notoriously difficult due to the 15' depth and the stringent requirements at the more difficult competition level. 

## Features
- Automated vertical profile
- Embedded State Machine
- Bluetooth control and data transmission
- Automated data saving and plotting

## Technologies Used
- PyQt
- Arduino Nano
- Arduino Bluetooth Module
- RTC Clock
- Bluerobotics sensor

## Languages
- C++
- Python

## UML Diagram
![Image description](/assets/img/projects/floater/floater_stateMach_umlDiag_700w_533h.png){:.lead width="700" height="533"}

Arduino Nano embedded State Machine.
{:.figcaption}

## GUI
![Image description](/assets/img/projects/floater/floater_GUI_1136w_901h.png){:.lead width="800" height="635"}

Floater GUI
{:.figcaption}

Our team name was "The Vikings"; the pixelart graphic assets for the GUI were created using generative AI.  
