# 🛰 Contributing to AEROSPACE CORE

First off, thank you for considering contributing to **AEROSPACE CORE**. As an Expert Aerospace & Full-Stack Systems project, we maintain high standards for physical accuracy and UI consistency.

By contributing, you agree to abide by our **Integrity Lock** protocols.

---

## 📜 Technical Standards & Protocol

To maintain the evolution of the codebase without losing existing functionalities, all contributors must follow these three pillars:

### 1. The Superset Rule
Every update must be a **superset** of the previous version. You are strictly forbidden from "cleaning up" code if it results in the loss of:
* Visual elements or UI buttons.
* Physical calculations (even if they seem redundant).
* Telemetry data points.

### 2. Physics Calibration
If you are modifying the `updatePhysics` function:
* Ensure the **Earth/Moon GM constants** remain NASA-standard.
* Verify that **TLI Phase Angle** math ($0.65$ rad) still results in a successful lunar intercept.
* New orbits (e.g., Molniya or Tundra) must be calculated using the existing `SCALE` constant ($1/15000$).

### 3. Cyber-Aero HUD Aesthetic
The UI must remain mission-ready:
* **Typography:** Always use `JetBrains Mono`.
* **Colors:** Use the defined CSS variables (`--neon`, `--safe`, `--warn`, `--danger`).
* **Language:** All telemetry and system logs must be in **English Technical** (NASA/SPX Format).

---

## 🛠 How to Contribute

### Reporting Bugs
1.  Check the **Mission Log** (Terminal) in the HUD for error codes.
2.  Open an Issue with the prefix `[BUG]`.
3.  Include your **Warp Speed** and **Mission State** (e.g., `TRANSIT`, `DESCENT`) at the time of the error.

### Feature Requests
1.  Open an Issue with the prefix `[PROPOSAL]`.
2.  Define the **Delta Analysis**: How will the new feature interact with the current `Feature Manifest`?
3.  Identify the **Injection Point** in the existing state machine.

### Pull Requests
1.  **Full File Only:** Since the project is a zero-dependency single-file build, provide the full `index.html` in your PR description for rapid testing.
2.  **Validation:** Confirm that the Lunar landing is still achievable with your changes.
3.  **Documentation:** Update the `README.md` Feature Manifest if you add new hardware or orbital layers.

---

## 🏗 Development Environment

* **No Build Step:** This is a vanilla JS project. Just a browser and a text editor are required.
* **Dependencies:** Only external CDNs allowed (`three.js`, `OrbitControls.js`). Do not add `npm` packages that require a bundler.

---

## ⚖️ Code of Conduct
We follow a professional, engineering-first approach. Be respectful, be technical, and keep the mission status **NOMINAL**.

**Fly safe.**
