# ⚡ Electrical Machines and Drives

### MATLAB/Simulink Modelling, Analysis & Motor Drive Simulation

This project explores the modelling, simulation and analysis of **DC machines, induction motors and electric motor drives** using **MATLAB and Simulink**.

The project applies fundamental electrical machine theory to practical simulation models, examining motor characteristics, speed control, electromagnetic torque, back EMF, power conversion, efficiency and variable-speed operation.

---

## 📌 Project Overview

The project investigates the behaviour and control of both **DC and AC electrical machines** through mathematical analysis and MATLAB/Simulink simulations.

The main areas investigated include:

- Separately excited DC machine
- Armature voltage speed control
- Back EMF measurement and analysis
- Series DC motor characteristics
- Series motor reversal and no-load operation
- DC motor field weakening
- Buck-converter-fed DC motor drive
- Ideal vs. real power semiconductor switching
- Induction motor equivalent-circuit analysis
- Induction motor power loss and efficiency
- Three-phase PWM inverter control
- Variable-speed induction motor operation

---

## 🛠️ Tools & Technologies

- MATLAB
- Simulink
- MATLAB scripting
- Electrical machine modelling
- Power electronics
- DC motor drives
- AC induction motor drives
- PWM inverter control
- Mathematical modelling
- Simulation and data analysis

---

# 1. 🔄 DC Machine – Armature Voltage Control

A separately excited DC machine was modelled in Simulink to investigate the relationship between **armature voltage and rotor speed**.

The simulations were performed using different armature voltages while maintaining a constant field voltage and mechanical load.

### Key Concepts

- Armature voltage control
- Back EMF
- Electromagnetic torque
- Rotor speed
- Armature current

### Simulation Conditions

| Parameter | Value |
|---|---:|
| Field Voltage | 300 V |
| Mechanical Load | 60 Nm |
| Armature Voltage | 500 V, 300 V, 50 V |

### Key Result

The simulation demonstrated that, under constant field flux and load conditions, increasing the armature voltage results in an increase in steady-state motor speed.

The **500 V** case reached approximately **180 rad/s**, while the **300 V** case reached approximately **105 rad/s**.

---

# 2. 🔧 Series DC Motor

The DC machine was reconfigured as a **series motor** to investigate its characteristic high starting torque and behaviour under different operating conditions.

The analysis included:

- Series motor operation
- Motor reversal
- No-load operation
- Starting behaviour
- Torque characteristics

A key engineering consideration demonstrated by the simulation is the potentially dangerous **runaway condition** of a series motor when operated without an appropriate mechanical load.

---

# 3. 📈 DC Motor Field Weakening

Field weakening was investigated by maintaining a constant armature voltage while reducing the field excitation.

The simulation demonstrates the inverse relationship between magnetic flux and motor speed:

> Reducing field flux allows the motor to operate above its normal base speed.

The model used a variable resistance in the field circuit to control field current.

### Simulation Conditions

The field resistance was varied across multiple operating conditions while maintaining a **500 V armature supply** and a **50 Nm mechanical load**.

### Engineering Observation

Weakening the field increases the speed capability of the motor but can also result in significantly increased armature current when the available electromagnetic torque becomes insufficient for the mechanical load.

This demonstrates an important limitation of field-weakening control.

---

# 4. ⚡ Buck Converter DC Motor Drive

A DC motor drive was developed using a **DC/DC buck converter**.

The model was used to investigate the relationship between:

- Converter output voltage
- Armature current
- Motor speed
- Back EMF
- Input power
- Output power
- Mechanical power
- Overall efficiency

The converter was evaluated using both **ideal and realistic switching devices**.

### Ideal Switching Case

The ideal model produced an output voltage of approximately **350 V** and demonstrated the expected transient motor behaviour.

The simulation produced:

| Parameter | Approximate Value |
|---|---:|
| Converter Input Power | 4848 W |
| Converter Output Power | 4847 W |
| Mechanical Power | 4404 W |

The near-unity converter efficiency illustrates the expected behaviour of an idealised switching model.

### Real Switching Case

Realistic semiconductor characteristics were introduced using device conduction losses.

The simulation demonstrated a reduction in converter output voltage due to:

- MOSFET on-state resistance
- Diode forward voltage
- Semiconductor conduction losses

This provided a comparison between theoretical ideal switching and practical power-electronic behaviour.

---

# 5. 🌀 Induction Motor Equivalent Circuit

The project also investigated the steady-state performance of an **AC induction motor** using its equivalent circuit.

The analysis examined:

- Slip
- Rotor speed
- Stator current
- Rotor current
- Power transfer
- Copper losses
- Mechanical power
- Power factor
- Efficiency

MATLAB was used to calculate motor performance across a range of slip values.

### Motor Parameters

The model included parameters such as:

- Stator resistance
- Stator reactance
- Rotor resistance
- Rotor reactance
- Mutual reactance
- Supply voltage
- Electrical frequency
- Number of pole pairs

---

# 6. 🎛️ Three-Phase PWM Induction Motor Drive

A three-phase PWM inverter was developed to control the speed of a squirrel-cage induction motor.

The system consisted of:

```text
DC Source
    │
    ▼
3-Phase PWM Inverter
    │
    ▼
Induction Motor
    │
    ▼
Fan-Type Mechanical Load
