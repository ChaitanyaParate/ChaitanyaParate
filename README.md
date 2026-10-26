# Chaitanya Parate

**Robotics · Reinforcement Learning · Graph Neural Networks · Sim-to-Real Control**

B.Tech Computer Science and Engineering (AI & Data Science) · MIT-WPU, Pune · Expected 2027

Research Intern, CAIR, IIT Mandi · RL-based quadruped locomotion.

Building across AI/ML, robotics, deep learning, software systems, and embedded engineering. Open to AI/ML, robotics, software, and embedded systems internships from January 2027.

[LinkedIn](https://www.linkedin.com/in/chaitanyaparate) · [Email](mailto:paratechaitanya5@gmail.com) · [GitHub Repositories](https://github.com/ChaitanyaParate?tab=repositories)

---

## Current Research: RL Quadruped Locomotion

**Centre for Artificial Intelligence and Robotics (CAIR), IIT Mandi** · Research internship, July-December 2026

Developing a reinforcement-learning locomotion pipeline for the Hiwonder ROSpug quadruped, with a focus on actuator-aware simulation and sim-to-real transfer.

- Structured PPO policy using a Hopf Central Pattern Generator (CPG), initially trained in MuJoCo and now running in NVIDIA Isaac Lab (Isaac Sim 6.0.1).
- Trained a data-driven Actuator-Net on measured servo-characterization data to model non-ideal actuator dynamics.
- Calibrated domain-randomization stages using measured servo characteristics to better represent the physical system.
- Exported the latest policy checkpoint to ONNX. Jetson Nano deployment and hardware validation are in progress.

Research paper in progress.

---

## Featured Project

### [Heterogeneous GNN Morphology Transfer](https://github.com/ChaitanyaParate/hetero-gnn-morphology-transfer)

[![DOI](https://img.shields.io/badge/DOI-10.5281%2Fzenodo.20187567-blue.svg)](https://doi.org/10.5281/zenodo.20187567)

Investigating zero-shot locomotion policy transfer across robot morphologies using a 31,582-parameter heterogeneous Graph Neural Network (GATv2Conv) trained with Proximal Policy Optimization (PPO). The system combines graph-based control with YOLOv8 perception and an on-device LLM planning layer, with ROS 2 Jazzy and Gazebo integration.

- **Zero-shot quadruped-to-hexapod transfer:** Transferred a policy from a 12-DOF quadruped to an 18-DOF hexapod without retraining, obtaining a reward of 106 ± 25 and approximately 47 survival steps. The fixed-input-dimension MLP baseline could not run on the unseen morphology.
- **Fine-tuning:** 500K additional steps increased reward from approximately 110 to 416 ± 114 and survival from 47 to 193 steps.
- **Model size:** 31,582 parameters, approximately 85% fewer than the 210,457-parameter MLP baseline. The MLP achieves higher in-distribution reward, while the GNN supports variable graph structures.
- **Terrain evaluation:** 95% success at a 5° slope and 0% at a 10° slope in the reported zero-shot terrain tests.
- **Control and deployment:** Reported 200 Hz GNN inference with yaw-rate PI correction to address circular drift associated with HAA joint offsets.
- **LLM planning:** Qwen 2.5 7B through Ollama maps natural-language instructions to skills and GNN-generated joint commands, running locally without cloud inference.

**Limitation:** Zero-shot transfer is not yet robust across all conditions. The hexapod's initial survival is substantially below the in-distribution result, and the 10° terrain result shows that the current policy has clear limits.

[Repository, implementation details, results, and reproduction instructions](https://github.com/ChaitanyaParate/hetero-gnn-morphology-transfer) · [Zenodo record](https://doi.org/10.5281/zenodo.20187567)

---

## Selected Projects

### [DeskAI: Local Desktop AI Daemon](https://github.com/ChaitanyaParate/Deskai)

A local-first Linux desktop AI daemon built around persistent services, UNIX domain socket IPC, X11/OCR context tracking, and streaming LLM inference through Ollama, with optional online fallback.

- Implemented an intent router that dispatches requests to typed executors, including summarization and error explanation.
- Built a fault-tolerant streaming pipeline that separates the CLI client lifecycle from the persistent daemon.
- Added internet-aware backend switching without requiring a daemon restart.

### [SE-Attention Half-UNet](https://github.com/ChaitanyaParate/SE-Attention-Half-UNet)

Medical-image polyp segmentation model combining attention gates, squeeze-and-excitation (SE) blocks, and BCE-Dice loss. Evaluated on Kvasir-SEG, with a reported Dice score of **0.9436**.

### [LEAP Hand Dexterous Grasping](https://github.com/ChaitanyaParate/leap-dexterous-grasping)

PPO-based reinforcement-learning pipeline in MuJoCo for grasping and lifting a cube with the LEAP Hand. The repository reports an **85% success rate across 100 randomized deterministic evaluation episodes**. The policy meets the defined binary success criterion, but sustained grasp quality remains a limitation documented in the repository.

### [STM32 Hyperloop Embedded Firmware](https://github.com/ChaitanyaParate/stm32-hyperloop-embedded)

Embedded C firmware for Team Vegapod, including a custom Bluetooth bootloader, FreeRTOS-based BMS/VCU braking, three-phase inverter PWM, and CAN communication. Represented MIT-WPU at European Hyperloop Week 2025 in the Netherlands.

### Additional Deep Learning Projects

- **[ResNet-50 from Scratch](https://github.com/ChaitanyaParate/ResNet50-From-Scratch-Pytorch-Imagenette):** Implemented ResNet-50 in PyTorch and reported 86.63% top-1 accuracy on Imagenette, with live ESP32-CAM inference.
- **[Brain Tumor MRI Classification](https://github.com/ChaitanyaParate/Modified-Half-UNet-for-Medical-Image-Classification):** Adapted a U-Net encoder for binary MRI classification, reporting 98% accuracy on a dataset of 3,000+ images.

---

## Open-Source Contributions

### [isaac-sim/IsaacLab](https://github.com/isaac-sim/IsaacLab) · [PR #7533](https://github.com/isaac-sim/IsaacLab/pull/7533)

Investigated a reported visualizer-configuration crash and traced it to a broken workspace installation rather than an underlying logic bug. The investigation surfaced stale visualizer-alias assertions and a test for a CLI flag removed in version 3.0. The resulting test fixes were merged in September 2026 and backported to `release/3.0.0`.

### [metatensor/metatrain](https://github.com/metatensor/metatrain) · [PR #1003](https://github.com/metatensor/metatrain/pull/1003)

Fixed a schema-validation edge case involving zero-sized validation splits in ML training pipelines. The pull request passed 17 CI checks and was merged in January 2026.

---

## Technical Stack

**Robotics and RL**  
![ROS 2](https://img.shields.io/badge/ROS_2-22314E?style=flat&logo=ros&logoColor=white)
![NVIDIA Isaac Sim](https://img.shields.io/badge/NVIDIA_Isaac_Sim-76B900?style=flat&logo=nvidia&logoColor=white)
![MuJoCo](https://img.shields.io/badge/MuJoCo-000000?style=flat&logo=mujoco&logoColor=white)
![Gazebo](https://img.shields.io/badge/Gazebo-F58113?style=flat&logo=gazebo&logoColor=white)
![PyBullet](https://img.shields.io/badge/PyBullet-346F9F?style=flat&logo=python&logoColor=white)

**Machine Learning and Deployment**  
![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=flat&logo=pytorch&logoColor=white)
![PyTorch Geometric](https://img.shields.io/badge/PyTorch_Geometric-3C2179?style=flat&logo=pytorch&logoColor=white)
![ONNX](https://img.shields.io/badge/ONNX-005CED?style=flat&logo=onnx&logoColor=white)
![YOLOv8](https://img.shields.io/badge/YOLOv8-111F68?style=flat&logo=yolo&logoColor=white)
![Ollama](https://img.shields.io/badge/Ollama-000000?style=flat&logo=ollama&logoColor=white)

**Systems and Embedded**  
![C](https://img.shields.io/badge/C-00599C?style=flat&logo=c&logoColor=white)
![C++](https://img.shields.io/badge/C%2B%2B-00599C?style=flat&logo=cplusplus&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=flat&logo=linux&logoColor=black)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat&logo=docker&logoColor=white)
![FreeRTOS](https://img.shields.io/badge/FreeRTOS-8CC84B?style=flat&logo=freertos&logoColor=white)
![STM32](https://img.shields.io/badge/STM32-03234B?style=flat&logo=stmicroelectronics&logoColor=white)

---

## Contact

- **LinkedIn:** [linkedin.com/in/chaitanyaparate](https://www.linkedin.com/in/chaitanyaparate)
- **Email:** [paratechaitanya5@gmail.com](mailto:paratechaitanya5@gmail.com)
- **GitHub:** [github.com/ChaitanyaParate](https://github.com/ChaitanyaParate)
