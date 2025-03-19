# RCAM-RealTime-FlightSim-Visualization 🚀

### Real-Time Flight Simulation with Variable Mass and Visualization

This project visualizes the **RCAM (Research Civil Aircraft Model)** in a **real-time flight simulation** with **keyboard-based control** and **variable mass implementation**. The simulation aims to analyze flight dynamics while incorporating mass changes, useful for scenarios such as **fuel tank drops** or **payload releases**.

---

## ✈️ Features

- **Real-Time Keyboard-Based Control**  
- **Variable Mass Implementation** (simulating fuel drop effect)  
- **Live Aircraft Visualization** using **NASA HL-20 Model visualization block**  
- **Simulink Model with 4 Scopes** (Inputs, States, Position, Geocentric Coordinates)  
- **Future Expandability** (X-Plane / FlightGear integration)

---

## 🕹️ Keyboard Controls

A custom MATLAB function (`keyboard_control_live`) captures **real-time keyboard inputs** and converts them into a **6-element control vector**.

| Key  | Control |
|------|---------|
| ⬆️⬇️ Left/Right | **Aileron (dA) & Elevator (dT)** |
| A / D | **Rudder (dR)** |
| W / S | **Throttle (dth1, dth2)** |
| Space | **Toggle Mass Drop (u6)** |

Each control input updates dynamically as `u_dynamic = u0 + control_input`, where `u0` represents the trim control inputs.

---

## 🛠️ Variable Mass Implementation

The **RCAM model** was **modified** to include a **mass variation** feature. The **sixth control input (`u6`)** acts as a toggle for mass reduction:

- **`u6 = 0`** → **m = 120,000 kg** (Initial mass)
- **`u6 = 1`** → **m = 90,000 kg** (Reduced mass)

This **simulates a fuel tank drop** without affecting the **aircraft’s aerodynamics** or **center of gravity** (assuming the dropped weight is aligned with the CG). The mass reduction allows analysis of performance changes due to weight loss.

---

## 🎥 Visualization & Scopes

The aircraft’s motion was **visualized** using the **NASA HL-20 Model visualization block**. Additionally, **four Simulink scopes** were implemented to monitor aircraft behavior:

- **Control Inputs Over Time**: Tracks variations in **dA, dT, dR, dth1, dth2, u6**  
- **State Variables (9 States)**: **u, v, w, p, q, r, ϕ, θ, ψ**  
- **Position (NED Frame)**: Monitors **PN, PE, PD**  
- **Geocentric Coordinate Evolution**: Tracks **Latitude, Longitude, and Altitude**, enabling potential **X-Plane or FlightGear integration**

---

## 🏁 Trim Initialization

The aircraft was initialized in **level flight at 85 m/s**, with predefined **trim values** for stability:

### **State Vector (`X0`)** **[12×1]**
