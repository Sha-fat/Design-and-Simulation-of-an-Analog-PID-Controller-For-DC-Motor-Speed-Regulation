
# DC Motor Speed Control System with Analog PID and Disturbance Rejection Analysis

This repository contains the simulation files, documentation, and presentation materials for the closed-loop speed regulation of a DC motor using an analog operational amplifier-based PID controller. The design evaluates tracking performance, parametric behavior, and transient recovery under external load torque disturbances.

---

## Repository Contents

* **`PSpice/`**: Contains the standalone schematic files (`.sch`) for the three test setups[cite: 4]:
  * `PID_MotorSpeed.sch`: Baseline transient step response analysis[cite: 4].
  * `PID_MotorSpeed_param.sch`: Parametric sweep analysis for controller tuning and variation[cite: 4].
  * `PID_MotorSpeed_Disturbance rejection.sch`: Load torque step disturbance rejection analysis[cite: 4].
* **`Proposal/`**: Project proposal document detailing system objectives, motor parameters, and circuit design strategy.
* **`Report/`**: Comprehensive project report containing full theoretical derivations, complete circuit diagrams, waveform plots, and tabulated performance metrics.
* **`Presentation/`**: Slide deck covering the design methodology, component selection, and performance evaluation.

---

## Project Overview

The closed-loop control system consists of:
1. **Differential Error Amplifier**: Compares the reference speed setpoint against the tachometer feedback voltage[cite: 1].
2. **Analog PID Controller**:
   * **Proportional Stage ($K_p$)**: Provides immediate proportional correction[cite: 1].
   * **Integral Stage ($K_i$)**: Eliminates steady-state speed error[cite: 1].
   * **Derivative Stage ($K_d$)**: Improves phase margin and transient damping[cite: 1].
3. **Power Stage Driver**: Push-pull transistor driver feeding the motor armature circuit[cite: 1].
4. **DC Motor Electromechanical Plant**:
   * Electrical domain: Armature resistance ($R_a$), inductance ($L_a$), and back-EMF source ($E_b$)[cite: 1, 3].
   * Mechanical domain analog: Equivalent capacitance for rotor inertia ($J$) and resistance for viscous damping friction ($B$)[cite: 1, 3].
   * Disturbance modeling: Pulsed current injection source to simulate external mechanical load steps[cite: 1, 3].

*For complete data tables, disturbance rejection values, and graphical waveforms, please refer to the document in the `Report/` directory.*

---

## Project Demonstration & Video

A complete walkthrough of the circuit schematics, simulation setups, and response verification is available on YouTube:

[![Project Demonstration Video](https://img.shields.io/badge/YouTube-Watch%20Demo-red?style=for-the-badge&logo=youtube)](YOUR_YOUTUBE_VIDEO_LINK_HERE)

> **Link:** [YOUR_YOUTUBE_VIDEO_LINK_HERE](YOUR_YOUTUBE_VIDEO_LINK_HERE)

---

## How to Run the Simulations

1. Open **Schematics** (PSpice / OrCAD)[cite: 4].
2. Go to **File > Open** and select the desired schematic file from the `PSpice/` folder[cite: 4]:
   * **`PID_MotorSpeed.sch`** to observe standard nominal step response[cite: 4].
   * **`PID_MotorSpeed_param.sch`** to run component sweeps[cite: 4].
   * **`PID_MotorSpeed_Disturbance rejection.sch`** to observe load torque disturbance rejection[cite: 4].
3. Click **Analysis > Simulate** (or press the **Simulate** button / `F11`).
4. In Probe, trace `V(SPEED)` to view system speed tracking and response dynamics[cite: 1, 3].

