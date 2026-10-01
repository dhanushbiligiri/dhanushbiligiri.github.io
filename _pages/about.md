---
permalink: /
title: "Dhanush Biligiri's Portfolio"
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---

<!-- Hi! I’m a Ph.D. student in Electrical and Computer Engineering at Binghamton University, working at the intersection of robotics, machine learning, and control.

My research focuses on reinforcement learning for legged and humanoid locomotion, with particular interest in fault-tolerant control, adaptive locomotion, and learning-based robotic systems. I work extensively with physics-based simulation environments such as MuJoCo and Isaac Lab to study how robots can learn robust locomotion behaviors under changing dynamics, actuator faults, and environmental conditions.

Before my current work in robotics, I worked on problems spanning machine learning, computer vision, scientific computing, and neural networks. I enjoy research problems where learning and physical systems meet—especially when the result is a robot learning how to move in ways that were not explicitly programmed.

Outside research, I’m usually playing basketball, running, golfing, following Formula 1, or watching the Golden State Warriors and Indian cricket. Coffee also plays a statistically significant role in most of these activities. -->

Hi! I’m a Ph.D. student in Electrical and Computer Engineering at [Binghamton University](https://www.binghamton.edu/), specializing in reinforcement learning, robotics, and control for legged and humanoid systems.

My work focuses on developing learning-based locomotion controllers that remain robust when robot dynamics, actuator capabilities, or operating conditions change. I am particularly interested in fault-tolerant locomotion, adaptive control, and reinforcement learning for bipedal and humanoid robots. My current research includes multi-fault-tolerant control for the Unitree G1 humanoid, energy-aware locomotion for bipedal robots, and studying how locomotion strategies emerge under different physical and environmental constraints.

I build and evaluate these systems primarily in [MuJoCo](https://mujoco.org/) and [Isaac Lab](https://isaac-sim.github.io/IsaacLab/), working across reinforcement learning, simulation, robot dynamics, control, and experimental analysis. My experience also includes machine learning, computer vision, scientific computing, and neural-network-based modeling.

I enjoy problems where algorithms have to interact with real physical constraints rather than only optimize a benchmark. I am especially interested in building robotic systems that can adapt, recover from failures, and continue performing useful tasks in uncertain environments.

Outside research, I enjoy basketball, running, golf, Formula 1, the Golden State Warriors, and Indian cricket.

## News

{% assign sorted_news = site.news | sort: "date" | reverse %}

{% for item in sorted_news limit:5 %}
**{{ item.date | date: "%b %d, %Y" }}** — [{{ item.title }}]({{ item.url | relative_url }})  
{% endfor %}

[View all news →](/news/)

## Recent Reads

{% assign sorted_reads = site.reads | sort: "date" | reverse %}

{% for item in sorted_reads limit:5 %}
**{{ item.date | date: "%b %d, %Y" }}** — [{{ item.title }}]({{ item.url | relative_url }}){% if item.author %}, {{ item.author }}{% endif %}  
{% endfor %}

[View all reads →](/reads/)