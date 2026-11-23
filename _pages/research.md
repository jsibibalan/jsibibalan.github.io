---
layout: page
permalink: /research/
title: Research
description: What I have worked on.
nav: true
nav_order: 3
---

My research sits at the intersection of **state estimation, system identification, and robust control**, applied to safety-critical systems. Rather than assuming noise is random with a known distribution, I treat uncertainty as **bounded** and use set-based methods to describe everything the system could be doing. 

## Human-aware automated vehicles

**The question.** In conditionally automated (SAE Level 3) driving, the vehicle drives but the human must be ready to take over. How the human behaves depends on internal states the car cannot measure, such as trust and mental workload. If a vehicle could estimate those states, it could adapt, for example by changing how much information it shows the driver, to improve safety. This is the focus of my dissertation.

**What I've done.**

- **Experiment Design.** I co-designed a <a href="https://www.sciencedirect.com/science/article/pii/S1369847825004243">novel experiment</a> to understand what factors affect human behavior during automated driving. The experiment was deployed on a medium-fidelity driving simulator built using Unreal Engine 5.
- **Modeling.** I developed a low-order <a href="https://ieeexplore.ieee.org/document/11423829">hybrid dynamic model</a> that captures continuous-valued cognitive states and the discrete decision to rely on automation or not, within a single framework. Unlike the majority of prior modeling efforts, I identify user-specific model parameters, meaning the model is personalized to the user. I also found that a decision-tree is a good choice for mapping the cognitive states to the user's reliance behavior.
- **Estimation.** I designed a <a href="https://arxiv.org/abs/2608.02308">set-based estimator</a> that characterizes uncertainty without probabilistic assumptions, unlike prior work that treats uncertainty as independent and identically distributed (IID). I hypothesized that the factors that affect human behavior and their responses to prompts aren't well represented by IID probabilistic distributions. The state estimator uses the hybrid model and fuses intermittent human self-reports and binary reliance observations to produce state estimates. I showed on human-subject data that a bounded characterization improved prediction accuracy by over 6% compared to a probabilistic particle filter.
- **Sensor scheduling.** I designed a real-time algorithm that decides *when to prompt the human to report their cognitive states*, based on current and predicted uncertainty. It polled only 2 of 16 participants while matching the prediction accuracy of the offline schedule.
- **Multi-Modal Sensing.** I helped conduct an <a href="https://journals.sagepub.com/doi/10.1177/10711813261484476">information-theoretic analysis</a> to identify physiological indicators (heart rate, skin conductance) and eye-gaze-based indicators that can be used to infer changes in human behavior. We found that informative features and their time-scales vary substantially across individuals; nevertheless, these indicators hold promise to reduce uncertainty or the querying frequency during state estimation.

<!-- ## System identification under bounded noise

Identifying a model from data usually assumes a noise distribution. In many real settings the only thing you can credibly say is that noise stays within known bounds. I work on identification methods built on **reachability analysis**, which return the full set of models consistent with the data and the bounds. See *A Reachability-Oriented Approach to Linear System Identification Under Unknown Bounded Noise* (ACC 2026). -->

## Robust control co-design for thermal management

I was fortunate to collaborate with my lab mate and apply set-based methods in a different application context.
In co-design, the system and the controller are designed together. An example of this would be simultaneous design of the dimensions of aircraft components and its autopilot software. I worked on applying set-based robust control co-design to a *nonlinear thermal management system*, guaranteeing safe operation (satisfying maximum temperature constraints) under unknown but bounded heat loads. Existing linear robust co-design approaches cannot ensure that guarantee for this class of system. 

## Earlier work

Before my PhD, I worked on creating mathematical models for nonlinear mechanical systems.


- **Compliant rolling-sliding contact (Indian Institute of Technology Tirupati).** I modeled a cam-follower mechanism with a flexible follower, building both a detailed nonlinear model and simpler, faster versions, one of which closely matches the detailed model. I used a combination of analytical and finite-element formulations. The analysis showed that compliance produces higher-period and chaotic behavior, and I studied how load and damping affect it. The approach could support faster digital twins of compliant mechanisms.
- **Nonlinear vibration absorbers (The Ohio State University).** As a summer research scholar, I analyzed the nonlinear dynamics of a vibration absorber using the multi-term harmonic balance method (MHBM). Unlike Runge-Kutta time integration, which steps the equations forward in time, MHBM turns the problem into a set of algebraic equations. 

<!-- ## Course projects

- **Trajectory-tracking MPC for an autonomous race car.** I implemented a feedback-linearized model predictive controller in Python within a ROS2 framework to track a trajectory on the Monza F1 circuit. Adding an iterative learning control scheme reduced lateral tracking error by over 50% across laps. -->

## Methods and tools

For my research and course projects, I've learned and applied state estimation (Kalman filtering, set-membership), reachability analysis, system identification, model predictive control (MPC), hybrid systems, robust control co-design, adaptive control, and nonlinear dynamical modeling. I work mostly in MATLAB, but I have also worked in Python and C++.

## Mentoring

I have mentored undergraduate researchers through Purdue's SURF program on projects including information-theoretic analysis of physiological signals, a real-time eye-gaze fixation classifier for automated driving, and the Unreal Engine driving simulator mentioned above.
