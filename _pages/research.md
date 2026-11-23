---
layout: page
permalink: /research/
title: research
description: What I work on and what I have done.
nav: true
nav_order: 3
---

My research sits at the intersection of **state estimation, system identification, and robust control**, applied to safety-critical systems. The thread running through it is *guaranteed* behavior under uncertainty. Rather than assuming noise is random with a known distribution, I model uncertainty as **bounded** and use set-based methods to reason about everything the system could be doing. Most of my work is in the Jain Research Lab at Purdue, advised by Prof. Neera Jain.

## Human-aware automated vehicles

**The question.** In conditionally automated (SAE Level 3) driving, the vehicle drives but the human must be ready to take over. How the human behaves depends on internal states the car cannot measure, such as trust and stress. If a vehicle could estimate those states, it could adapt, for example by changing how much information it shows the driver, to improve safety. This is the focus of my dissertation.

**What I've done.**

- **Modeling.** I developed a low-order hybrid dynamic model that captures continuous-valued cognitive states and the discrete decision to rely on automation or not, within a single framework. See *A Hybrid Dynamic Model for Predicting Human Cognition and Reliance During Automated Driving* (ITSC 2025).
- **Estimation.** I designed a set-based estimator that characterizes uncertainty without probabilistic assumptions. On human-subject data it improved prediction accuracy by over 6% compared to a state-of-the-art particle filter. See *A Set-Based Framework for Estimating Human Cognitive States During Conditionally Automated Driving* (under review).
- **Sensor scheduling.** I designed a real-time algorithm that decides when to solicit a measurement from the human, based on current and predicted uncertainty. It polled only 2 of 16 participants while matching the prediction accuracy of the offline schedule. See *A Sensor-Scheduling Approach to Predict Human Reliance During Automated Driving* (IFAC World Congress 2026).
- **Experiments and data.** With collaborators I helped design the experiments behind this work and analyze the resulting cognitive, physiological and gaze data. See the HFES papers and the *Transportation Research Part F* article in my [publications]({{ '/publications/' | relative_url }}). The driving studies run on a medium-fidelity SAE Level 3 simulator built in Unreal Engine 5, which began as an undergraduate project I supervised.

## System identification under bounded noise

Identifying a model from data usually assumes a noise distribution. In many real settings the only thing you can credibly say is that noise stays within known bounds. I work on identification methods built on **reachability analysis**, which return the full set of models consistent with the data and the bounds. See *A Reachability-Oriented Approach to Linear System Identification Under Unknown Bounded Noise* (ACC 2026).

## Robust control co-design for thermal management

In co-design, the plant and the controller are designed together. I extended set-based robust control co-design to a **nonlinear thermal management system**, guaranteeing safe operation under bounded uncertainty in heat loads. Existing linear robust co-design approaches cannot ensure that guarantee for this class of system. The tools include zonoLAB for set-based computation and Gurobi for optimization. See *Set-based Robust Control Co-Design for Nonlinear Systems: A Case Study for a Thermal Management System* (under review).

## Earlier work

Before my PhD, I worked on nonlinear dynamics and computational modeling:

- **Compliant rolling-sliding contact (IIT Tirupati).** I built a kinematic and dynamic nonlinear model of a compliant rolling-sliding contact mechanism using analytical and finite-element formulations, and simplified it to cut computation time by 40%. See the *Nonlinear Dynamics* article.
- **Nonlinear vibration absorbers (The Ohio State University).** As a summer research scholar, I analyzed the nonlinear dynamics of a vibration absorber with the multi-term harmonic balance method, which cut solution time by two orders of magnitude relative to a Runge-Kutta benchmark.

## Course projects

- **Trajectory-tracking MPC for an autonomous race car.** I implemented a feedback-linearized model predictive controller in Python within a ROS2 framework to track a trajectory on the Monza F1 circuit. Adding an iterative learning control scheme reduced lateral tracking error by over 50% across laps.

## Methods and tools

Set-based (set-membership) state estimation, reachability analysis, system identification, model predictive control, hybrid systems, robust control co-design, and nonlinear dynamical modeling. I work mostly in MATLAB, Python and C++.

## Mentoring

I have mentored undergraduate researchers through Purdue's SURF program on projects including information-theoretic analysis of physiological signals, a real-time eye-gaze fixation classifier for automated driving, and the Unreal Engine driving simulator mentioned above.
