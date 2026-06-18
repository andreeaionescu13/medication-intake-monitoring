# Project Report

## Abstract

Medication non-adherence remains a significant challenge in healthcare, contributing to preventable hospital admissions, disease progression, and increased healthcare costs. This project presents a multi-modal computer vision framework for medication intake monitoring using a single RGB camera. The proposed system combines YOLOv8 object detection, MediaPipe pose estimation, ResNet-18 action recognition, and a finite-state machine fusion controller to verify medication intake behaviour. The framework provides a privacy-preserving, non-invasive alternative to traditional adherence monitoring technologies while maintaining real-time performance and interpretability.

---

# 1. Introduction

Medication adherence is a critical factor influencing patient outcomes and healthcare efficiency. Traditional monitoring approaches such as self-reporting, pill counting, and electronic monitoring systems often suffer from measurement limitations and behavioural biases.

This project investigates whether computer vision can provide an objective method for verifying medication intake without requiring specialised hardware or modifications to existing medication routines.

---

# 2. Research Questions

This dissertation addresses the following questions:

1. Can a monocular RGB camera reliably detect medication intake events?
2. Can the system verify the correct sequence of medication administration?
3. Which modelling choices improve robustness across subjects and environments?
4. Is the proposed system suitable for future real-world deployment?

---

# 3. Methodology

The proposed system consists of four major components.

## 3.1 Video Preprocessing

Video recordings are converted into standardised image frames through temporal normalisation and resizing procedures.

## 3.2 Pill Detection

YOLOv8n is used to detect pharmaceutical objects within medication intake scenes.

## 3.3 Pose and Gesture Detection

MediaPipe Pose and MediaPipe Hands are used to extract body and hand landmarks, enabling hand-to-mouth gesture analysis while preserving privacy.

## 3.4 Action Recognition

A ResNet-18 model classifies medication-related actions including:

* Opening medication container
* Picking up pill
* Drinking water
* Closing medication container

## 3.5 Multi-Modal Fusion

A finite-state machine integrates information from all modules to determine whether a complete medication intake event has occurred.

---

# 4. Dataset

A custom medication-intake dataset was created specifically for this research.

The dataset includes:

* Medication container manipulation
* Pill handling
* Hand-to-mouth gestures
* Drinking actions

Videos were processed into image frames and annotated for object detection and action recognition tasks.

---

# 5. Results

The system was evaluated using:

* Precision
* Recall
* F1 Score
* Accuracy
* ROC-AUC
* Confusion Matrix Analysis

Results demonstrate that combining object detection, pose estimation, and action recognition provides more robust medication-intake verification than any individual module operating independently.

---

# 6. Key Contributions

The project contributes:

* A custom medication-intake dataset
* A YOLOv8-based pill detection framework
* A privacy-preserving pose-analysis pipeline
* A ResNet-18 action-recognition module
* A finite-state machine fusion architecture
* A complete end-to-end medication monitoring framework

---

# 7. Limitations

Several limitations should be acknowledged:

* Controlled data collection environment
* Limited participant diversity
* Single-camera viewpoint
* Sensitivity to severe occlusions
* Need for larger-scale clinical validation

---

# 8. Future Work

Future improvements include:

* Larger datasets
* Multi-person monitoring
* Transformer-based temporal modelling
* Explainable AI integration
* Edge-device deployment
* Clinical validation studies

---

# 9. Conclusion

This research demonstrates the feasibility of monitoring medication intake using computer vision and multi-modal fusion techniques. The proposed framework provides an interpretable, privacy-preserving, and scalable approach to medication adherence monitoring that could support future healthcare applications in both home and clinical environments.
