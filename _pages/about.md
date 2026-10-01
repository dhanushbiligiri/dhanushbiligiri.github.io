---
permalink: /
title: "Dhanush Biligiri's Portfolio"
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---

Hi! I’m a Ph.D. student in Electrical and Computer Engineering at Binghamton University, working at the intersection of robotics, machine learning, and control.

My research focuses on reinforcement learning for legged and humanoid locomotion, with particular interest in fault-tolerant control, adaptive locomotion, and learning-based robotic systems. I work extensively with physics-based simulation environments such as MuJoCo and Isaac Lab to study how robots can learn robust locomotion behaviors under changing dynamics, actuator faults, and environmental conditions.

Before my current work in robotics, I worked on problems spanning machine learning, computer vision, scientific computing, and neural networks. I enjoy research problems where learning and physical systems meet—especially when the result is a robot learning how to move in ways that were not explicitly programmed.

Outside research, I’m usually playing basketball, running, golfing, following Formula 1, or watching the Golden State Warriors and Indian cricket. Coffee also plays a statistically significant role in most of these activities.

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