# 📡 PMUT FEM Simulation using COMSOL

This repository contains a finite element simulation of a Piezoelectric Micromachined Ultrasonic Transducer (PMUT), carried out using COMSOL Multiphysics. The goal is to analyze the static and dynamic mechanical behavior of the device, estimate resonance frequencies, and validate design parameters for a target working frequency of **6 MHz**.

## 📘 About the Simulation
This software analyzes physics-based numerical problems by dividing the geometric domain into finite elements (meshing) and solving the associated partial differential equations.

The project includes Multiple Physics: Solid Mechanics, Electrostatic and Piezoelectric effect
- ✅ **Stationary simulations**: for static deformation and stress
- ✅ **Eigenfrequency studies**: to calculate natural oscillating frequencies
- ✅ **Parametric sweeps**: to evaluate how the PMUT membrane radius affects resonance frequency 

## 🎯 Objective

- Characterize PMUT behavior under excitation
- Achieve a working frequency near **6 MHz**
- Optimize geometry for fabrication
- Use the simulation as a validation tool for experimental design and fabrication

---

## 🔩 PMUT Structure Overview

The device is a multilayer circular membrane modeled on a silicon substrate. Layers include:

| Material              | Thickness / Size             |
|-----------------------|------------------------------|
| Silicon               | 2 in diameter, 297 µm thick  |
| AlN Interlayer        | 0.17 µm                      |
| Mo (Bottom Electrode) | 0.25 µm                      |
| AlN Piezo Layer       | 1.1 µm                       |
| Mo (Top Electrode)    | 0.25 µm                      |

## ⚙️ FEM Model Setup

- Bottom walls of wafer: **Fixed**
- Top electrode: **2V electric potential**
- Bottom electrode: **Grounded**
- Remaining parts: **Free to vibrate**

**Material Properties (Si):**
- Young’s Modulus: `170 GPa`
- Density: `2329 kg/m³`
- Poisson’s Ratio: `0.28`

---

## 📐 3D Geometry & Mesh
![3D Model- 4 membranes](https://github.com/samueloladosu37/PMUT-FEM-Simulation-using-COMSOL/blob/main/3D%20Model%201.png)

![FEM Mesh Model](https://github.com/samueloladosu37/PMUT-FEM-Simulation-using-COMSOL/blob/main/3D%20Mesh%20Model.png)

![Close View of the back etching of a single membrane](https://github.com/samueloladosu37/PMUT-FEM-Simulation-using-COMSOL/blob/main/Back%20View.png)

![Top View of a single membrane](https://github.com/samueloladosu37/PMUT-FEM-Simulation-using-COMSOL/blob/main/Top%20View.png)
<sub>Fig. 2: COMSOL 3D model and FEM mesh </sub>

---

## 📐 Resonance Frequency Equation (Timoshenko Plate Theory)

The resonance frequency `fr` of a circular, clamped, homogeneous plate is given by:

```
fr = [(3.19)^2 / (2π * r²)] * sqrt(D / μ)
```
Where:

* `D = (E * t³) / [12 * (1 - ν²)]` → Flexural rigidity
* `μ = ρ * t` → Mass per unit area

Putting it together:
```
fr = [(3.19)^2 / (2π * r²)] * sqrt[(E * t²) / (12 * (1 - ν²) * ρ)]
```
### 📌 Proportional Relationship
```
fr ∝ t / r²
```
---
### 🧮 Variable Definitions:

| Symbol | Description                      |
| ------ | -------------------------------- |
| `fr`   | Resonance frequency              |
| `r`    | Radius of the membrane           |
| `t`    | Thickness of the membrane        |
| `E`    | Young’s modulus                  |
| `ν`    | Poisson’s ratio                  |
| `ρ`    | Density of the membrane material |
| `D`    | Flexural rigidity                |
| `μ`    | Mass per unit area               |
---

## 📈 Simulation Results

Resonance frequencies obtained from eigenfrequency studies:

| Radius (µm) | Resonance Frequency (MHz) |
|-------------|----------------------------|
| 75 µm       | ~9 MHz                     |
| 100 µm      | ~7.9 MHz                     |
| 125 µm      | ~6.3 MHz                     |

![Mode 75 µm](https://github.com/samueloladosu37/PMUT-FEM-Simulation-using-COMSOL/blob/main/PMUT%2075%20%C2%B5m.png)
![Modes 100 µm](https://github.com/samueloladosu37/PMUT-FEM-Simulation-using-COMSOL/blob/main/PMUT%20100%20%C2%B5m.png)
![Modes 125 µm](https://github.com/samueloladosu37/PMUT-FEM-Simulation-using-COMSOL/blob/main/PMUT%20125%20%C2%B5m.png)
![Graph](https://github.com/samueloladosu37/PMUT-FEM-Simulation-using-COMSOL/blob/main/Graph.png)
<sub>Fig. 3: Simulated vibration modes at different radii</sub>

---

## 📫 Contact

Feel free to reach out or collaborate:

- LinkedIn: [Samuel Oladosu](https://www.linkedin.com/in/samueloladosu/)
- Email: [samueloladosu37@gmail.com](mailto:samueloladosu37@gmail.com)

---
