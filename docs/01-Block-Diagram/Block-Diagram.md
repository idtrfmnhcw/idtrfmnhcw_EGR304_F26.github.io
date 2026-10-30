
---
title: Individual Block Diagram
tags:
- Block Diagram
- EGR304
---

## Overview

This block diagram describes the User Controls & Safety subsystem of the project.

The subsystem uses a Microchip PIC18F57Q43 Curiosity Nano to process user inputs and provide system safety and status outputs.

The main user-control inputs include:

* E-Stop Button
* Start / Pause Button
* Speed Knob (Potentiometer)

The main actuators and indicators include:

* Green LED for run status
* Red LED for fault or E-Stop indication
* Buzzer for audible warning

The subsystem receives its required power from the project power distribution system and distributes the appropriate supply voltage to the microcontroller and user-interface components.

The subsystem communicates with other project subsystems through Connector 1 using digital and analog signals.

The primary inter-system signals include SAFE_OK, RUN_REQ, GRIP_CMD, OBJ_HELD, ARM_IN_POS, SPEED_SET, GRIP_FORCE, and GND.

## Block Diagram

![User Controls and Safety Individual Block Diagram]<img width="805" height="681" alt="螢幕擷取畫面 2026-10-30 124431" src="https://github.com/user-attachments/assets/8ec44210-9675-47fb-a873-7b4eb69a36e5" />
