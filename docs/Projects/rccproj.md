---
title: RC Wifi Controller
tags: [case-study, embedded, esp32, pcb, schematic, LSE]
---

<div class="hero">
  <h1>RC Wifi Controller for Future projects</h1>
  <p class="lead">Custom ESP-32 RC/Wifi controller. Provides bluetooth and Wifi connectivity, ESD protection, and clean electrical interfaces like buttons, potentiometers, joysticks, and SPI and UART headers.</p>
  <div>
    <a class="hero-cta primary" href="../projects/">← Back to Projects</a>
    <a class="hero-cta ghost" href="../../subfolder/Mechatronic.pdf">Resume</a>
  </div>
</div>

---

## Overview

COMING SOON
---

## Objective

Create a **custom RC/WIFI Controller PCB** that:

- Hand-solderable, compact 4-layer board for prototyping
- USB programming and debugging via USB interface
- Wireless capabilities (BLE and Wifi)
- Accept battery or power from USB
- SPI and UART headers for sensors or actuators  
- Further technical and PCB skills

---

## Hardware Images

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 16px;">

<div>
  <h4>PCB Layout</h4>
  <img src="../RcConProj/PCBtopviewRC.png" alt="PCB Layout">
</div>

<div>
  <h4>3D Model</h4>
  <img src="../RcConProj/3Dmodel.png" alt="3D MODEL">
</div>

<div>
  <h4>Schematic</h4>
  <img src="../RcConProj/schematic1IMG.jpg" alt="Schematic">
</div>

</div>

---

## Technical Highlights

| Feature | Description |
| --- | --- |
| **Microcontroller** | ESP32-S3-WROOM-2 |
| **Power System** | 3.3 V regulated supply with reverse polarity protection and decoupling network |
| **Programming Interface** | USB-C |
| **Peripherals** | SPI, UART, HMI (buttons, potentiometers, and joysticks) |
| **Wireless** | BLE and Wifi |
| **PCB Stackup** | 4-layer (Top: mixed, L2: GND, L3: power, Bottom: signals/GND) |
| **Design Tools** | KiCad for schematic capture, layout, and DRC verification and JLCPCB's DFM |

---

## Design Process

- Schematic capture: Defined power, MCU, and peripheral subsystems with proper decoupling and ESD protection.

- Validation: Ran ERC/DRC checks and verified manufacturability with JLCPCB’s DFM tool.
  
---

## Results

- Comming soon

---

## Reflection

This project strengthened Luis’s experience in:

- PCB design
- Power regulation and decoupling strategies  
- ESD protection and power strategies
- Battery Charging

Future improvements include external clock tuning, and a more compact and optimized layout

---

## Links

- [Team Website](https://egr314-2025-s-202.github.io/team202.github.io/)  
- [Resume (PDF)](../subfolder/Mechatronic.pdf)
