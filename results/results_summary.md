# Results Summary

## YOLOv8n Object Detection

The YOLOv8n detector was trained to identify medication-related objects within RGB video frames. Evaluation on a held-out validation set demonstrated strong small-object detection performance while maintaining real-time inference speed.

Key metrics:

* Precision: 0.974
* Recall: 0.962
* mAP@0.5: 0.986
* mAP@0.5:0.95: 0.625
* Inference Speed: ~3.4 ms/image (NVIDIA T4)
* Model Size: ~6.2 MB

These results indicate that YOLOv8n provides reliable medication-object detection suitable for real-time medication monitoring applications.

---

## Pose and Hand Landmark Analysis

MediaPipe Pose and Hands were used to extract skeletal body and hand landmarks from video frames. The system analysed wrist–mouth proximity, drinking behaviour, and upper-body motion patterns while preserving privacy through skeleton-based processing.

The pose-estimation module successfully provided robust behavioural features required for medication-intake verification while avoiding the storage of identifiable facial information.

---

## Action Recognition

A ResNet-18 action-recognition model was trained to classify medication-related activities from video frames.

Recognised actions included:

* Opening medication container
* Picking up pill
* Drinking water
* Closing medication container

Validation results demonstrated strong classification performance across all medication-intake action categories, supporting reliable behavioural understanding within the complete monitoring pipeline.

---

## Multi-Modal Fusion and Intake Verification

The final system combined:

* YOLOv8n object detection
* MediaPipe pose and hand landmarks
* ResNet-18 action recognition

through a transparent Finite State Machine (FSM) controller.

The fusion architecture verified complete medication-intake episodes by enforcing clinically meaningful event sequences, including medication handling, hand-to-mouth interaction, and drinking behaviour.

Performance was evaluated using:

* Accuracy
* Precision
* Recall
* F1 Score
* Confusion Matrix Analysis
* ROC Analysis
* Ablation Studies

Results demonstrated that multi-modal fusion improved intake-verification reliability compared with individual sensing modalities operating independently.

---

## Key Findings

The proposed system successfully demonstrated that medication intake can be monitored using a single RGB camera through the integration of object detection, pose estimation, action recognition, and temporal decision fusion.

The combination of complementary computer-vision modalities produced a privacy-preserving, interpretable, and computationally efficient solution suitable for future deployment in home and clinical medication-adherence monitoring environments.
