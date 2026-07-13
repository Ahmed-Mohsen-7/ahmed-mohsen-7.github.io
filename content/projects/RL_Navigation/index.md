---
title: "Robot Navigation using Reinforcement Learning"
summary: "Deep reinforcement learning for robot goal-navigation in a custom Turtlebot3-inspired environment, comparing DQN, DDPG, and TD3 in discrete and continuous action spaces"
date: 2022-12-01
tags:
  - CV
  - Robotics
---

Built a custom OpenAI Gym environment inspired by Turtlebot3 to train robot navigation policies from scratch, and implemented and compared three reinforcement learning algorithms (DQN, DDPG, and TD3) across both discrete and continuous action spaces.

**Key Contributions:**
* **Custom Environment Design**: Built a Gym-compatible navigation environment (`world.py`) from scratch, including a map-to-grayscale conversion pipeline (via OpenCV) to distinguish navigable space from walls and obstacles, and registered it as a proper Gym environment (`World-v1` with obstacles, `World-v2` without).
* **Reward Shaping**: Designed a two-component reward function combining a distance reward (inverse of Euclidean distance to target) and a bearing reward (alignment between robot heading and target direction), balancing goal-seeking behavior with orientation control.
* **Algorithm Implementation & Comparison**: Implemented and trained three RL algorithms, DQN (discrete action space) and DDPG/TD3 (continuous action space, controlling linear and angular velocity), to solve the navigation task under identical environment conditions.

**Environment Details:**
* Observation space: robot pose (x, y, θ) and target position (x, y)
* Action space: linear velocity (v) and angular velocity (w), continuous for DDPG/TD3
* Randomized start/target poses per episode, constrained to avoid walls, obstacles, and overlapping start/goal positions
* Motion modeled via an integration approximation for pose updates given (v, w)

**Methods Used:**
* Deep Q-Network (DQN) for discrete action-space navigation
* Deep Deterministic Policy Gradient (DDPG) and Twin Delayed DDPG (TD3) for continuous action-space navigation
* Custom Gym environment with distance + bearing reward shaping
* Computer vision-based map preprocessing (grayscale conversion for navigable-space detection)

**Software Used:**
Python, OpenAI Gym, Stable-Baselines3, OpenCV, Pillow

**Results (validated in simulation):**

This video shows the robot navigatin to a random target location, trained using RL policy.
<div style="display: flex; justify-content: flex-end; margin-top: 2rem;">
  <iframe src="https://drive.google.com/file/d/1jKqXJ_4NQIm32j_P0myAXHUWCRvsIBO9/preview" width="640" height="480" style="max-width: 100%; border: none; border-radius: 8px;"></iframe>
</div>
