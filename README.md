# 🏗️ Buckling Analysis — Aluminum Rectangular Beam (ANSYS Static Structural)

Analytical and numerical study of the critical buckling load of an
aluminum beam with rectangular cross-section, comparing Euler's
formula with FEA simulation results.

> 📚 Aerospace Structural Mechanics — University of Brasília (UnB), 2022

---

## 📌 Overview

This project calculates the critical buckling load of a simply
supported (pinned-pinned) aluminum beam using two approaches:
- **Analytical** — Euler's critical load formula
- **Numerical** — Finite Element Analysis via ANSYS 2021 R2

Results are compared to validate the numerical model.

---

## 📐 Geometry & Parameters

Cross-section type: **Solid Rectangle**

| Parameter        | Value          |
|------------------|----------------|
| Length (L)       | 400 mm         |
| Width (b)        | 10 mm          |
| Height (h)       | 18 mm          |
| Material         | Aluminum Alloy 3 |
| Elastic Modulus  | 70 GPa         |

---

## 🧮 Analytical Solution

Euler's critical load formula for a pinned-pinned beam:

$$P_{cr} = \frac{\pi^2 E I}{L^2}$$

**Moment of inertia of the rectangular section:**

$$I = \frac{b \cdot h^3}{12} = \frac{10 \times 18^3}{12} = 4860 \text{ mm}^4$$

**Critical load:**

$$P_{cr} = \frac{\pi^2 \times 70000 \times 4860}{400^2} = 20985.25 \text{ N}$$

**Buckling direction:** **+y**

Boundary conditions (pinned-pinned):

$$v = B\sin(\mu z), \quad \mu = \frac{\pi}{L}$$

Since $z$ varies between $0$ and $L$, the sine function is always
positive, confirming buckling in the **+y** direction.

---

## 💻 Numerical Simulation (ANSYS 2021 R2)

**Module:** Static Structural + Eigenvalue Buckling

**Workflow:**
1. 2D rectangular cross-section sketch (b=10mm, h=18mm)
2. Extrusion to 400 mm length (both directions — symmetric)
3. Material assigned: Aluminum Alloy 3
4. Boundary conditions: Cylindrical supports at both ends (pinned-pinned)
5. Eigenvalue Buckling solver

**Result:**

| Mode | Load Multiplier |
|------|----------------|
| 1    | 21777 N        |
| 2    | 26400 N        |

Buckling direction: **+y** ✅

---

## 📊 Comparison & Validation

| Method               | Critical Load  |
|----------------------|---------------|
| Analytical (Euler)   | 20985.25 N    |
| Numerical (ANSYS)    | 21777 N       |
| **Percentage Error** | **3.77%**     |

✅ Results are in good agreement, confirming the validity of both
approaches. The small discrepancy is within acceptable engineering
tolerance and is attributed to mesh discretization effects.

---

## 🔁 Comparison with Previous Study

| Property         | Exercise 1 (Steel / C-section) | Exercise 2 (Aluminum / Rectangle) |
|------------------|-------------------------------|-----------------------------------|
| Material         | Steel (E = 200 GPa)           | Aluminum (E = 70 GPa)             |
| Boundary Cond.   | Fixed-Free (cantilever)       | Pinned-Pinned                     |
| Pcr Analytical   | 1359.3 N                      | 20985.25 N                        |
| Pcr Numerical    | 1331.8 N                      | 21777 N                           |
| Error            | 2.06%                         | 3.77%                             |

---

## 🛠️ Tools Used

![ANSYS](https://img.shields.io/badge/ANSYS-2021_R2-yellow?style=flat)
![FEA](https://img.shields.io/badge/FEA-Static_Structural-blue?style=flat)
![Analytical](https://img.shields.io/badge/Method-Euler's_Formula-green?style=flat)
![Material](https://img.shields.io/badge/Material-Aluminum_Alloy-silver?style=flat)

---

## 👨‍💻 Author

**Guilherme Garcia Guedes**
Aerospace Engineer — UnB
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Guilherme_Garcia-blue?style=flat&logo=linkedin)](https://www.linkedin.com/in/guilherme-garcia-guedes-aeroespacial/)
