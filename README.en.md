<p align="center">
  <a href="README.md">Русский</a> | <b>English</b> | <a href="README.de.md">Deutsch</a>
</p>

# Microstrip Line Simulation and Calculation

This repository contains the design, analytical calculation, and 3D electromagnetic simulation results of a microstrip transmission line optimized to operate at **1.015 GHz**.

The project includes the mathematical synthesis of the line geometry for a standard 50-Ohm system, CAD modeling, and full-wave analysis of the matching characteristics using numerical simulation.

---

## Project Structure

* `/cad` — 3D CAD models of the structure in SolidWorks (`.sldprt`) and neutral (`.step`) formats.
* `/calculations` — analytical calculations of the line parameters in Mathcad (`.xmcd`).
* `/simulation` — full-wave electromagnetic analysis project in CST Studio Suite (`.cst`).
* `/docs/images` — graphical results of calculations and frequency response plots.

---

## Analytical Parameter Calculation

Mathematical calculation of the geometric parameters was performed in Mathcad. A 1 mm thick dielectric substrate with a relative permittivity of $\varepsilon = 3.38$ was selected.

![Analytical Calculation](docs/images/calc_microstrip_analytical.png)

### Specifications and Calculated Parameters:
* **Target Characteristic Impedance ($Z_B$):** 50 Ohm
* **Strip Width ($b$):** 4.098 mm
* **Cutoff Frequency of Higher-Order Mode ($F_{crit}$):** 82.15 GHz
* **Attenuation Coefficient ($\alpha$):** 0.345 dB/m

---

## 3D Model and Geometry

Based on the calculated dimensions, a coupled microstrip structure was designed on a dielectric substrate with a ground plane. RF signal excitation is achieved using Discrete Ports.

![3D Model in CST](docs/images/simulation_3d_model.png)

---

## Electromagnetic Simulation Results

The frequency response analysis was performed in the 0.8–1.2 GHz range. The optimal matching frequency of the structure is identified at $f_0 = 1.015$ GHz.

### Key Parameters at 1.015 GHz:

| Parameter | Symbol | Value | Description |
| :--- | :---: | :---: | :--- |
| Reflection Coefficient | S11 | -28.86 dB | Low reflection level, confirming proper matching. |
| VSWR | VSWR1 | 1.086 | Value remains close to unity across the operating band. |
| Input Impedance | Z11 | 50.49 Ohm | Corresponds to the standard 50-Ohm system. |

---

## Frequency Response Analysis

<details open>
  <summary><b>1. Reflection Coefficient (S11)</b></summary>
  <br>
  
  <img src="docs/images/simulation_s_parameters.png" alt="S-Parameters" width="100%"/>

  * **Analysis:** At 1.0136–1.015 GHz, the resonance depth is -28.86 dB, indicating minimal power loss due to reflection.
  * **Bandwidth:** At the standard -10 dB level, the matched bandwidth spans from approximately 0.97 GHz to 1.06 GHz.
</details>

<details open>
  <summary><b>2. Voltage Standing Wave Ratio (VSWR)</b></summary>
  <br>
  
  <img src="docs/images/simulation_vswr.png" alt="VSWR" width="100%"/>

  * **Analysis:** At the operating frequency of 1.015 GHz, the VSWR is 1.086, indicating high matching quality.
</details>

<details open>
  <summary><b>3. Input Impedance (Z11)</b></summary>
  <br>
  
  <img src="docs/images/simulation_z_parameters.png" alt="Input Impedance" width="100%"/>

  * **Analysis:** The input impedance magnitude at 1.015 GHz is 50.49 Ohm, ensuring seamless integration with standard 50-Ohm components.
</details>

## License

Copyright (c) 2026 Ilya Kornilov

This source describes Open Hardware and is licensed under the CERN-OHL-P v2. 
You may redistribute and modify this source and make products using it under 
the terms of the CERN-OHL-P v2 (https://cern.ch/cern-ohl).

This source is distributed WITHOUT ANY EXPRESS OR IMPLIED WARRANTY, 
INCLUDING OF MERCHANTABILITY, SATISFACTORY QUALITY AND FITNESS FOR A 
PARTICULAR PURPOSE. Please see the CERN-OHL-P v2 for applicable conditions.