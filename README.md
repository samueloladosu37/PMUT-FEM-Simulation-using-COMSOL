# 📡 PMUT FEM Simulation using COMSOL

This repository contains a finite element simulation of a Piezoelectric Micromachined Ultrasonic Transducer (PMUT), carried out using COMSOL Multiphysics. The goal is to analyze the static and dynamic mechanical behavior of the device, estimate resonance frequencies, and validate design parameters for a target working frequency of **6 MHz**.

---

## 📘 About the Simulation

> _"This software analyzes physics-based numerical problems by dividing the geometric domain into finite elements (meshing) and solving the associated partial differential equations."_

The project includes Multiple Physics: Solid Mechanics, Electrostatic and Piezoelectric effect
- ✅ **Stationary simulations**: for static deformation and stress
- ✅ **Eigenfrequency studies**: to calculate natural oscillating frequencies
- ✅ **Parametric sweeps**: to evaluate how the PMUT membrane radius affects resonance frequency 

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

### Cross-Sectional View

![Cross Section](./path_to_image/cross_section.png)
<sub>Fig. 1: Cross-section of Mo/AlN/Mo multilayers on Si wafer</sub>

---

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

![3D Model](./path_to_image/3d_model.png)
<sub>Fig. 2: COMSOL 3D model (left) and FEM mesh (right)</sub>

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
| 100 µm      | ~7 MHz                     |
| 125 µm      | ~6 MHz                     |

![Modes](./path_to_image/mode_shapes.png)
<sub>Fig. 3: Simulated vibration modes at different radii</sub>

---

## 🎯 Objective

- Characterize PMUT behavior under excitation
- Achieve a working frequency near **6 MHz**
- Optimize geometry for fabrication
- Use the simulation as a validation tool for experimental design

---

