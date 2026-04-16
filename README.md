# HyPhi-Dance: Multimodal Brain-Body Synchrony Pipeline 🧠💃

![Python](https://img.shields.io/badge/Python-3.10-blue)
![MNE](https://img.shields.io/badge/MNE-EEG_Processing-orange)
![YOLO](https://img.shields.io/badge/YOLO-Pose_Estimation-yellow)
![TDA](https://img.shields.io/badge/Giotto--TDA-Topology-pink)

## 📌 Project Overview
**HyPhi-Dance** is a highly scalable, headless Proof of Concept (PoC) pipeline engineered for **Mobile Brain/Body Imaging (MoBI)** and **Community Neuroscience** research. It addresses the critical computational bottlenecks in real-world hyperscanning by seamlessly synchronizing and analyzing physical movement (Kinematics) and neural connectivity (EEG).

This pipeline was designed to facilitate ecological research into intergenerational communication, somatic therapies (Dance Movement Therapy), and affective computing.

---

## 🏗️ The Architecture
The pipeline is divided into three distinct, headless modules designed for cloud execution (e.g., Google Colab):

1. **Kinematic Synchrony Extraction (Computer Vision):** 
   Utilizes `YOLO-Pose` (headless OpenCV distribution) to extract 17-point skeletal multi-person kinematics from video data. It calculates a geometric **Kinematic Synchrony Index (KSI)** to quantify the physical mimicry and coordination between dyads (e.g., child and grandparent).
   
2. **EEG Artifact Ablation (Signal Processing):** 
   Utilizes `MNE-Python` to automatically apply bandpass filtering and **Independent Component Analysis (ICA)**. This mimics the automated rejection of severe electromyogenic (EMG) artifacts generated during unconstrained physical movement.

3. **Information-Geometric Hyperscanning (Topology):** 
   Instead of traditional linear correlation (PLV), this pipeline utilizes `Ripser` to model the dual-brain functional connectivity as a high-dimensional simplicial complex. By computing **Persistent Homology**, it extracts the *Topological Entropy* of the network, capturing non-linear phase transitions during social bonding.

---

## 📊 Visual Proof & Output

Below is a generated plot demonstrating the temporal alignment between the physical movement of the dyad (Kinematic Synchrony) and their collective neural topology (Topological Entropy).

*(Upload your `synchrony_plot.png` to your repo and link it here like this:)*
![Synchrony Output Plot](synchrony_plot.png)

---

## ❓ Frequently Asked Questions (FAQ)

### Why does this PoC use simulated (random) EEG data?
Open-source, highly synchronized multimodal datasets containing both raw multi-channel EEG and corresponding video of unconstrained dyadic dance are virtually non-existent in the public domain due to extreme privacy protocols and the novelty of the field. 
To demonstrate the *computational architecture*, this pipeline mathematically generates synthetic EEG data containing noise, effectively proving that the **MNE/ICA cleaning** and **Topological Data Analysis** pipelines function perfectly within a cloud environment. 

### How will this work in a Real-World scenario?
In a real-world clinical or museum setting (e.g., using wireless EEG headsets like Smarting MoBI), the data streams (EEG and Video/Motion Capture) are multiplexed and timestamped using the **Lab Streaming Layer (LSL)** framework. The `mne-lsl` Python library would simply replace the `simulate_and_clean_eeg` function in this code, ingesting the timestamped `.xdf` files directly into this exact same pipeline.

### Can this pipeline handle 1-person vs. 2-person scenarios?
Yes. The architecture is dynamically adaptive:
* **For a Dyad (2-people):** The YOLO model calculates the Euclidean distance between the two skeletons (Inter-personal Kinematic Synchrony), and the TDA module evaluates the *Inter-Brain* functional connectivity matrix.
* **For an Individual (1-person):** The pipeline automatically detects a single bounding box. It shifts to measuring *Intra-personal* kinematic complexity (e.g., movement entropy) and runs the TDA exclusively on the individual's *Intra-Brain* connectivity, making it perfect for studying individual neuroaesthetics or motor control.

---
**Author:** Saleh Estaki Organi  
**Focus:** Computational Social Science | Health Psychology | Applied AI
