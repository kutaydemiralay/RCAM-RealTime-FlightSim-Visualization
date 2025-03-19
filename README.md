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

A custom MATLAB function (`keyboard_control_live`) was implemented to capture **real-time keyboard inputs** and convert them into a **6-element control vector**.

| Key  | Control |
|------|---------|
| ⬆️⬇️ Left/Right | **Aileron (dA) & Elevator (dT)** |
| A / D | **Rudder (dR)** |
| W / S | **Throttle (dth1, dth2)** |
| Space | **Toggle Mass Drop (u6)** |

Each control input updates dynamically as:

