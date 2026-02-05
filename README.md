# quanser-aero2-cascade-control-Control-Systems
Cascade PI–PID control of Quanser Aero2 dual-rotor system with system identification and hardware validation.

# 🚁 Quanser Aero2 Cascade Control (PI–PID)

This project presents modelling and cascade control design of a Quanser Aero2 dual-rotor system configured in a 1-DOF pitch setup.

The workflow includes:
- System identification from step response data
- Model validation against physical hardware
- PI control of rotor speed (inner loop)
- PID control of pitch angle (outer loop)
- Analysis of simulation vs real-world behavior

📄 Full report: `report/Control_Fundamentals_Coursework_Ben.pdf`

---

## System Identification

### Rotor Subsystem (Inner Loop)
Identified as a first-order system using step response:

- Gain: K = 18.704  
- Time constant: τ = 1.16 s  

Model:
G(s) = 18.704 / (1.16s + 1)

Validation showed physical response faster than simulation due to higher-order dynamics and nonlinear effects.

---

### Pitch Subsystem (Outer Loop)

Modeled as second-order using free oscillation:

- Natural frequency: ωₙ = 0.735 rad/s  
- Damping ratio: ζ = 0.0167  

Observed phase shift and amplitude differences between simulation and hardware due to unmodelled friction and varying damping.

---

## Cascade Control Architecture

### Inner Loop — Rotor Speed (PI)

- kp = 0.027  
- ki = 0.099  

Simulation met specifications, but physical system showed faster rise and reduced overshoot due to additional damping.

---

### Outer Loop — Pitch Angle (PID)

Final tuned gains:

- kp = 5.5  
- ki = 20  
- kd = 40  

Simulation achieved smooth tracking.  
Physical system exhibited oscillatory transient before settling near 0.3 rad, attributed to high integral action and limited derivative damping.

---

## Key Engineering Insights

- Real systems deviate from simplified models due to friction, air resistance, and nonlinear dynamics
- High integral gain reduces steady-state error but introduces oscillations
- Cascade control enables separation of fast actuator dynamics from slower mechanical motion
- Hardware validation is essential to reveal modelling limitations

---

## Tools Used

- MATLAB / Simulink
- QUARC (hardware interface)
- Quanser Aero2 platform

---

## Skills Demonstrated

- System identification
- Cascade control design
- PI/PID tuning
- Hardware-in-the-loop validation
- Control theory applied to physical systems

---

## Author

Ben Paul Richard
