# F450 Quadcopter Drone Build using KK2.1.5 Flight Controller

## Project Overview

This project documents the complete design, assembly, configuration, calibration, and testing of a custom-built F450 Quadcopter Drone using the KK2.1.5 Flight Controller, FlySky FS-i6 Transmitter, and A2212 1000KV Brushless Motors.

The primary objective of this project was to understand the working principles of multirotor drones, flight stabilization systems, RC communication, power distribution systems, ESC control, and flight tuning.

The drone was successfully assembled, configured, calibrated, and tested with a flight duration of approximately 10+ minutes using a 3S 2200mAh LiPo battery.

---

# Hardware Components

## Frame

| Component     | Specification            |
| ------------- | ------------------------ |
| Frame         | F450 Quadcopter Frame    |
| Material      | Glass Fiber + Nylon Arms |
| Configuration | Quad X                   |

Approximate Cost: ₹700 – ₹1200

---

## Motors

| Component  | Specification      |
| ---------- | ------------------ |
| Motor Type | Brushless DC Motor |
| Model      | A2212              |
| KV Rating  | 1000KV             |
| Quantity   | 4                  |

Approximate Cost: Included in Kit

---

## ESC

| Component      | Specification |
| -------------- | ------------- |
| ESC Type       | SimonK ESC    |
| Current Rating | 30A           |
| Quantity       | 4             |

Approximate Cost: Included in Kit

---

## Propellers

| Component | Specification   |
| --------- | --------------- |
| Type      | 1045 Propellers |
| Quantity  | 2 CW + 2 CCW    |

Approximate Cost: Included in Kit

---

## Flight Controller

| Component  | Specification |
| ---------- | ------------- |
| Controller | KK2.1.5       |
| MCU        | Atmel 644PA   |
| Sensor     | MPU6050       |
| Display    | LCD           |

Approximate Cost: ₹1200 – ₹1800

---

## Radio Control System

| Component   | Specification  |
| ----------- | -------------- |
| Transmitter | FlySky FS-i6   |
| Receiver    | FS-iA6B        |
| Channels    | 6 Channels     |
| Frequency   | 2.4GHz AFHDS2A |

Approximate Cost: ₹4500 – ₹6000

---

## Battery

| Component        | Specification |
| ---------------- | ------------- |
| Battery Type     | LiPo          |
| Cells            | 3S            |
| Voltage          | 11.1V         |
| Capacity         | 2200mAh       |
| Discharge Rating | 35C           |

Approximate Cost: ₹1200 – ₹1800

---

## Charger

| Component | Specification               |
| --------- | --------------------------- |
| Charger   | IMAX B3 Pro Compact Charger |

Approximate Cost: ₹350 – ₹600

---

# Estimated Project Cost

| Component           | Cost  |
| ------------------- | ----- |
| F450 Kit            | ₹4500 |
| KK2.1.5             | ₹1500 |
| FS-i6 + Receiver    | ₹5500 |
| Battery             | ₹1500 |
| Charger             | ₹500  |
| Connectors & Wiring | ₹500  |

## Total Cost

₹13,000 – ₹15,000

---

# Drone Architecture

Battery
↓
Power Distribution Board
↓
4 x ESC
↓
4 x Brushless Motors

Receiver
↓
KK2.1.5 Flight Controller
↓
ESC Signal Wires
↓
Motors

---

# Motor Rotation Directions

Quad X Configuration

Front

M2 (CCW) -------- M1 (CW)

M3 (CW) -------- M4 (CCW)

Rear

---

# Propeller Installation

CW Propellers

Motor 1
Motor 3

CCW Propellers

Motor 2
Motor 4

Always verify motor direction before installing propellers.

---

# Flight Controller Wiring

KK2.1.5 Receiver Inputs

Channel 1 → Aileron
Channel 2 → Elevator
Channel 3 → Throttle
Channel 4 → Rudder
Channel 5 → AUX

