# Smart Water Level Control System | MATLAB Simulink

A closed-loop water level control system developed using MATLAB Simulink and Simscape Fluids, featuring PID-based control, physical tank modeling, and real-time simulation monitoring.

## Overview

This project focuses on the modeling, simulation, and control of a liquid storage tank using feedback control principles. A PID controller regulates the inlet valve based on the difference between the desired and measured water levels.

The system integrates Simulink control logic with Simscape Fluids physical components to simulate tank dynamics, fluid flow, and water level regulation.

## Key Features

- **Closed-Loop Control:** Feedback-based water level regulation using a PID controller.
- **Physical System Modeling:** Tank and fluid network modeled using Simscape Fluids.
- **Valve Control:** Inlet flow regulated through a controllable Local Restriction (IL) component.
- **System Monitoring:** Water level and liquid volume monitored during simulation.
- **Dynamic Response Analysis:** Transient response, overshoot, and steady-state behavior evaluated through simulation.

## System Architecture

The model consists of two interconnected subsystems:

**1. Control Subsystem**
- Reference water level
- Error calculation and feedback
- PID controller
- Gain block and Simulink-PS signal conversion

**2. Physical Plant Subsystem**
- Tank (IL)
- Controllable inlet restriction
- Outlet restriction
- Fluid reservoirs
- Level and volume measurement outputs

### Control Strategy

The measured water level is compared with the reference setpoint to generate an error signal:

\[
e(t) = h_{\mathrm{ref}} - h(t)
\]

The PID controller processes the error and generates a control signal for the inlet valve.

The controller uses the parallel PID formulation:

\[
u(t) = K_p e(t) + K_i \int e(t)\,dt + K_d \frac{de(t)}{dt}
\]

where:
- \(h_{\mathrm{ref}}\) is the reference water level.
- \(h(t)\) is the measured water level.
- \(K_p\), \(K_i\), and \(K_d\) are the PID controller gains.

## Simulation Configuration

| Parameter | Value |
|---|---:|
| Reference water level | 0.35 m |
| Tank cross-sectional area | 0.02 m² |
| Maximum tank capacity | 100 L |
| Proportional gain, \(K_p\) | 5 |
| Integral gain, \(K_i\) | 0.2 |
| Derivative gain, \(K_d\) | 0 |
| Controller type | Continuous-time PI |
| Simulation duration | 100 s |

*Note: The controller is configured as a PI controller because the derivative gain is zero.*

## Simulation Results

The model was simulated to evaluate the tank's water level and volume responses under closed-loop control.

### Water Level Response

The simulated water level rises toward the reference setpoint, exhibits a small overshoot, and subsequently approaches the target level.

- **Reference level:** 0.35 m
- **Observed peak level:** Approximately 0.368 m
- **Level at 100 s:** Approximately 0.35 m

### Volume Response

The simulated liquid volume increases during filling, reaches a peak, and gradually approaches a steady operating value as the inlet and outlet flows balance.

### Simulation Visualizations

Add the following images to the `images/` directory:

| Visualization | File |
|---|---|
| Complete Simulink model | `images/system_model.png` |
| Water level response | `images/level_response.png` |
| Water volume response | `images/volume_response.png` |

#### System Model

![System Model](https://github.com/barathvaj-kv/Simscape-Water-Tank-Level-Control/blob/86f7c492edfca11eae9e6903bdf8f66e29bf1315/Images/system_model.png)

#### Water Level Response

![Water Level Response](https://github.com/barathvaj-kv/Simscape-Water-Tank-Level-Control/blob/86f7c492edfca11eae9e6903bdf8f66e29bf1315/Images/level_response.png)

#### Water Volume Response

![Water Volume Response](https://github.com/barathvaj-kv/Simscape-Water-Tank-Level-Control/blob/86f7c492edfca11eae9e6903bdf8f66e29bf1315/Images/volume_response.png)

## Technologies and Tools

- MATLAB
- Simulink
- Simscape
- Simscape Fluids
- PID / PI Control
- Feedback Control Systems
- Dynamic System Simulation

## How to Run

1. Clone or download this repository.
2. Open MATLAB with the required Simulink and Simscape products installed.
3. Open `Smart_Water_Level_Control.slx`.
4. Load any required supporting files or workspace variables.
5. Run the simulation.
6. Examine the water level and volume outputs.

## Engineering Skills Demonstrated

- Feedback control system design
- PID controller configuration
- Physical system modeling using Simscape Fluids
- Integration of Simulink control signals with physical networks
- Simulation-based performance evaluation
- Analysis of transient and steady-state responses

## Future Development

- Implement interactive setpoint adjustment through a dashboard.
- Tune controller parameters to improve transient response.
- Introduce high-level and low-level alarm logic.
- Evaluate performance under varying inlet and outlet conditions.
- Investigate overflow prevention and fault detection.

---

**Project Domain:** Control Systems | Process Automation | System Modeling and Simulation
