# Autonomous UAV Wind Vector Estimation & Track Compensation Engine

![Python 3](https://img.shields.io/badge/Language-Python%203.10-blue)
![Flight Dynamics](https://img.shields.io/badge/Domain-Aerodynamics%20%26%20Avionics-red)
![Developer](https://img.shields.io/badge/Developer-Ayoub%20Lahmar-brightgreen)

A spatial avionics estimator for UAV dead-reckoning navigation in GPS-degraded environments. Evaluates the aerodynamic **Wind Triangle** in the East-North-Up (\(ENU\)) reference frame to isolate crosswind velocity vectors and computes real-time **Crab Angle** heading compensations.

Developed by **Ayoub Lahmar** ([@Redayoub-lang](https://github.com/Redayoub-lang)).

## 📐 Mathematical Formulation

The vector addition connecting Ground Velocity \(\vec{V}_g\), True Airspeed \(\vec{V}_a\), and Ambient Wind \(\vec{W}\) is:
$$\vec{V}_g = \vec{V}_a + \vec{W} \implies \vec{W} = \vec{V}_g - \vec{V}_a$$To eliminate crosswind drift along target track $\theta_{track}$, the Crab Angle $\beta$ is computed via crosswind scalar projection $W_{cross} = \vec{W} \cdot \hat{u}_{cross}$:$$\beta = \arcsin\left( \frac{-W_{cross}}{\|\vec{V}_a\|} \right)$$$$\theta_{heading} = \theta_{track} + \beta$$
💻 Run Pipeline
python wind_estimator.py
