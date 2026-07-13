---
title: "Trajectory Planner for Autonomous Ground Vehicles in Unknown Environments"
summary: "Master's thesis: a Hybrid A*/JPS trajectory planner with a novel free-space-estimation recovery behavior and MPC feedback control, extending the FASTER planning framework for ground robots"
date: 2024-07-13
tags:
  - Robotics
---

Developed a comprehensive autonomous navigation stack for ground vehicles as part of my Master's thesis, extending [FASTER](https://github.com/mit-acl/faster) with a new trajectory planner, a novel recovery behavior, and MPC-based feedback control.

**Key Contributions:**
* **Trajectory Planning**: Replaced FASTER's JPS-only planning approach with Hybrid A* as the primary trajectory planner, supplemented by JPS to improve planning efficiency, reducing optimization failures and total simulation time.
* **Free Space Estimation Recovery Behavior**: Designed and implemented a novel free-space estimation approach that acts as a recovery behavior in critical situations, particularly narrow paths and corridors where nominal free-space estimation tends to fail.
* **Feedback Control**: Integrated Model Predictive Control (MPC) as the vehicle's feedback control mechanism, enabling precise real-time trajectory tracking toward the optimal path.

**Methods Used:**
* Hybrid A* trajectory planning, supplemented by Jump Point Search (JPS)
* Novel free-space estimation recovery behavior for narrow-space navigation
* Model Predictive Control (MPC) for feedback control
* Simulation-based validation against baseline planners (FASTER/JPS-only, Hybrid A*-only)

**Software Used:**
ROS, C++, Gurobi Optimizer, Gazebo, Rviz, JPS3D

**Results (validated in simulation):**
* 23% reduction in optimization failures compared to the original FASTER approach (JPS-only planning)
* 3% reduction in total simulation time compared to using Hybrid A* alone
* 5x improvement in recovery success rate over nominal free-space estimation in obstacle-dense, narrow-corridor environments

This video shows the mobile robot navigating to a random target point (green sphere) while avoiding new obstacles in the unknown environment.
<div style="display: flex; justify-content: flex-end; margin-top: 2rem;">
  <iframe src="https://drive.google.com/file/d/1QqfabunIrlzDQM1eV_LZS0Yo78BxrjXR/preview" width="640" height="480" style="max-width: 100%; border: none; border-radius: 8px;"></iframe>
</div>
