---
title: Ceiling‑Mounted Drone Docking System
tags: [case-study, embedded, stm32, pcb, schematic, actuators]
---

<div class="hero">
  <h1>Ceiling‑Mounted Drone Docking System</h1>
  <p class="lead">Custom embedded controller and actuator interface enabling a ceiling‑mounted docking mechanism for autonomous drone retrieval and controlled release.</p>
  <div>
    <a class="hero-cta primary" href="../projects/">← Back to Projects</a>
    <a class="hero-cta ghost" href="https://github.com/luisasaenz/STEM-DAM">Repository</a>
  </div>
</div>

---

## Overview

This project implements a **ceiling‑mounted docking mechanism** designed to secure and release a quadcopter.  
**Role:** Electrical, software, and team lead  
**Dates:** 09/2025 – 05/2026  

Luis designed the **embedded controller**, **actuator interface**, and **custom PCB** that drive a linear actuator, a locking solenoid, and four servos to perform the docking sequence.

---

## Hardware Summary

### Key Components

- **MCUs:** Arduino Uno 3 (peripheral controller), Raspberry Pi 5 (server)  
- **Locking actuator:** FIT0620 (electric solenoid) via relay breakout  
- **Linear actuator:** PQR12-100-6-R  
- **Servos:** 4 × 180° (p# ser0064)  
- **Power:** three 6 V buck regulators, one 12 V buck regulator  
- **Protection:** TVS diodes, resettable fuses, flyback diodes  
- **Connectivity:** terminal blocks, GPIO headers

---

## PCB Design

- **2‑layer board**  
- **Top and bottom ground planes**  
- **Power pours on top**, **signal routing on bottom**  
- Designed to fit inside the ceiling enclosure with limited space  
- Included mounting holes even though enclosure lacked mounting points  
- Designed in **Cadence** (files not shared)

---

## Power Architecture

- **Regulator A (6–7 V adjustable):** MCU rail (500–900 mA)  
- **Regulator B (6 V):** Servo rail (1.8–2 A combined)  
- **Regulator C (6 V):** Linear actuator (200–300 mA)  
- **12 V regulator:** Locking actuator (200–300 mA)

---

## Actuator Interfaces

- **Arduino Uno 3** controller that pins are connected to.
- **Linear actuator:** PWM pin 3  
- **Servos:** PWM on pins 5, 6, 9, 10  
- **Solenoid:** Relay breakout controlled via digital output  
- **Solenoid state:** Read via digital input 7  
- **UART:** Arduino ↔ Raspberry Pi 5 (Arduino RX on pin 11 via software UART)

---

## Firmware and Control

The firmware manages sequencing, actuator timing, servo positioning, and safety logic.  
It also provides a simple serial‑based interface for manual testing and for the Raspberry Pi server.

### Command Interface

| Command | Description |
| ------- | ----------- |
| `next` | Advance to the next stage |
| `back` | Return to the previous stage |
| `start` | Enable demo open/close/release sequences after configuration |
| `quit` | Abort and reset to stage zero |

The system is organized into discrete “stages” to allow controlled testing of each mechanical action.  
Commands can be issued from the serial monitor or from the Raspberry Pi server.

---

## Hardware Images

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 16px;">

<div>
  <h4>PCB Layout</h4>
  <img src="../CMDEProj/gerber_pcb.png" alt="PCB Layout">
</div>

<div>
  <h4>Schematic – Page 1</h4>
  <img src="../CMDEProj/schmpg1.png" alt="Schematic Page 1">
</div>

<div>
  <h4>Schematic – Page 2</h4>
  <img src="../CMDEProj/schmpg2.png" alt="Schematic Page 2">
</div>

<div>
  <h4>Schematic – Page 3</h4>
  <img src="../CMDEProj/schmpg3.png" alt="Schematic Page 3">
</div>

<div>
  <h4>Enclosure Assembly</h4>
  <img src="../CMDEProj/enclosure.png" alt="Enclosure Assembly">
</div>

<div>
  <h4>Manufactured PCB</h4>
  <img src="../CMDEProj/PCB_nocomponents.png" alt="Real PCB">
</div>

</div>

---

## Integration and Testing

### Mechanical Integration

- PCB positioned between enclosure doors  
- Wiring left exposed for demonstration  
- No enclosure mounting points; PCB included its own mounting holes

### Key Tests

- Verified actuator sequencing and timing  
- Evaluated solenoid holding and release behavior  
- Identified PLA gear shaft failures (80% failure rate) → replaced with D‑shaft  
- Linear actuator stroke insufficient → added prongs to drone harness  
- Servo torque or inner gear assembly and driving gear is insufficient for locking → mechanical redesign required

---

## Results and Reflection

### Deliverables

- Custom 2‑layer PCB integrating all actuators and power rails  
- Firmware for staged sequencing, PWM control, and UART interface  
- Demonstration‑ready prototype

### Skills Strengthened

- PCB design for actuator‑driven systems  
- Power distribution and high‑current switching  
- Firmware sequencing and safety logic  
- Cross‑discipline coordination with mechanical team

### Future Improvements

- Add position feedback (limit switches or encoders)  
- Improve mechanical robustness (material + geometry)  
- Add proper wiring harness and enclosure mounting solution  

---

## Credits

- **Emerson Wall** — teammate and collaborator

---

## Links

- [Team Website](https://egr314-2025-s-202.github.io/team202.github.io/)  
- [Datasheet Template](https://embedded-systems-design.github.io/EGR314DataSheetTemplate/)  
- [Resume (PDF)](../subfolder/Mechatronic.pdf)
