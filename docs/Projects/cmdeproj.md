---
title: Ceiling‑Mounted Drone Docking System
tags: [case-study, embedded, stm32, pcb, schematic, actuators]
---

<div class="hero">
  <h1>Ceiling‑Mounted Drone Docking System</h1>
  <p class="lead">Custom embedded controller and actuator interface enabling a ceiling‑mounted docking mechanism for autonomous drone retrieval.</p>
  <div>
    <a class="hero-cta primary" href="../projects/">← Back to Projects</a>
    <a class="hero-cta ghost" href="https://github.com/luisasaenz/STEM-DAM">Repository</a>
  </div>
</div>

---

## Overview

This project implements a **ceiling‑mounted docking mechanism** designed to secure a quadcopter after flight.  
Luis developed the **embedded controller**, **actuator interface**, and **custom PCB** responsible for driving a linear actuator, a locking solenoid, and four servos used in the docking and release sequence.

The system focuses on reliable actuation, mechanical alignment, and safe locking/unlocking behavior.

---

## Problem Statement

The docking system required a compact embedded controller capable of:

- Driving a linear actuator for vertical positioning  
- Controlling a locking solenoid for secure retention  
- Operating four servos for mechanical alignment and stabilization  
- Fitting within the tight mechanical constraints of the ceiling mount  
- Providing clean power and reliable signal routing to all actuators  

Off‑the‑shelf boards lacked the required actuator layout, power distribution, and interface routing.

---

## Objective

Design a **custom embedded controller** that:

- Integrates actuator drivers, power regulation, and an STM32 microcontroller  
- Provides stable power delivery for high‑current loads (actuator + solenoid)  
- Breaks out servo headers with proper routing and grounding  
- Fits the mechanical footprint of the ceiling‑mounted enclosure  
- Supports firmware hooks for sequencing and safety interlocks  

---

## Technical Approach

<div class="projects-grid">

<article class="project-card">s
  <img class="project-thumb" src="../CMDEProj/TopPCB_Luis.png" alt="Docking controller PCB">
  <div>
    <p class="project-meta"><span class="project-title">PCB Design</span><span class="kv">4‑Layer · STM32</span></p>
    <p class="project-summary">Designed a compact 4‑layer PCB integrating actuator drivers, power regulation, and an STM32 microcontroller for docking control.</p>
  </div>
</article>

<article class="project-card">
  <img class="project-thumb" src="../CMDEProj/firmware_debug.jpg" alt="Firmware debugging">
  <div>
    <p class="project-meta"><span class="project-title">Schematic & Interfaces</span><span class="kv">Actuators · Power · Control</span></p>
    <p class="project-summary">Created schematics defining actuator outputs, solenoid drive circuitry, servo headers, and power paths for reliable operation.</p>
  </div>
</article>

</div>

---

## System Architecture

- **STM32 microcontroller** for actuator sequencing and safety logic  
- **Linear actuator output** with motor driver interface  
- **Locking solenoid output** with protected high‑current switching  
- **Four servo channels** for mechanical alignment and stabilization  
- **5 V and 3.3 V regulation** with proper decoupling and ground stitching  
- **Debug headers** for firmware development and testing  

The system was designed to be electrically robust and mechanically compact to ensure consistent operation inside the ceiling‑mounted enclosure.

---

## Results

- Delivered a fully functional embedded controller used in the docking prototype  
- Provided reliable control of actuator, solenoid, and servo mechanisms  
- Enabled repeatable docking and release sequences during testing  
- Supported iterative firmware development through accessible debugging headers  

---

## Reflection

This project strengthened Luis’s experience in:

- PCB design for actuator‑driven embedded systems  
- Schematic capture and interface definition  
- Power regulation and high‑current switching  
- Firmware design for sequencing and safety interlocks  
- Integrating embedded hardware into constrained mechanical systems  

Future improvements include adding position feedback, refining actuator control, and optimizing the PCB layout for manufacturability.

---

## Links

- [Team Website](https://egr314-2025-s-202.github.io/team202.github.io/)  
- [Datasheet Sections](https://embedded-systems-design.github.io/EGR314DataSheetTemplate/)  
- [Resume (PDF)](../subfolder/Mechatronic.pdf)
  