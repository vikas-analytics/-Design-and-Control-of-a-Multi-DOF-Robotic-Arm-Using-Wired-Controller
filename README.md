# 🤖 Design and Control of a Multi-DOF Robotic Arm Using Wired Controller

### 5-DOF Robotic Arm | STM32 | Servo Control | PWM | Kinematics

An academic robotics project focused on the **design, development, and control of a 5 Degrees of Freedom (DOF) robotic arm using a wired controller**.

The project combines mechanical design, embedded electronics, servo-motor control, PWM generation, and robotic kinematics to achieve controlled and coordinated movement of the robotic arm.

---

## 📌 Project Overview

Robotic arms are widely used in industrial automation, laboratory applications, education, material handling, and repetitive tasks.

This project presents a **5-DOF robotic arm** designed to replicate human-like arm movements and perform basic manipulation tasks such as:

* Pick and place
* Object sorting
* Object positioning
* Basic assembly
* Laboratory automation
* Educational demonstrations

The system uses servo motors for joint actuation and an **STM32F103C8T6 microcontroller** as the primary control unit.

---
* RoboArm Model Preview :
  <img width="526" height="488" alt="Robo arm model preview" src="https://github.com/user-attachments/assets/c01f8b4a-b292-4a39-9559-8c107e5263ca" />


## 🎯 Objectives

The main objectives of this project are:

* Design a functional 5-DOF robotic arm.
* Control multiple servo motors simultaneously.
* Implement wired control of the robotic arm.
* Generate PWM signals for accurate servo positioning.
* Study forward and inverse kinematics.
* Achieve coordinated movement of multiple joints.
* Develop a low-cost and programmable robotic platform.
* Explore applications in automation, education, and research.

The research specifically focuses on accurate, efficient, and repeatable robotic-arm operation.

---

## 🏗️ System Architecture

```text
                 ┌─────────────────────┐
                 │   Wired Controller  │
                 └──────────┬──────────┘
                            │
                            ▼
                 ┌─────────────────────┐
                 │ STM32F103C8T6 MCU   │
                 │   Control Unit      │
                 └──────────┬──────────┘
                            │
                       PWM Signals
                            │
          ┌─────────────────┼─────────────────┐
          ▼                 ▼                 ▼
      Servo 1            Servo 2           Servo 3
       Base             Shoulder            Elbow
          │                 │                 │
          └─────────────────┼─────────────────┘
                            │
                       Servo 4 & 5
                            │
                            ▼
                    ┌───────────────┐
                    │ End Effector  │
                    │   / Gripper   │
                    └───────────────┘
```

---

## ⚙️ Working Principle

The robotic arm consists of multiple revolute joints connected through rigid mechanical links.

Each joint is actuated using a servo motor. The STM32 microcontroller receives control commands and converts them into PWM signals.

The PWM signals determine the angular position of individual servo motors, allowing coordinated movement of the robotic arm.

### Basic workflow

```text
Controller Input
       ↓
Command Processing
       ↓
Joint Angle Calculation
       ↓
PWM Generation
       ↓
Servo Motor Movement
       ↓
Robotic Arm Motion
       ↓
End-Effector Position
```

---

## 🧮 Kinematics

A major part of the project involves robotic kinematics.

### Forward Kinematics

Forward kinematics determines the position and orientation of the end-effector based on the known joint angles.

```text
Joint Angles
     ↓
Kinematic Equations
     ↓
End-Effector Position
```

### Inverse Kinematics

Inverse kinematics works in the opposite direction. It determines the required joint angles to achieve a desired end-effector position and orientation.

```text
Desired Position
       ↓
Inverse Kinematics
       ↓
Required Joint Angles
       ↓
Servo Positions
```

The research identifies both forward and inverse kinematics as important for accurate pick-and-place and positioning operations.

---

## 🎮 Control System

The robotic arm can receive commands through a wired controller or other control interfaces.

The microcontroller processes these commands and generates PWM signals corresponding to the required servo positions.

The system can operate using:

### Open-Loop Control

Predefined movements are executed without positional feedback.

### Closed-Loop Control

Sensors can provide feedback about the position of joints, allowing the controller to detect and correct positional errors.

---

## 🔩 Mechanical Structure

The robotic arm consists of:

* Base
* Shoulder link
* Upper arm
* Elbow joint
* Forearm
* Wrist joints
* End-effector / gripper

The five revolute joints form the kinematic chain responsible for positioning and orienting the end-effector.

---

## 🔧 Hardware Components

| Component           | Purpose                |
| ------------------- | ---------------------- |
| STM32F103C8T6       | Main microcontroller   |
| Servo Motors        | Joint actuation        |
| Wired Controller    | User input             |
| 5V Regulated Supply | Servo power            |
| Power Supply        | MCU operation          |
| Limit Switches      | Joint safety           |
| Jumper Wires        | Electrical connections |
| Capacitors          | Power stabilization    |
| Mechanical Links    | Robotic structure      |
| Bearings            | Reduce joint friction  |
| Gripper             | Object manipulation    |

The paper specifies the STM32F103C8T6 and multiple servo motors as the principal electronics and actuation components.

---

## 🧠 Microcontroller

### STM32F103C8T6

The STM32F103C8T6 is used as the main control unit.

Key characteristics described in the research include:

* 32-bit ARM Cortex-M3 architecture
* 72 MHz clock
* Multiple PWM channels
* USART communication
* I²C
* SPI
* 3.3V operation

It processes control commands and generates PWM signals for coordinated servo movement.