---

# Receiver Connections

FS-iA6B Receiver

CH1 → Aileron
CH2 → Elevator
CH3 → Throttle
CH4 → Rudder
CH5 → AUX

Connected directly to KK2.1.5 Input Ports.

---

# ESC Connections

KK2.1.5 Outputs

M1 → Front Right Motor
M2 → Front Left Motor
M3 → Rear Left Motor
M4 → Rear Right Motor

Signal wire orientation:

Signal → Top Row
5V → Middle Row
Ground → Bottom Row

---

# Power Wiring

Battery XT60 Connector
↓
Power Distribution Board

Power Distribution Board
↓
ESC 1
ESC 2
ESC 3
ESC 4

Recommended Wire

14 AWG Silicone Wire

Alternative

1.5 sq.mm Flexible Copper Wire

---

# Initial ESC Testing

Before connecting to KK2:

Arduino Uno
↓
Servo Library
↓
ESC Signal Wire

Used to verify:

* ESC functionality
* Motor functionality
* Rotation direction

---

# KK2.1.5 Configuration

Load Motor Layout

Menu
↓
Load Motor Layout
↓
Quadcopter X

---

# Receiver Mode

Receiver Type

STD

Channel Mapping

AETR

---

# Sensor Calibration

ACC Calibration

1. Place drone on flat surface
2. Open KK Menu
3. Select ACC Calibration
4. Press Enter
5. Wait for completion

---

# Receiver Test Verification

Correct Directions

Roll Right → Positive
Roll Left → Negative

Pitch Forward → Positive
Pitch Backward → Negative

Yaw Right → Positive
Yaw Left → Negative

Throttle Up → Positive

---

# Self-Level Configuration

Self-Level Mode

Always Enabled

Recommended Values

Self-Level P Gain = 60

Self-Level Limit = 30

---

# PID Tuning

Recommended Starting Values

Roll

P Gain = 65
I Gain = 30

Pitch

P Gain = 65
I Gain = 30

Yaw

P Gain = 50

Further tuning performed based on flight behavior.

---

# Battery Monitoring

KK2.1.5 Battery Monitoring Pins

BATT +
BATT -

Connected directly to battery voltage sensing wires.

Recommended Low Voltage Alarm

10.5V – 10.8V

---

# Flight Procedure

1. Turn ON transmitter
2. Connect battery
3. Wait for KK2 initialization
4. Arm motors
5. Slowly increase throttle
6. Lift to 1 meter hover
7. Test Roll
8. Test Pitch
9. Test Yaw
10. Land safely

---

# Safety Checklist

Before Every Flight

✓ Battery charged
✓ Props tightened
✓ Motor directions verified
✓ KK2 calibrated
✓ Receiver connected
✓ Transmitter battery charged
✓ No loose wires

---

# Flight Performance

Battery Used

3S 2200mAh LiPo

Observed Flight Time

10+ Minutes

Flight Mode

Manual Self-Level

---

# Future Enhancements

## GPS Integration

Potential upgrade using:

* Pixhawk
* Neo M8N GPS

Features:

* GPS Hold
* Return To Home
* Autonomous Navigation

---

## Camera System

Planned Upgrades

* ESP32-CAM
* 2 Axis Pan-Tilt Mount
* Live Video Streaming

Future Advanced Options

* FPV Camera
* AI Object Detection
* Computer Vision
* Search and Rescue Applications

---

# Learning Outcomes

Through this project the following concepts were learned:

* Brushless Motor Control
* ESC Operation
* RC Communication
* Flight Controller Configuration
* PID Tuning
* LiPo Battery Management
* Quadcopter Dynamics
* Flight Stabilization
* Sensor Calibration
* Power Distribution Systems

---

# Project Status

Successfully Built
Successfully Configured
Successfully Tuned
Successfully Flight Tested

Current Flight Time: 10+ Minutes

Status: Operational
