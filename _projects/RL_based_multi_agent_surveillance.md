---
layout: page
title: Reinforcement Learning based Persistent Surveillance by Robots
description: A rolling-horizon RL-based solution to multi-agent persistent surveillance with battery and communication constraints.
img: assets/img/25N-3A.gif
importance: 1
category: thesis
related_publications: true
---

This project proposes a **reinforcement learning-based framework** for optimal routing in persistent surveillance using energy-constrained single and multi-agent systems.

We model the environment as a **strongly connected weighted graph**, with agents tasked to visit surveillance nodes and occasionally return to base nodes to upload data, all while respecting energy constraints. A **rolling-horizon optimization** strategy is used with **D3QN and PPO** algorithms for learning. 

The agents are trained to **minimize node idleness** and **maximize coverage efficiency**. We handle hard energy constraints using **action-space projection to safe sets** and develop **scalable, near-optimal policies** using attention-based deep neural networks and **bidirectional GRUs**.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/RL_based_ma_surv/graph_topology.png" title="Example Graph topology used in simulations" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/RL_based_ma_surv/ma_q_network.png" title="Multi agent Q-Network Architecture" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/RL_based_ma_surv/comp_time.png" title="RL vs. IP Computation Time" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

<div class="caption">
    Left: A sample graph with base/survey nodes. Center: Multi agent Q-network with BRNN + attention. Right: RL policy achieves significant speedup over exact solvers.
</div>

### Highlights
- Developed a **deep Q-network** with **Bahdanau attention** for learning node visit policies.
- Guaranteed energy constraint satisfaction via **safe set projection**.
- Achieved **orders of magnitude speedup** compared to SCIP-based IP solvers.
- Demonstrated robust policies over graphs with up to **100 nodes** and **multi-agent setups**.

### Resources
- 📄 [Thesis Report (PDF)](https://ronin-25.github.io/assets/pdf/RL_based_ma_surv/MTech_Project_Final_Report.pdf)
- 🖼️ [Poster Presentation (PDF)](https://ronin-25.github.io/assets/pdf/RL_based_ma_surv/poster_final.pdf)

### Supervisor
Dr. Pavankumar Tallapragada, Indian Institute of Science

---

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/RL_based_ma_surv/10N-2A.gif" title="Simulation result with 10 nodes and 2 agents" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/RL_based_ma_surv/20N-3A.gif" title="Simulation result with 20 nodes and 3 agents" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/RL_based_ma_surv/25N-1A.gif" title="Simulation results with 25 nodes and 1 agent" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

<div class="caption">
    Simulation results with different number of nodes and agents configurations. Left: 10 nodes with 2 agents. Center: 20 nodes with 3 agents. Right: 25 nodes with 1 agent.
</div>
