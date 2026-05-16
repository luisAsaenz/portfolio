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

This project implements a **ceiling‑mounted docking mechanism** designed to secure and release a quadcopter.  
**Role:** Electrical, software, and team lead.  
**Dates:** 09/2025 – 05/2026.  
Luis designed the **embedded controller**, **actuator interface**, and **custom PCB** that drive a linear actuator, a locking solenoid, and four servos to perform the docking sequence.

---

## Hardware Summary

**Key components**
- **MCUs:** Arduino Uno 3 (peripheral controller), Raspberry Pi 5 (server)  
- **Locking actuator:** FIT0620 (electric solenoid) driven via relay breakout  
- **Linear actuator:** PQR12-100-6-R  
- **Servos:** 4 × 180° (p# ser0064)  
- **Power:** three 6 V buck regulators, one 12 V buck regulator; resettable fuses; terminal blocks; GPIO headers  
- **Protection:** TVS diodes; resettable fuses; flyback diodes (implemented where applicable)

**PCB**
- **Stackup:** 2‑layer board; top and bottom used as ground planes  
- **Layout strategy:** power pours on top, signal traces on bottom; compact form factor to fit inside the ceiling enclosure; mounting holes included though enclosure mounting was not finalized  
- **Tools:** Cadence (design files not shared)

---

## Electrical Design and Interfaces

**Power distribution**
- **Three 6 V regulators** (one configurable to ~7 V via feedback resistor for MCU rail; 500–900 mA budget)  
  - Reg A: MCU rail (adjustable)  
  - Reg B: Servos (combined 1.8–2 A per servo budget)  
  - Reg C: Linear actuator (200–300 mA)  
- **12 V regulator** for locking actuator (200–300 mA)

**Actuator interfaces**
- **Linear actuator:** PWM control from Arduino (pin 3) via motor driver interface  
- **Servos:** PWM channels on Arduino (pins 5, 6, 9, 10) with dedicated 6 V servo rail and common ground  
- **Locking solenoid:** driven by relay breakout controlled from Arduino GPIO (relay logic on digital outputs); solenoid state read on a digital input (pin 7)  
- **Communications:** UART between Arduino and Raspberry Pi 5 (Arduino RX on pin 11 used as software UART)  
- **Debugging:** terminal blocks for UART and LEDs; SW-style debug headers included

**Protection and safety**
- TVS diodes and resettable fuses on power rails; flyback diodes used on inductive loads where applicable.

---

## Firmware and Control

**Responsibilities implemented**
- Sequencing and stage control for opening, closing, and release operations  
- PWM generation for servos and linear actuator; helper function to map 0–100% stroke to PWM values per actuator datasheet  
- Relay control and solenoid timing with safety interlocks and timeouts  
- UART command interface for manual testing and server control

**Command interface (serial)**
- `next` — advance to next stage  
- `back` — return to previous stage  
- `start` — enable autonomous open/close/release sequences after configuration  
- `quit` — abort and reset to stage zero

**Notes**
- Firmware organized into discrete "stages" to allow stepwise testing and safe handoff between manual and autonomous operation.  
- Used AI tools to accelerate debugging and to scaffold the Raspberry Pi server that relays commands to the Arduino.

---

## Integration and Testing

**Mechanical integration**
- PCB sized to fit between enclosure doors; wiring left exposed for demonstration; four PCB mounting holes provided though not fastened to the enclosure in final demo.

**Key tests and outcomes**
- **Actuation sequencing:** reliable open/close sequences implemented and repeatable under test conditions.  
- **Solenoid holding:** evaluated whether solenoid/magnet arrangement could retain the drone and release reliably; required mechanical adjustments to the drone harness.  
- **Material failure:** PLA inner gear shafts failed under servo torque (~80% failure). Replaced with D‑type shafts to handle torque.  
- **Linear actuator range:** actuator stroke alone could not separate drone from magnets; team added prongs to the drone harness to increase separation and enable release.  
- **Servo torque/locking:** servo/geartrain could not reliably provide locking torque in the original gear design; mechanical redesign required for robust locking.

**Known limitations**
- No position feedback implemented (open‑loop control).  
- Wiring harness and enclosure mounting were left exposed for the prototype demonstration.  
- Some protection components (flyback diodes placement) were iterated during testing.

---

## Results and Reflection

**Deliverables**
- Custom 2‑layer PCB integrating actuator drivers, power regulation, and MCU interfaces  
- Firmware for staged sequencing, PWM control, and UART command handling  
- Prototype enclosure integration and demonstration-ready hardware

**Skills strengthened**
- PCB design for actuator‑driven systems; power distribution and high‑current switching; firmware sequencing and safety interlocks; cross‑discipline coordination with mechanical and systems teams.

**Future improvements**
- Add position feedback (limit switches or encoders) for closed‑loop control  
- Harden mechanical interfaces and replace PLA parts with stronger materials or redesigned geometry  
- Implement a harnessed wiring solution and enclosure mounting points for production readiness

---

## Assets and Credits

**Files and assets**
- Board and enclosure images available on request for inclusion in the case study (user will provide).  
- Design files created in Cadence (not shared).

**Team credit**
- **Emerson Wall** — teammate and collaborator

---

## Links

- [Team Website](https://egr314-2025-s-202.github.io/team202.github.io/)  
- [Datasheet Template](https://embedded-systems-design.github.io/EGR314DataSheetTemplate/)  
- [Resume (PDF)](../subfolder/Mechatronic.pdf)
