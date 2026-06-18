# Computer Vision System for Medication Intake Monitoring Through Multi-Modal Fusion

## MSc Artificial Intelligence and Machine Learning Dissertation

**Author:** Andreea Ionescu
**University:** University of Portsmouth
**Supervisor:** Rinat Khusainov
**Year:** 2025


## Project Overview

Medication non-adherence remains one of the most significant challenges in modern healthcare, contributing to preventable hospital admissions, disease progression, and increased healthcare costs.

This project presents an end-to-end computer vision system capable of automatically monitoring medication intake using a single RGB camera. The proposed solution combines object detection, human pose estimation, action recognition, and multi-modal decision fusion to verify whether medication has been taken correctly.

Unlike traditional adherence monitoring methods such as self-reporting, pill counting, electronic pill caps, or ingestible sensors, this system provides an objective, non-invasive, and privacy-preserving approach that does not require modifications to existing medication routines.

---

## Research Objectives

The primary objective of this dissertation is to develop and evaluate a real-time medication intake monitoring system capable of:

* Detecting medication-related objects using computer vision.
* Tracking human body and hand movements during medication intake.
* Recognising medication-related actions.
* Verifying the correct sequence of medication administration.
* Producing transparent and interpretable adherence decisions.
* Supporting future deployment in home and clinical environments.

---

## System Architecture

The proposed system consists of four main components:

### 1. Video Preprocessing

* Video frame extraction
* Temporal normalisation
* Frame resizing and normalisation
* Dataset preparation

### 2. Pill Detection (YOLOv8)

* Fine-tuned YOLOv8n model
* Detection of pills within medication intake scenes
* Real-time inference capability
* Small-object detection optimisation

### 3. Pose and Gesture Analysis (MediaPipe)

* Human pose estimation
* Hand landmark detection
* Wrist-to-mouth proximity calculation
* Hand-to-mouth gesture recognition
* Privacy-preserving skeletal representation

### 4. Action Recognition (ResNet-18)

Recognition of medication-related actions:

* Opening medication container
* Picking up pill
* Drinking water
* Closing medication container

### 5. Multi-Modal Fusion

A finite-state machine (FSM) combines outputs from all modules to determine whether a complete medication intake event has occurred.

---

## Technologies Used

### Programming Language

* Python

### Computer Vision

* OpenCV
* MediaPipe

### Deep Learning

* PyTorch
* YOLOv8 (Ultralytics)
* ResNet-18

### Data Analysis

* NumPy
* Pandas
* Matplotlib
* Scikit-learn

### Development Environment

* Google Colab
* Jupyter Notebook

---

## Dataset

A custom medication intake dataset was created for this research.

The dataset contains videos of medication administration activities recorded under controlled conditions, including:

* Pill handling
* Container manipulation
* Hand-to-mouth gestures
* Drinking behaviour

Video data was processed into image frames and annotated for object detection and action recognition tasks.

For privacy reasons, the original dataset is not included in this repository.

---

## Methodology

The proposed pipeline follows the sequence below:

1. Video acquisition
2. Frame extraction and preprocessing
3. Pill detection using YOLOv8
4. Pose and hand landmark extraction using MediaPipe
5. Action classification using ResNet-18
6. Temporal event modelling
7. Multi-modal fusion using a finite-state machine
8. Final medication intake prediction

---

## Results

The system demonstrates the feasibility of real-time medication intake monitoring through computer vision.

Evaluation includes:

* Object detection performance
* Pose and gesture recognition performance
* Action recognition accuracy
* Intake decision accuracy
* Confusion matrix analysis
* ROC analysis
* Ablation studies

The results indicate that combining object detection, pose estimation, and action recognition improves robustness compared with individual modules operating independently.

---

## Repository Structure

```text
medication-intake-monitoring/
├── README.md
├── MODEL_CARD.md
├── report.md
├── requirements.txt
├── .gitignore
├── LICENSE
│
├── notebooks/
│   └── Dissertation_Andreea_Ionescu.ipynb
│
├── src/
│
├── data/
│   └── dataset_description.md
│
├── images/
│
└── results/
```

## Installation

Clone the repository:

```bash
git clone https://github.com/andreeaionescu13/medication-intake-monitoring.git
cd medication-intake-monitoring
```

Install dependencies:

```bash
pip install -r requirements.txt
```

---

## Future Work

Future development may include:

* Multi-person monitoring
* Mobile and edge-device deployment
* Larger and more diverse datasets
* Clinical validation studies
* Transformer-based temporal modelling
* Explainable AI integration
* Healthcare platform integration

---

## Ethical Considerations

This research was conducted with attention to privacy-preserving design principles.

The system relies primarily on skeletal keypoints and behavioural representations rather than storing identifiable patient imagery. The proposed framework is intended to support healthcare professionals and caregivers rather than replace clinical judgement.

---

## Citation

If you use or reference this work, please cite:

**Ionescu, A. (2025). Computer Vision System for Medication Intake Monitoring Through Multi-Modal Fusion. MSc Dissertation, University of Portsmouth.**

---

## License

This project is released under the MIT License.
