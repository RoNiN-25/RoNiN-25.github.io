---
layout: page
title: Deep RL based Control of a Quadrotor
description: A deep respecting learning based position and attitude controller for a Quadrotor
img: assets/img/Deep_RL_based_control_for_quadrotor/deep_rl_drone_control.png
importance: 1
category: robotics
related_publications: false
---

This project investigates the use of **deep reinforcement learning (DRL)** for achieving **position** and **attitude control** of a quadrotor in a simulated 3D environment. Using a **Proximal Policy Optimization (PPO)**-based policy gradient approach, we designed controllers that learn end-to-end mappings from system states to motor commands, enabling autonomous flight without relying on explicit dynamic models.

The control problem involves stabilizing a quadrotor and navigating it to desired positions while handling its nonlinear dynamics. We explored **two different DRL-based control architectures**:

1. **Single-Policy Approach**

   * A single PPO policy was trained to take the **desired position, velocity, and acceleration** along with the **current state** (position, velocity, acceleration, and corresponding errors) as input.
   * The policy directly output the **motor velocities** for the four quadrotor motors.

2. **Hierarchical Two-Policy Approach** *(Cascaded Control)*

   * Inspired by the **cascaded PID controller** structure, two PPO policies were trained:

     * **Outer Loop Policy**: Processes the current state and outputs the **desired attitude**.
     * **Inner Loop Policy**: Receives the desired attitude and current orientation, generating the **motor velocities**.

In our experiments, the **hierarchical two-policy approach** outperformed the single-policy method, achieving better stability, smoother trajectories, and faster convergence. All training and simulations were conducted using the **PyBullet physics engine**.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/Deep_RL_based_control_for_quadrotor/deep_rl_drone_control.png" title="Architecture Diagram" class="img-fluid rounded z-depth-1" %}
    </div>

    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/Deep_RL_based_control_for_quadrotor/drone_flying.gif" title="Drone Flying" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

<div class="caption">
    Left: Architecture diagram for the Single-Policy and Two-Policy Approach for the controller. Right: A gif of the result obtained from the trained Two-policy network
</div>

### **Highlights**

* Implemented **PPO-based DRL controllers** for quadrotor position and attitude control.
* Designed and compared **single-policy** and **hierarchical two-policy** architectures.
* Demonstrated improved performance using the **cascaded control-inspired** hierarchical design.
* Trained and evaluated policies in a **realistic PyBullet simulation environment**.


