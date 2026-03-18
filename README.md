# 🚀 AEROSPACE CORE v25.1.0: LUNAR ASCENDANT

[![License: MIT](https://img.shields.io/badge/License-MIT-00f2ff.svg)](https://opensource.org/licenses/MIT)
[![Engine: Three.js](https://img.shields.io/badge/Engine-Three.js%20r128-00ff88)](https://threejs.org/)
[![Type: Aerospace Simulation](https://img.shields.io/badge/Sector-Aerospace%20%26%20Defense-ff3333)](https://github.com/)

**AEROSPACE CORE** is a high-fidelity, browser-based orbital mechanics simulator and mission control interface. Designed by an Expert Aerospace & Full-Stack Systems Engineer, this platform bridges the gap between complex physical calculations and high-performance "Cyber-Aero" UI/UX.

---

## 🛠 Feature Manifest

### 🪐 Orbital & Celestial Mechanics
* **Multi-Mission Logic:** Integrated support for LEO (400km), MEO (20,200km), GEO (35,786km), and Artemis-style Lunar trajectories.
* **N-Body Approximation:** Real-time Earth/Moon gravity modeling including Sphere of Influence (SOI) transition and Lunar capture.
* **Navigation Landmarks:** Dynamic visualization of Lagrange Points (L1, L2, L4, L5), the Karman Line, and the Van Allen Radiation Belts.
* **Trajectory Tracking:** Long-exposure orbital path rendering (1,000,000-point buffer).

### 🚀 Hardware & Mission Library
* **Launch Vehicles:**
    * **SpaceX Falcon 9:** Reusable medium-lift for LEO/Starlink missions.
    * **SpaceX Starship:** Super-heavy lift for deep-space and lunar landing.
    * **NASA SLS Block 1:** Deep-space exploration platform for the Orion MPCV.
* **Payloads:** Real-world technical specifications for **Starlink V2**, **GPS III**, **ViaSat-3**, and **Artemis III** mission profiles.

### 🎮 Mission Control (HUD)
* **Real-Time Telemetry:** NASA-SPEC tracking of relative velocity (KM/S), phase angles, and lunar range.
* **Automated TLI Window:** Physics-driven Trans-Lunar Injection calculator using a 0.65 rad phase angle lock for precise lunar intercept.
* **Surface Operations:** Deployable **MSE-1 Rover** with autonomous resource scanning for Helium-3 and Water Ice.

---

## ⚙️ Technical Specifications

### Physics Kernel
The simulation utilizes a sub-stepped Euler integration method ($n=60$) to ensure trajectory stability during high-speed time warping.

| Parameter | Value |
| :--- | :--- |
| **Earth Gravity ($GM_E$)** | $398,600 km^3/s^2$ |
| **Lunar Gravity ($GM_M$)** | $4,902 km^3/s^2$ |
| **Distance Scaling** | $1:15,000$ |
| **Escape Velocity ($V_e$)** | $\approx 10.9 km/s$ (for TLI) |
| **Simulation Warp** | 1x to 2500x Acceleration |

### Tech Stack
* **Core:** Vanilla JavaScript (ES6+)
* **Graphics:** WebGL via **Three.js r128**
* **Controls:** OrbitControls.js
* **Typography:** JetBrains Mono (Standardized HUD font)

---

## 🕹 Operation Manual

### 1. Mission Configuration
Select your **Launch Vehicle** and **Payload** from the sidebar. Each selection updates the internal flight computer with the correct `targetOrbitAlt`. Click on the hardware names to view live NASA/SPX specification logs.

### 2. Launch Sequence
Execute the **Pre-Flight Diagnostic**. Once "MISSION GO" is confirmed, initiate the **T-10 Sequence**. The core handles the gravity turn automatically until target altitude is reached.

### 3. Deployment
Once in a stable orbit (LEO/MEO/GEO), perform **Stage Separation** and **Solar Bus Deployment**. Deploying panels is critical for maintaining bus voltage during deep space transit.

### 4. Trans-Lunar Injection (TLI)
For Lunar missions, click **"Arm Auto-TLI Burn"**. The Guidance computer calculates the phase angle relative to the Moon's orbital position. The system will auto-ignite at the optimal window to ensure capture.

### 5. Lunar Surface
Upon touchdown, release the **MSE-1 Rover**. Monitor battery levels while scanning for Helium-3 and Water Ice resources.

---

## 📂 Installation & Deployment

This is a zero-dependency, single-file production build.

1.  Clone the repository:
    ```bash
    git clone [https://github.com/youruser/aerospace-core.git](https://github.com/youruser/aerospace-core.git)
    ```
2.  Open `aerospace-core-v25.1.0.html` in any modern, WebGL-enabled browser.

---

## ⚖️ License
Distributed under the MIT License. See `LICENSE` for more information.

---
**Mission Status: Nominal.**
