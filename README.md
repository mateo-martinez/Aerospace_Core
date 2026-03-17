# AEROSPACE CORE v23.4: Lunar Expedition Simulator 🚀

**Lead Engineer:** Mateo Martínez  
**Project Status:** `OPERATIONAL`  
**Mission Phase:** Surface Exploration (MSE-1)  
**License:** [AGPL-3.0](https://opensource.org/licenses/AGPL-3.0)

---

## 1. Project Overview
**AEROSPACE CORE** is a high-fidelity, browser-based orbital mechanics and lunar landing simulator developed using **Three.js** and vanilla JavaScript. The project simulates a multi-stage mission from Earth liftoff to the deployment of a **Mobile Surface Explorer (MSE-1)** rover on the Lunar South Pole.

The simulator utilizes a custom physics engine to calculate gravitational vectors, orbital velocities, and TLI (Trans-Lunar Injection) trajectories in real-time.

---

## 2. Technical Architecture

### 2.1 Physics Engine & Scaling
To maintain visual coherence while respecting astronomical proportions, the system uses a dual-scale approach:
* **Distance Scaling:** $1 \text{ Unit} = 15,000 \text{ km}$
* **Time Scaling:** Variable via the **Warp Drive** (1x to 1500x)
* **Gravitational Constants:**
    * Earth ($GM_E$): $398,600 \text{ km}^3/\text{s}^2$
    * Moon ($GM_M$): $4,902 \text{ km}^3/\text{s}^2$
    * Earth Radius ($R_E$): $6,371 \text{ km}$
    * Moon Radius ($R_M$): $1,737 \text{ km}$

### 2.2 Numerical Integration
The engine uses **Euler Integration** with a sub-stepping protocol ($50 \text{ iterations per frame}$) to ensure stability during high-velocity transits and high Warp Drive settings.
$$\vec{a} = \sum \frac{-GM}{r^2} \cdot \hat{r}$$
$$\vec{v}_{t+1} = \vec{v}_t + \vec{a} \cdot \Delta t$$

### 2.3 Lunar Capture Logic (SOI)
The simulator implements an aggressive **Sphere of Influence (SOI)** capture. When the craft enters the $120,000 \text{ km}$ Lunar radius, the guidance system transitions from Earth-centric to Lunar-centric, applying an artificial gravity assist to ensure capture even at sub-optimal intercept angles.

---

## 3. Mission Phases & Operating Manual

### Phase 1: Pre-Launch (T-10 Sequence)
Upon initiating the sequence, the system performs a 10-second automated check of all subsystems.
* **T-10:** Internal Power Switch.
* **T-7:** Flight computer startup.
* **T-3:** Engine ignition sequence start.

### Phase 2: Ascent & Orbital Insertion
The craft climbs to a $400 \text{ km}$ LEO (Low Earth Orbit).
* **Action:** Monitor logs for "Atmospheric Exit."
* **Requirement:** Velocity must stabilize at $\approx 7.6 \text{ km/s}$ before Staging.

### Phase 3: Trans-Lunar Injection (TLI)
The most critical burn. The system calculates a Hohmann-like transfer trajectory.
* **Action:** Execute TLI Burn.
* **Safety:** Do not exceed 1000x Warp during transit to avoid "collision tunneling" through the Lunar mesh.

### Phase 4: Lunar Descent & Touchdown
The craft detects the Lunar surface at $1 \text{ km}$ altitude.
* **Landing Criteria:** Relative velocity must reach $0.000 \text{ km/s}$.
* **Status:** `LANDED` indicator will turn green, unlocking Rover deployment.

### Phase 5: Surface Exploration (MSE-1)
Deploy the Rover to begin resource scanning.
* **Sensors:** Helium-3 and Water Ice spectrometer active.
* **Data:** Logs will report geological anomalies and deposit coordinates in real-time.

---

## 4. Key Features
* **Deep Space Network (DSN) Verbose Logs:** Real-time telemetry reporting in standard NASA/SpaceX English terminology.
* **Lagrange Point Visualization:** Real-time calculation of L1, L2, L4, and L5 stability wells between Earth and Moon.
* **AES-256 Telemetry Encryption:** Simulated secure data link for mission integrity.
* **Trajectory FDR (Flight Data Recorder):** Visual path tracing of the entire mission profile.

---

## 5. Controls & HUD
| Component | Function |
| :--- | :--- |
| **Mission Ops Panel** | Sequential control of flight stages (1-5). |
| **Warp Slider** | Controls simulation speed (Time Compression). |
| **Telemetry Panel** | Real-time monitoring of Distance, Velocity, and Resource Scan %. |
| **OrbitControls** | Mouse Left (Rotate), Mouse Right (Pan), Scroll (Zoom). |

---

## 6. Installation
1.  Clone the repository:
    ```bash
    git clone [https://github.com/your-username/aerospace-core.git](https://github.com/your-username/aerospace-core.git)
    ```
2.  Open `index.html` in any modern web browser (Chrome/Edge recommended).
3.  Ensure an active internet connection for the Three.js CDN and texture assets.

---
**"Per Aspera ad Astra."** *Developed for the exploration of new frontiers.*