---

## ⚙️ Servo Motor Configuration

The documented configuration includes:

| Servo   | Function                         |
| ------- | -------------------------------- |
| Servo 1 | Base Rotation                    |
| Servo 2 | Shoulder                         |
| Servo 3 | Elbow                            |
| Servo 4 | Wrist Pitch                      |
| Servo 5 | Wrist Roll / Gripper Orientation |

The paper also documents an additional pickup servo channel in its pin-configuration section.

---

## 🔌 Power System

The robotic arm uses separate power requirements for the servo motors and microcontroller.

The research describes:

* **5V regulated supply** for servo motors
* **3.3V or 5V supply** for the STM32
* **0.1 µF decoupling capacitors** for MCU-related stabilization
* **1000 µF bulk capacitor** for servo power stabilization

These help maintain stable operation during changes in servo current demand.

---

## 🛡️ Safety Features

Safety and reliability are important aspects of the system.

The project considers:

* Limit switches
* Positional feedback
* Joint-limit protection
* Obstacle detection
* Stable power supply
* Mechanical stability
* Controlled servo movement

Limit switches and sensors can help prevent the robotic arm from exceeding its intended joint limits or colliding with objects.

---

## 🚀 Applications

### 🏭 Industrial Automation

* Material handling
* Pick-and-place
* Packaging
* Assembly
* Sorting
* Repetitive operations

### 🎓 Education & Research

* Robotics education
* Kinematics experiments
* Control-system demonstrations
* Automation research
* Motion-planning experiments

### 🧪 Laboratory Automation

* Sample handling
* Repetitive laboratory tasks
* Experimental automation

### 🏥 Medical & Rehabilitation Research

The research also identifies potential applications in areas such as rehabilitation assistance and precision-support systems.

---

## 📊 Key Features

* 🤖 5 Degrees of Freedom
* 🎮 Wired Controller
* ⚙️ Servo Motor Based Actuation
* 🧠 STM32 Microcontroller
* 📡 PWM-Based Motor Control
* 🧮 Forward Kinematics
* 🔄 Inverse Kinematics
* 🛡️ Limit-Switch Safety
* 🎯 Precise Positioning
* 🔧 Modular Mechanical Design
* 💰 Low-Cost Approach
* 🏭 Automation Applications

---

## 📈 Results

The research reports that the robotic arm demonstrated:

* Smooth movement
* Accurate positioning
* Repeatable operation
* Coordinated joint movement
* Practical pick-and-place capability
* Potential for educational and light industrial applications

The results support the feasibility of a low-cost robotic-arm platform integrating mechanical design, electronics, and control algorithms.

---

## 📚 Research Publication

### Published Research Paper

**Title:**
**Design and Control of a Multi-DOF Robotic Arm Using Wired Controller**

**Journal:** Journal of Advance and Future Research (JAAFR)

**Volume:** 4

**Issue:** 3

**Publication:** March 2026

**Paper ID:** JAAFR2603642

**Registration ID:** 504701

**Authors:**

* Vikas Chaurasiya
* Aman Gupta
* Vishal Yadav
* Pawan Pal
* Namrata Kulkarni

The publication certificate confirms the paper's publication in Volume 4, Issue 3, March 2026.

---

## 👨‍💻 Team

| Member           | Contribution           |
| ---------------- | ---------------------- |
| Vikas Chaurasiya | Research & Development |
| Aman Gupta       | Research & Development |
| Vishal Yadav     | Research & Development |
| Pawan Pal        | Research & Development |
| Namrata Kulkarni | Faculty Guidance       |

---

## 📁 Repository Structure

```text
5-DOF-Robotic-Arm/
│
├── README.md
│
├── docs/
│   ├── Research-Paper.pdf
│   └── Publication-Certificate.pdf
│
├── hardware/
│   ├── block-diagram.png
│   ├── circuit-diagram.png
│   └── robotic-arm.jpg
│
├── firmware/
│   └── STM32/
│
├── kinematics/
│   ├── forward-kinematics/
│   └── inverse-kinematics/
│
├── images/
│   └── project-images/
│
└── LICENSE
```

---

## 📖 References

1. J. J. Craig, *Introduction to Robotics: Mechanics and Control*, Pearson.
2. B. Siciliano and O. Khatib, *Springer Handbook of Robotics*.
3. M. P. Groover, *Automation, Production Systems, and Computer-Integrated Manufacturing*.
4. STM32F103 Reference Manual.
5. RoboAnalyzer — Robotics Simulation and Analysis Tool.
6. Research literature on kinematic analysis and control of 5-DOF robotic arms.

---

## ⭐ Project Status

**Status:** Completed Academic Research Project

**Domain:** Robotics & Automation

**Controller:** STM32F103C8T6

**Degrees of Freedom:** 5 DOF

**Control:** Wired / PWM-Based

**Research Publication:** Published

**Publication Year:** 2026

**Paper ID:** JAAFR2603642

---

## 📜 Disclaimer

This repository is intended for **educational, academic, and research purposes**. The documentation represents the project described in the associated research publication and is intended to demonstrate concepts in robotics, embedded systems, servo control, kinematics, and automation.

---

### 🚀 Future Improvements

Potential future improvements identified by the research include:

* Increasing the number of degrees of freedom
* Wireless control
* Advanced sensors
* More sophisticated task sequences
* Improved feedback control
* Advanced motion planning
* Greater automation capability

The research specifically identifies additional DOF, wireless control, advanced sensors, and complex task sequences as possible future enhancements.
