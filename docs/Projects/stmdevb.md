---
title: STM32 DEV BOARD
tags: [case-study, embedded, stm32, pcb, schematic, RF, LSE, HSE]
---

<div class="hero">
  <h1>STM32 Dev Board for Future projects</h1>
  <p class="lead">Custom STM32 wireless module that provides bluetooth connectivity, ESD protection, and clean electrical interfaces like GPIO headers, and SPI and I2C headers.</p>
  <div>
    <a class="hero-cta primary" href="../projects/">← Back to Projects</a>
    <a class="hero-cta ghost" href="../../subfolder/Mechatronic.pdf">Resume</a>
  </div>
</div>

---

## Overview

Designed a custom STM32WB55CCU6 development board to strengthen my multi‑layer PCB design skills and build a reusable platform for future embedded projects. The board integrates BLE 5.3 wireless capability, USB programming, SWD debugging, and expandable I/O for sensors and actuators. Its 4‑layer layout focuses on clean grounding, proper decoupling, and RF‑safe antenna placement. Although unmanufactured and untested so far, it represents a production‑ready design that reflects my current engineering capabilities.

---

## Objective

Create a **custom STM32 PCB** that:

- Hand-solderable, compact 4-layer board for prototyping
- USB programming and debugging via USB interface
- Wireless capabilities (BLE)
- Accept battery or DC power (from barrel jack) and power from USB
- GPIO headers for sensors, actuators, and debugging  
- Further technical and PCB skills

---

## Hardware Images

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 16px;">

<div>
  <h4>PCB Layout</h4>
  <img src="../STMdevBoard/pcbview.png" alt="PCB Layout">
</div>

<div>
  <h4>3D Model</h4>
  <img src="../STMdevBoard/stm_dcmotor_encoder.png" alt="3D MODEL">
</div>

<div>
  <h4>Schematic</h4>
  <img src="../STMdevBoard/stmschematic.png" alt="Schematic">
</div>

</div>

---

## Technical Highlights

| Feature | Description |
| --- | --- |
| **Microcontroller** | STM32WB55CCU6 (ARM Cortex-M4 + M0, BLE 5.3, 256 KB Flash, 128 KB SRAM) |
| **Power System** | 3.3 V regulated supply with reverse polarity protection and decoupling network |
| **Programming Interface** | Native USB (DFU + CDC) and SWD header |
| **Peripherals** | I²C, SPI, UART, GPIO expansion headers |
| **Wireless** | Integrated BLE via u.fl connection |
| **PCB Stackup** | 4-layer (Top: mixed, L2: GND, L3: power, Bottom: signals/GND) |
| **Solderability** | QFN48 package with exposed pad and thermal vias |
| **Design Tools** | KiCad for schematic capture, layout, and DRC verification |

---

## Design Process

- Schematic capture: Defined power, MCU, and peripheral subsystems with proper decoupling and ESD protection.

- Layout: Focused on short return paths, ground stitching vias, and RF isolation for BLE antenna.

- Validation: Ran ERC/DRC checks and verified manufacturability with JLCPCB’s DFM tool.
  
---

## Results

- Compact STM32 dev board
- Simplified integration through clean power and signal interfaces  

---

## Reflection

This project strengthened Luis’s experience in:

- PCB design for RF‑capable microcontrollers
- Gained experience in RF layout considerations
- Filtering RF and power lines
- Power regulation and decoupling strategies  
- ESD protection and power strategies

Future improvements include antenna tuning, external clock tuning, and a more compact and optimized layout

---

## Links

- [Team Website](https://egr314-2025-s-202.github.io/team202.github.io/)  
- [Resume (PDF)](../subfolder/Mechatronic.pdf)
