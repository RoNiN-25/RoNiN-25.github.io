---
layout: page
title: Robust Drone Control using Uncertainty and Disturbance Estimation (UDE)
description: Implementation of a UDE based robust control on a quadrotor
img: assets/img/Robust_UDE_drone_control/plutox_img.png
importance: 1
category: thesis
related_publications: false
---

This project investigates the design and implementation of a **robust control architecture** for a quadrotor drone using the **Uncertainty and Disturbance Estimator (UDE)** approach. The goal was to achieve stable flight and accurate trajectory tracking in the presence of **model uncertainties** and **external disturbances**.

We used a **PlutoX quadrotor** equipped with an **ESP32** controller and integrated it with a **WhyCon marker-based localization system** for indoor tracking. The control framework was implemented using **MATLAB/Simulink** for simulation and **ROS**/**C++** for real-world deployment.


Traditional **PID-based controllers** often fail to deliver reliable performance when the drone dynamics are uncertain or when disturbances affect the system. To address this, we implemented a **UDE-based control strategy** that dynamically estimates the effects of disturbances and model inaccuracies and compensates for them in real-time.

Key features of the implementation:

* **Virtual force-based position control**: Computes a desired virtual force vector from the drone’s current state to the goal point, enabling intuitive 3D navigation.
* **UDE-based torque control**: Achieves robust control of the drone’s roll, pitch, and yaw angles even under model inaccuracies.
* **ROS-based integration**: Used **WhyCon markers** for precise position feedback and implemented real-time communication between the controller and drone.
* **Onboard implementation**: Developed a **C++-based UDE controller** using the **Cygnus IDE** and flashed it onto the STM32 microcontroller for faster attitude control.

Simulations were carried out in **MATLAB/Simulink** to validate the performance, followed by real-world testing. Results demonstrated that the **UDE controller significantly outperformed PID control**, achieving lower overshoot and better stability while successfully compensating for external disturbances.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/Robust_UDE_drone_control/cascaded_controller.png" title="Cascaded Controller" class="img-fluid rounded z-depth-1" %}
    </div>

    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/Robust_UDE_drone_control/plutox_img.png" title="PlutoX" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

<div class="caption">
    Left: The cascaded controller used for position and attitude control. Right: An image of the PlutoX quadrotor used for hardware verification
</div>
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/Robust_UDE_drone_control/step_response.png" title="UDE step response" class="img-fluid rounded z-depth-1" %}
    </div>

    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/Robust_UDE_drone_control/hw_resp.png" title="Hardware response" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

<div class="caption">
    Left: Step response of the designed UDE controller showing position and attitude control. Right: Results from the attitude controller deployed on the hardware
</div>


### **Highlights**

* Designed and implemented a **UDE-based robust controller** for a quadrotor drone.
* Achieved **precise position and attitude control** using virtual forces and torque-based UDE control.
* Demonstrated significant improvement over traditional PID controllers in simulation and real-world tests.
* Integrated **WhyCon localization**, **ROS-based control**, and **onboard C++ implementation** for faster computation and real-time performance.
* Validated results through **MATLAB/Simulink simulations** and hardware experiments.


### Resources
- 📄 [Thesis Report (PDF)](https://ronin-25.github.io/assets/pdf/Robust_UDE_drone_control/Final_report.pdf)
- 🖼️ [Poster Presentation (PDF)](https://ronin-25.github.io/assets/pdf/Robust_UDE_drone_control/Poster.pdf)
- 💻 [Implementation code (github)](https://github.com/RoNiN-25/UDE_Robust_drone_control/tree/main)



