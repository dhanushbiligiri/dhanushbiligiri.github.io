---
title: "Reinforcement Learning: Teaching Machines Through Interaction"
date: 2026-10-01
permalink: /blogs/reinforcement-learning/
tags:
  - reinforcement learning
  - robotics
  - machine learning
  - control
---

Reinforcement learning (RL) is one of the areas of machine learning that I find particularly interesting because it changes the way we think about programming intelligent systems.

Instead of explicitly telling a system exactly what action to take in every possible situation, reinforcement learning allows an **agent to learn behavior through interaction with an environment**. The agent observes what is happening, takes an action, receives feedback in the form of a reward, and gradually learns a policy that produces useful behavior.

This idea sounds simple, but it becomes especially interesting when the "agent" is a physical system such as a robot.

## The Basic Idea

A reinforcement-learning problem is commonly described using a **Markov Decision Process (MDP)** consisting of:

- **State** — what situation the agent is currently in
- **Action** — what the agent can do
- **Transition** — how the environment changes after an action
- **Reward** — feedback indicating whether an action was useful
- **Policy** — the strategy used by the agent to select actions

The goal is not necessarily to maximize the immediate reward. Instead, the agent tries to maximize the **cumulative reward over time**.

For robotics, the situation is usually even more complicated because the robot cannot perfectly observe its complete physical state. Sensors provide measurements rather than perfect knowledge, making many real robotic problems closer to **partially observable decision processes**.

For example, a humanoid robot may observe joint positions, joint velocities, body orientation, previous actions, and a commanded walking velocity. A reinforcement-learning policy can then use those observations to determine its next action.

---

## What Does an RL Agent Actually Learn?

At the center of reinforcement learning is the policy:

\[
a_t \sim \pi_\theta(a_t \mid s_t)
\]

or, when working with observations rather than complete states,

\[
a_t \sim \pi_\theta(a_t \mid o_t)
\]

where:

- \(o_t\) is the observation at time \(t\),
- \(a_t\) is the action,
- \(\pi_\theta\) is the learned policy parameterized by \(\theta\).

In robotics, the action could represent many different things.

A policy might output:

- desired joint positions,
- joint-position offsets,
- actuator torques,
- footstep locations,
- velocity commands,
- motion references,
- or even high-level skills.

This is one reason reinforcement learning is such a broad area. Two systems may both use RL while learning completely different parts of the overall control pipeline.

---

## Major Types of Reinforcement Learning

There are many RL algorithms, but one useful way to organize them is according to how they use knowledge of the environment dynamics.

### Model-Free Reinforcement Learning

In **model-free RL**, the agent learns directly from experience without explicitly learning a model that predicts how the environment evolves.

The agent essentially learns:

> "Given what I observe now, what action should I take?"

Popular model-free algorithms include:

- **Q-Learning**
- **Deep Q-Networks (DQN)**
- **Proximal Policy Optimization (PPO)**
- **Soft Actor-Critic (SAC)**
- **Deep Deterministic Policy Gradient (DDPG)**
- **Twin Delayed DDPG (TD3)**

For high-dimensional continuous-control problems such as robotic locomotion, algorithms such as **PPO and SAC** are particularly common.

I use both of these families in my own robotics research.

PPO is an **on-policy** algorithm. It improves the policy using data collected from the current policy while constraining how aggressively the policy is updated.

SAC is an **off-policy actor-critic** algorithm. It can reuse previously collected experience and includes an entropy objective that encourages exploration.

Both approaches can learn complex behaviors, but their training characteristics and data requirements are different.

---

## Model-Based Reinforcement Learning

In **model-based RL**, the system either knows or learns a model of the environment dynamics.

Conceptually, the system learns something like

\[
\hat{s}_{t+1} = f_\phi(s_t,a_t),
\]

where the model predicts what will happen after taking an action.

The agent can then use this model to reason about future outcomes before acting.

This can potentially make learning more **sample efficient**, which is particularly important when interaction with the real system is expensive.

For robotics, however, accurately modeling phenomena such as:

- contact,
- friction,
- impacts,
- actuator dynamics,
- deformable surfaces,

can become difficult.

This is one reason model-free reinforcement learning combined with physics simulation has become so common in modern legged robotics.

---

## Hybrid Reinforcement Learning

There is also an important middle ground: **hybrid approaches**.

Instead of asking reinforcement learning to control everything, a system can preserve reliable classical robotics components and use learning only where adaptation is needed.

For example,

\[
u_t = u_t^0 + \Delta u_t
\]

can be used, where:

- \(u_t^0\) is the command produced by a conventional controller,
- \(\Delta u_t\) is a correction learned using reinforcement learning.

This is often called **residual reinforcement learning**.

Similar architectures can combine RL with:

- PD controllers,
- model predictive control,
- whole-body control,
- trajectory optimization,
- inverse kinematics.

I find this direction particularly interesting because it does not require choosing between "classical control" and "machine learning." The two can complement each other.

---

## Other Ways RL Systems Are Structured

The distinction between model-free and model-based RL describes how dynamics are handled, but RL systems can also be organized according to their architecture.

### Imitation + Reinforcement Learning

Sometimes it is inefficient to ask a robot to discover a complicated behavior entirely through random exploration.

Instead, demonstrations can provide examples of useful behavior.

The robot may first imitate human motion or reference trajectories and then use reinforcement learning to improve robustness and adapt the behavior.

This approach is widely used for humanoid locomotion and whole-body motion.

---

### Hierarchical Reinforcement Learning

A complicated task can also be split into multiple levels.

For example:

```text
High-level policy
        ↓
"Walk to the table"
        ↓
Locomotion policy
        ↓
Joint targets
        ↓
Robot