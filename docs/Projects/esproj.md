---
title: STEM Education Project — ESP32 Wireless Module
tags: [case-study, embedded, esp32, pcb, schematic, mqtt, wifi]
---

<div class="hero">
  <h1>STEM Education Project</h1>
  <p class="lead">Custom ESP32 wireless module providing Wi‑Fi connectivity, MQTT messaging hooks, and clean electrical interfaces for a modular STEM learning platform.</p>
  <div>
    <a class="hero-cta primary" href="../projects/">← Back to Projects</a>
    <a class="hero-cta ghost" href="https://egr314-2025-s-202.github.io/team202.github.io/">Team Website</a>
  </div>
</div>

---

## Overview

This STEM project introduces students to embedded systems through modular sensing, actuation, human interface, and wireless communication.  
Luis designed the **ESP32 wireless module**, which include schematic capture, PCB layout, and interface definition. The board provided Wi‑Fi connectivity and MQTT publishing/subscribing which was used for team testing and inter‑module communication.

---

## Problem Statement

The team needed a hardware module that could:

- Provide reliable Wi‑Fi connectivity  
- Support MQTT‑based messaging for coordination  
- Receive and deliver messages from team
- Fit within the project’s mechanical constraints  
- Deliver power to team subsystems
  
---

## Objective

Create a **custom ESP32 PCB** that:

- Integrates Wi‑Fi and MQTT capability  
- Provides clean 3.3 V regulation and proper decoupling  
- Breaks out GPIOs for sensors, actuators, and debugging  
- Supports UART communication with team by complying with messaging system.

---

## Technical Approach

<div class="projects-grid">

<article class="project-card">
  <img class="project-thumb" src="../EmbSysProj/RL_PCB.jpg" alt="ESP32 Wi-Fi subsystem PCB">
  <div>
    <p class="project-meta"><span class="project-title">PCB Design</span><span class="kv">2‑Layer · ESP32‑WROOM</span></p>
    <p class="project-summary">Designed a PCB integrating the ESP32 module, power regulation, decoupling, and GPIO expansion for the team’s messaging system and power delivery.</p>
  </div>
</article>

<article class="project-card">
  <img class="project-thumb" src="../EmbSysProj/TopPCB_Luis.png" alt="Firmware debugging">
  <div>
    <p class="project-meta"><span class="project-title">Schematic & Interfaces</span><span class="kv">Power · GPIO · UART/I2C</span></p>
    <p class="project-summary">Created schematics defining power paths, protection circuitry, and communication buses to ensure reliable integration with team member's controllers.</p>
  </div>
</article>

</div>

---

## System Architecture

- **ESP32‑WROOM module** for Wi‑Fi  
- **On‑board 3.3 V buck regulator** with proper decoupling
- **GPIO breakout** for sensors, actuators, and debugging  
- **UART headers** for communication with the main controller  
- **MQTT firmware hooks** for publish/subscribe messaging  
- **Topic structure** used during development:  
  - `team202/sub*`  
  - `team202/rpm*`  
  - `team202/sensor*`  

MQTT was primarily used as a **status screen**, allowing users and team to see real-time data.

---

## Results

- Delivered a **fully functional ESP32 wireless module** used throughout the project  
- Provided a stable hardware platform for MQTT‑based communication  
- Simplified integration through clean power and signal interfaces  
- Enabled team debugging using standard MQTT tools  
- Supported classroom demonstrations without additional hardware  

---

## Reflection

This project strengthened Luis’s experience in:

- PCB design for RF‑capable microcontrollers  
- Schematic capture and interface definition  
- Power regulation and decoupling strategies  
- Designing hardware to support firmware‑level communication protocols  
- Cross‑team collaboration across mechanical, firmware, and sensing groups  

Future improvements include antenna tuning, onboard diagnostics, and a more compact layout optimized for manufacturability.

---

## Links

- [Team Website](https://egr314-2025-s-202.github.io/team202.github.io/)  
- [Datasheet Sections](https://embedded-systems-design.github.io/EGR314DataSheetTemplate/)  
- [Resume (PDF)](../subfolder/Mechatronic.pdf)
