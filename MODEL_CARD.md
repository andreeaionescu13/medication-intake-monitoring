# Model Card

## Model Overview

This project presents a multi-modal computer vision system for medication intake monitoring using a single RGB camera.

The system integrates multiple components:

* **YOLOv8n** for pill detection
* **MediaPipe Pose** for body landmark extraction
* **MediaPipe Hands** for hand landmark tracking
* **ResNet-18** for medication-related action recognition
* **Finite State Machine (FSM)** for temporal event fusion and final intake verification

The objective is to determine whether a complete medication intake event has occurred by analysing object interactions, body movements, hand-to-mouth gestures, and drinking behaviour.

---

## Intended Use

This system is designed as a decision-support tool for:

* Medication adherence monitoring
* Elderly care support
* Home healthcare monitoring
* Clinical observation environments
* Research in healthcare computer vision

The system is intended to assist healthcare professionals, caregivers, and researchers by providing objective behavioural evidence of medication intake.

It is **not intended for medical diagnosis or autonomous clinical decision-making**.

---

## Training Data

The models were trained and evaluated using a custom medication-intake dataset collected specifically for this research.

The dataset contains:

* Medication handling activities
* Pill appearance and manipulation
* Hand-to-mouth gestures
* Drinking-water actions
* Medication container opening and closing events

Video recordings were converted into image frames and annotated for object detection and action recognition tasks.

The original dataset is not publicly distributed for privacy reasons.

---

## Model Inputs

### YOLOv8n

Input:

* RGB image frames

Output:

* Pill bounding boxes
* Detection confidence scores

### MediaPipe

Input:

* RGB image frames

Output:

* Body landmarks
* Hand landmarks
* Wrist-to-mouth proximity measurements

### ResNet-18

Input:

* Video frames

Output:

* Action class predictions:

  * Opening medication container
  * Picking up pill
  * Drinking water
  * Closing medication container

### Finite State Machine

Input:

* Detection events
* Pose events
* Action predictions

Output:

* Medication intake decision
* Confidence score
* Event timeline

---

## Evaluation Metrics

The system was evaluated using:

* Accuracy
* Precision
* Recall
* F1 Score
* Confusion Matrix
* ROC Curve
* AUC
* Ablation Analysis

Evaluation was performed at both module level and end-to-end system level.

---

## Strengths

* Real-time capable
* Privacy-preserving architecture
* Interpretable decision-making
* Single-camera deployment
* Non-invasive monitoring approach
* Modular design enabling future expansion

---

## Limitations

* Dataset collected under controlled conditions
* Limited participant diversity
* Single-camera viewpoint
* Potential sensitivity to lighting variations
* Occlusions may affect detection accuracy
* Additional clinical validation is required before deployment in healthcare settings

---

## Ethical Considerations

The system was designed with privacy preservation as a core requirement.

Where possible, behavioural analysis relies on skeletal landmarks and geometric relationships rather than storing identifiable visual information.

The system should be used only as a support tool and must not replace healthcare professionals, clinical judgement, or established medical procedures.

Human oversight is required for all healthcare-related decisions.

---

## Future Work

Future improvements may include:

* Multi-person monitoring
* Larger and more diverse datasets
* Edge-device deployment
* Transformer-based temporal modelling
* Explainable AI techniques
* Clinical validation studies
* Integration with healthcare information systems
