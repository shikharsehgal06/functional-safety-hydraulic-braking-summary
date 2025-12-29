# Functional Failure Mode and Effects Analysis (FMEA)

A functional failure mode effect analysis (FMEA) identifies subsystem-level potential failures that will cause the safety goals to be violated as defined by ISO.

## Failure Mode Analysis by Component

| Component | Potential Failure Mode | Potential Effect (Hazard) | Potential Cause / Mechanism |
| :--- | :--- | :--- | :--- |
| **CHB Control Module** | Arbitration Logic Fault. | Improper resolution of conflicting commands leading to H4. | Firmware crash or corrupted software parameters. |
| **WSS (Wheel Speed Sensor)** | Stuck at same reading / No signal. | Loss of ABS function; potential wheel lock-up (H3). | Internal IC short, open circuits, or EMI/ESD disturbances. |
| **Brake Modulator** | Valves stuck open or closed. | Insufficient braking force (H5) or unintended braking (H4). | Hardware actuator failure or power supply disruption. |
| **Brake Pressure Sensor** | Out of range or offset signal. | Inaccurate pressure calculation leading to unintended deceleration. | Signal connector failure or internal connection short. |
| **Yaw Rate Sensor** | Inverted or missing signal. | Unintended yaw/lateral motion (H1) or insufficient stability control. | Electromagnetic interference (EMI) or sensor misalignment. |



## Safety Strategy (Safe States)

When the FMEA identifies these failed actions, the system will transition into a safe state during a fault-tolerant time interval (FTTI) which typically falls within the range of 150-250 milliseconds:

* **Safe State 3**: The ABS feature is disabled.
* **Safe State 5**: All electronic braking interventions are disabled, and the system will revert to using the mechanical hydraulic service brake.
