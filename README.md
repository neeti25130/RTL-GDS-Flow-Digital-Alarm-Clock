# ⏰ Digital Alarm Clock – Complete RTL to GDSII Flow

![VLSI](https://img.shields.io/badge/Domain-VLSI-blue)
![RTL](https://img.shields.io/badge/Design-Verilog-green)
![Cadence](https://img.shields.io/badge/EDA-Cadence-orange)
![Status](https://img.shields.io/badge/Project-Completed-success)

## 📌 Project Overview

This project implements a **Digital Alarm Clock** using a complete **RTL-to-GDSII VLSI Design Flow**. The design was developed in **Verilog HDL** and taken through multiple stages of semiconductor implementation, including **functional verification, synthesis, formal verification, Design for Testability (DFT), Static Timing Analysis (STA), floorplanning, placement, Clock Tree Synthesis (CTS), routing, physical verification, and final GDS generation**.

The Digital Alarm Clock supports **real-time clock operation, programmable dual alarms, snooze functionality, cancel operation, buzzer control, and display interfacing**. Multiple optimization constraints such as **minimum area, best timing, and intermediate timing constraints** were explored to study the impact on performance, power, and area (PPA).

---

# 📖 Table of Contents

* [Project Objective](#-project-objective)
* [Features](#-features)
* [System Architecture](#-system-architecture)
* [RTL Design](#-rtl-design)
* [Functional Verification](#-functional-verification)
* [Code Coverage](#-code-coverage)
* [Logic Synthesis](#-logic-synthesis)
* [Constraint Optimization](#-constraint-optimization)
* [Formal Equivalence Checking](#-formal-equivalence-checking)
* [Static Timing Analysis (STA)](#-static-timing-analysis-sta)
* [Design for Testability (DFT)](#-design-for-testability-dft)
* [Physical Design Flow](#-physical-design-flow)
* [Power, Performance and Area (PPA)](#-power-performance-and-area-ppa)
* [Tools Used](#-tools-used)
* [Repository Structure](#-repository-structure)
* [Results](#-results)
* [How to Run](#-how-to-run)
* [Team Members](#-team-members)

---

# 🎯 Project Objective

The primary objective of this project is to design and implement a **Digital Alarm Clock** and complete its **end-to-end VLSI implementation from RTL to GDSII**.

The project focuses on:

* RTL development using **Verilog HDL**
* Functional verification through simulations
* Optimization of **timing, area, and power**
* Design validation using **formal equivalence checking**
* Testability improvement using **scan insertion**
* Physical implementation using **RTL-to-GDS flow**
* Timing closure and physical signoff

---

# ✨ Features

### ⏰ Clock Functionality

* Real-time digital clock
* Hour and minute tracking
* Clock rollover support

### 🔔 Alarm Features

* Dual programmable alarms
* Alarm enable/disable support
* Independent alarm configuration

### 😴 Snooze Feature

* Temporary alarm pause
* Resume after snooze duration

### ❌ Cancel Feature

* Stop ringing alarm immediately

### 🖥️ Display Interface

* Display current time
* Display alarm information

### 🔊 Buzzer Control

* Ring indication when alarm triggers

---

# 🏗️ System Architecture

The Digital Alarm Clock design contains the following major modules:

### 1. Time Counter

Maintains digital clock timing and updates hour/minute values.

### 2. Alarm Programming Block

Allows user-defined alarm programming.

### 3. FSM-Based Alarm Controller

Finite State Machine controls:

* Idle state
* Ringing state
* Snooze state
* Cancel state

### 4. Snooze Logic

Pauses the alarm temporarily and restarts after a delay.

### 5. Display Controller

Updates output display registers.

### 6. Buzzer Logic

Activates buzzer whenever alarm matches system time.

---

# 💻 RTL Design

The complete functionality was implemented in **Verilog HDL**.

### Key RTL Modules

* Alarm programming logic
* Clock divider
* Counter logic
* Alarm FSM
* Buzzer control
* Display control

### RTL Verification Goals

* Functional correctness
* Proper timing updates
* Correct alarm triggering
* Snooze functionality validation
* Cancel operation testing

---

# 🧪 Functional Verification

Functional verification was performed using multiple **testbenches** to validate design correctness.

### Test Cases Covered

#### ✅ Time Rollover Verification

* 23:59 → 00:00 rollover

#### ✅ Alarm Triggering

* Alarm activates at programmed time

#### ✅ Snooze Verification

* Alarm pauses temporarily

#### ✅ Cancel Operation

* Alarm immediately stops

#### ✅ Stress Testing

* Random test vectors applied

The verification ensured proper behavior across all corner scenarios.

---

# 📊 Code Coverage

Extensive simulation was performed to improve:

### Coverage Metrics

* Statement Coverage
* Branch Coverage
* Toggle Coverage
* FSM Coverage
* Functional Coverage

High code coverage ensured that critical paths and corner cases were properly validated.

---

# ⚙️ Logic Synthesis

RTL was synthesized into a gate-level netlist using **Cadence Genus**.

Synthesis was performed under multiple optimization goals:

## 1. Minimum Area Optimization

Focused on:

* Reducing standard cell utilization
* Lower silicon area
* Reduced resource consumption

## 2. Best Timing Optimization

Focused on:

* Maximum timing performance
* Positive setup slack
* Reduced timing violations

## 3. Intermediate Constraint Optimization

Balanced:

* Timing
* Area
* Power

### Generated Reports

* Area Report
* Timing Report
* Power Report
* Cell Utilization Report

---

# 📐 Constraint Optimization

Different SDC timing constraints were applied:

### Minimum Area

Optimized for silicon efficiency.

### Intermediate Timing

Balanced optimization strategy.

### Best Timing

Achieved timing closure with positive slack.

The comparison helped evaluate **Power, Performance and Area (PPA)** tradeoffs.

---

# 🔍 Formal Equivalence Checking

Formal verification was performed using **Cadence Conformal**.

### Objective

Ensure synthesized netlist matches RTL functionality.

### Verification Steps

* RTL vs synthesized netlist comparison
* Golden vs revised design checking
* Bad netlist comparison

### Results

* Functional equivalence confirmed
* Mismatches identified in intentionally modified netlists

---

# ⏳ Static Timing Analysis (STA)

STA was performed to ensure reliable timing performance.

### Timing Checks

#### Setup Time Analysis

Ensures signals arrive before clock edge.

#### Hold Time Analysis

Ensures signals remain stable.

#### Slack Analysis

* Positive slack → timing met
* Negative slack → violation

### STA Goals

* Timing closure
* No setup violations
* Hold violation fixes
* Clock uncertainty analysis

---

# 🛠️ Design for Testability (DFT)

DFT techniques were introduced to improve chip testability.

### Scan Insertion

* Scan flip-flops inserted
* Scan chains generated

### Benefits

* Easier fault detection
* Better debugging capability
* Improved manufacturing testing

### Fault Coverage

Improved observability and controllability of internal nodes.

---

# 🏭 Physical Design Flow (RTL to GDS)

The synthesized netlist was implemented through the **Physical Design Flow**.

## 1️⃣ Floorplanning

* Die size definition
* IO placement
* Power planning
* Macro placement

## 2️⃣ Power Planning

* Power rings
* Power straps
* Robust VDD/VSS distribution

## 3️⃣ Placement

Standard cells placed optimally to:

* Reduce congestion
* Improve timing
* Minimize wirelength

## 4️⃣ Clock Tree Synthesis (CTS)

Clock buffers inserted to:

* Reduce skew
* Balance clock paths
* Improve timing reliability

## 5️⃣ Routing

Signal routing completed:

* Global Routing
* Detailed Routing

### Routing Goals

* DRC clean routing
* Minimum congestion
* Timing-aware optimization

## 6️⃣ Timing Closure

Post-route optimization performed to:

* Fix setup violations
* Fix hold violations
* Reduce clock skew

## 7️⃣ Physical Verification

Verification checks included:

### DRC (Design Rule Check)

Ensures foundry rule compliance.

### LVS (Layout vs Schematic)

Confirms layout matches schematic.

### Antenna Checks

Protects metal interconnect reliability.

## 8️⃣ GDSII Generation

Final layout exported as **GDSII tapeout database**.

---

# 📈 Power, Performance and Area (PPA)

The design was analyzed using:

### Power

* Internal power
* Leakage power
* Switching power

### Performance

* Timing slack
* Clock frequency
* Critical path delay

### Area

* Standard cell area
* Cell count
* Utilization

---

# 🛠️ Tools Used

| Tool                | Purpose                 |
| ------------------- | ----------------------- |
| Verilog HDL         | RTL Design              |
| Cadence Genus       | Logic Synthesis         |
| Cadence Conformal   | Formal Verification     |
| Innovus             | Physical Design         |
| STA Tool            | Timing Analysis         |
| GTKWave / Simulator | Functional Verification |

---

# 📂 Repository Structure

```text
RTL-GDS-Flow-Digital-Alarm-Clock/
│
├── RTL/
│   ├── alarm_clock.v
│   ├── testbench.v
│
├── Simulation/
│   ├── waveforms/
│   ├── coverage_reports/
│
├── Synthesis/
│   ├── constraints/
│   ├── reports/
│
├── Formal_Verification/
│   ├── equivalence_reports/
│
├── STA/
│   ├── setup_reports/
│   ├── hold_reports/
│
├── DFT/
│   ├── scan_reports/
│
├── Physical_Design/
│   ├── floorplan/
│   ├── placement/
│   ├── CTS/
│   ├── routing/
│   ├── signoff/
│   └── GDS/
│
└── README.md
```

# 📊 Results

✔ Functional verification passed
✔ High simulation coverage achieved
✔ Successful synthesis under multiple constraints
✔ Timing closure achieved
✔ Formal equivalence verified
✔ DFT scan insertion completed
✔ RTL-to-GDS physical implementation completed

---

# 🚀 How to Run

### Clone Repository

```bash
git clone https://github.com/neeti25130/RTL-GDS-Flow-Digital-Alarm-Clock.git
```

### Navigate to Folder

```bash
cd RTL-GDS-Flow-Digital-Alarm-Clock
```

### Run Simulation

Compile RTL and testbench using your preferred Verilog simulator.

### Run Synthesis

Use Cadence Genus scripts for synthesis.

### Run Physical Design

Execute Innovus flow scripts for placement, CTS, routing, and GDS generation.

---


