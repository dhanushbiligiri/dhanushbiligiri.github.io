---
layout: archive
title: "CV"
permalink: /cv/
author_profile: true
classes: cv-page
redirect_from:
  - /resume
---

{% include base_path %}

# Education

* **Ph.D. in Electrical and Computer Engineering**, Binghamton University (SUNY), Vestal, NY  
  Expected May 2028  
  Ph.D. studies transferred from Michigan Technological University, Computer Engineering (Aug. 2024 – Aug. 2026).

* **M.S. in Data Science**, Michigan Technological University, Houghton, MI  
  Aug. 2022 – Apr. 2024  
  GPA: 3.75

* **B.E. in Information Science and Engineering**, New Horizon College of Engineering, Bengaluru, India  
  Aug. 2018 – May 2022  
  GPA: 3.52


# Research Experience

## Robotics, Locomotion and Applied Control (RoLAC) Lab
**Graduate Research Assistant**  
Binghamton, NY / Houghton, MI  
May 2023 – Present

### Multi-Fault-Tolerant Humanoid Locomotion – Unitree G1
* Developed SAC-based reinforcement-learning controllers for goal-directed locomotion of a 23-DoF Unitree G1 using Python, MuJoCo, Gymnasium, and Stable-Baselines3.
* Increased simulated course completion under two joint-lock faults from 0% to 72%.
* Implemented damage-propagation reduction using per-joint torque limits, reducing representative compensatory knee peak torque from 70.9 to 52.6 N·m under a hip-joint lock.
* Trained fault-tolerant crawling policies, increasing survival with forward progress from 65% to 92.5% under three simultaneous knee/ankle joint locks with the hip joints available in simulation.

### Energy-Regularized Bipedal Locomotion under Varying Gravity – Bolt
* Funded by the National Science Foundation (NSF).
* Designed and trained PPO-based locomotion policies in MuJoCo across 26 energy-regularization settings under Earth and lunar gravity without prescribing target velocity, gait symmetry, or gait structure.
* Quantified emergent gait transitions using contact ratio, ground reaction forces, friction utilization, speed, and cost of transport.
* Identified gradual running-to-skipping transitions under Earth gravity and sharper hopping-to-loping transitions under lunar gravity.

### RL-Based Bipedal Locomotion – Cassie
* Designed and trained PPO-based locomotion policies in MuJoCo for dynamic bipedal locomotion.
* Reduced joint-tracking error by 16%.
* Developed neural predictors for joint-trajectory estimation and investigated learning-based optimization of locomotion performance.

### Reinforcement Learning for Humanoid Perception, Planning, and Control
* Led a systematic review of reinforcement learning for humanoid robots spanning 2000–2025.
* Organized methods across perception, planning, and control.
* Consolidated an 870-paper database from Scopus and IEEE Xplore, retaining 168 studies after systematic screening.
* Analyzed 45 representative works across algorithms, simulation environments, physical humanoid platforms, applications, and real-world deployment.

### Scientific Machine Learning – FractionalNet
* Partially funded by Oak Ridge Associated Universities (ORAU).
* Developed a symmetric neural-network architecture for approximating half-order fractional derivatives from integer-order data.
* Designed a two-stage genetic algorithm for network hyperparameter optimization.
* Evaluated seven weight-initialization strategies and identified He-Uniform as the strongest-performing initialization for the three-layer architecture.


# Industry Experience

## Aeronautical Development Establishment (ADE), DRDO
**Software Engineer Intern**  
Bengaluru, India  
Feb. 2021 – Apr. 2021

* Developed software for UAV control-data processing and automated reporting.
* Improved analysis efficiency by 40% and reporting speed by 30%.


# Teaching Experience


<ul>
{% for post in site.teaching reversed %}
  {% include archive-single-cv.html %}
{% endfor %}
</ul>


# Skills

* **Programming & Reinforcement Learning:** Python, PyTorch, Stable-Baselines3, Gymnasium, RLlib, Scikit-learn, MATLAB, C++
* **Robotics Simulation & Hardware Platforms:** MuJoCo, Isaac Lab, ROS, Unitree G1, Bolt
* **Embedded & Systems:** Linux, Git/GitHub, Verilog, ARM Microcontrollers, Intel RealSense, Jetson Nano


# Publications

<ul>
{% for post in site.publications reversed %}
  {% include archive-single-cv.html %}
{% endfor %}
</ul>


# Misc Projects

## Multi-Ingredient Food Image Classification & Recipe Recommendation
* Built an end-to-end computer vision and NLP pipeline using YOLOv8n for multi-ingredient detection.
* Achieved mAP@50 = 0.829.
* Used TF-IDF retrieval and T5-based recipe generation.
* Deployed an interactive Gradio interface for image-based recipe recommendation.
* **Technologies:** Python, YOLOv8, OpenCV, Optuna, TF-IDF, Hugging Face T5, Gradio

## Underwater Object Detection with Image Enhancement
* Evaluated YOLOv8 object detection on original and Semi-UiR-enhanced underwater imagery.
* Image enhancement improved visual clarity by 12%.
* Detection on original imagery achieved 30% higher accuracy than detection on enhanced images.
* **Technologies:** Python, OpenCV, YOLOv8, Ultralytics, Semi-UiR


# Honors & Awards

* **Jonathan Bara Outstanding Graduate Teaching Assistant Award**, Michigan Technological University, 2025
* **GSG Outstanding Graduate Teaching Assistant Award**, Michigan Technological University, 2026


# Service & Leadership

* **Vice President**, Graduate Student Government, Michigan Technological University  
  Apr. 2026 – Aug. 2026

* **Department Representative**, Graduate Student Government, Michigan Technological University  
  Aug. 2023 – Apr. 2026

* **Student Member**, IEEE

* **Tutor**, McNair Scholars Program, Michigan Technological University  
  Aug. 2023 – Apr. 2024