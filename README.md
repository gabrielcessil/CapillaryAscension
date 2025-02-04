# Capillary Ascension in Porous Media

## Overview
This project explores **capillary ascension** in porous media, which describes how liquid moves through small interconnected pores due to **surface tension** and **adhesive forces**. This phenomenon is essential in various natural and industrial applications, including **soil moisture retention, oil recovery, and ink absorption**.

We compare different mathematical models to describe capillary dynamics, focusing on the **Lucas-Washburn equation** and two alternative methods that aim to capture both the **dynamic rise and steady-state height** of the liquid column.

---

## **Mathematical Model**
### **General Capillary Rise Dynamics**
The fundamental governing equation for capillary ascent is:

$$
h\frac{d^{2}h}{dt^{2}} + \left(\frac{dh}{dt}\right)^{2} + \frac{8\mu h}{\rho R^2} \frac{dh}{dt} = \frac{2\sigma\cos\theta}{\rho R} - gh
$$

where:
- \( h \) = liquid height
- \( \mu \) = dynamic viscosity
- \( \sigma \) = surface tension
- \( \theta \) = contact angle
- \( \rho \) = density of the liquid
- \( R \) = capillary radius
- \( g \) = gravitational acceleration

### **Equilibrium Condition**
At steady state, the liquid reaches its maximum height \( h_{eq} \), where capillary forces balance gravity:

$$
h_{eq} = \frac{2\sigma \cos\theta}{\rho g R}
$$

---

## **Numerical Methods Implemented**
The following methods are used to analyze capillary ascent:

### **1. Method 1 (Additive Approximation)**
This method replaces the term \( \frac{dh}{dt} \) with an **average velocity** approximation:

$$
\frac{dh}{dt} = \frac{\frac{2\sigma\cos\theta - g\rho R}{\rho R}}{\frac{h'}{t}+\frac{8\mu h}{\rho R^2}}
$$

which simplifies to:

$$
\frac{dh}{dt} = \frac{(2\sigma\cos\theta - g\rho R)Rt}{h' \rho R^{2} + 8 \mu h t}
$$

---

### **2. Method 2 (Multiplicative Approximation)**
Here, \( \frac{dh}{dt} \) is replaced with an **alternative mean velocity** approach:

$$
\frac{dh}{dt} = \frac{ \frac{2\sigma\cos\theta}{\rho R} -gh}{\frac{h'}{t}}-\frac{8\mu h}{\rho R^2}
$$

which simplifies to:

$$
\frac{dh}{dt} = \frac{(2\sigma\cos\theta-gh \rho R) R t - 8 \mu h h'}{p R^{2} h'}
$$

---

### **3. Lucas-Washburn Equation**
The classical **Lucas-Washburn** model assumes the capillary rise is controlled by the **balance between capillary pressure and viscous resistance**:

$$
\frac{dh}{dt} = \frac{\sigma R \cos\theta}{4 \mu h}
$$

with the **integrated form**:

$$
h^2 = \frac{\sigma R \cos\theta}{2 \mu} t
$$

This model predicts that **height increases proportionally to the square root of time** but does not capture the equilibrium height accurately.

---

## **Python Implementation**
The simulation is implemented in **Python** using `NumPy` and `Matplotlib`. The main function `run()` integrates the equations numerically.

### **Code Structure**
- `heq()` → Calculates the analytical equilibrium height.
- `h1()` → Computes height evolution using **Method 1**.
- `h2()` → Computes height evolution using **Method 2**.
- `hLW()` → Computes height using the **Lucas-Washburn** method.
- `run()` → Simulates capillary rise over time.

### **Usage**
Clone the repository and run the script:

```bash
git clone https://github.com/YOUR_USERNAME/CapillaryAscension.git
cd CapillaryAscension
python ascencaocapilar.py
