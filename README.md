# Agro Insect Detection — Master Repo

## Authors

- Riccardo Serraino — [GitHub](https://github.com/riccardoserraino) | [LinkedIn](https://www.linkedin.com/in/riccardoserraino/)
- Giuliano Livi — [GitHub](https://github.com/Giuliano-Livi) | [LinkedIn](https://www.linkedin.com/in/giuliano-livi-524a81335/)

---

This repository links the two implementations developed to detect agricultural insects — **bee**, **butterfly**, and **ladybug** — in the context of a field robotics competition held in Germany in 2026 - [FRE2026](https://www.fieldrobotevent.eu/).

We participated in the competition representing [Politecnico di Milano](https://www.polimi.it/) as part of the [AIRLab team](https://airlab.deib.polimi.it/).

Insects appear in the competition field as **puppets**, **printed images**, or **text labels**, and must be detected in real time from a robot-mounted camera.

---

## Repositories

### 🔗 [YOLOv11 Detection](https://github.com/riccardoserraino/Insect_Detection_YOLO.git)

YOLOv11-based pipeline for real-time insect detection.  
Detects **bee, butterfly, ladybug, and text regions**.  
When text is detected, an OCR module (EasyOCR) is triggered to extract and classify the insect name.

---

### 🔗 [OAK-D ROS2 Integration](https://github.com/riccardoserraino/OAK_Detection.git)

This repository contains the real-time deployment pipeline on the Luxonis OAK-D Pro camera.

It integrates:
- DepthAI pipeline (RGB + NN inference + Stereo/Depth)
- YOLOv11 inference on-device
- ROS2 bridge for image and detection streaming
- OCR service communication (C++ -> Python)
- Real-time crop extraction and classification feedback loop

It is the robot-side execution layer responsible for running the full perception system directly on embedded vision hardware.

---

## Approach Evolution

Early experiments explored multiple architectures for classification and detection. These were progressively replaced due to limitations in real-time performance, deployment complexity, and robustness in field conditions.

| Stage | Model | Reason for Change |
|------|------|------------------|
| Baseline | Simple CNN | Limited generalization on real field data |
| Transfer Learning | MobileNet | Improved accuracy but unstable under occlusions or multiple objects |
| Detection (prototype) | YOLOv6 | Integration issues in ROS2 + embedded pipeline |
| Final System | YOLOv11 + EasyOCR | Best balance of accuracy, speed, and deployability on OAK-D |

YOLOv11 was selected as the final model due to:
- strong real-time performance on edge devices
- better robustness in cluttered environments
- simpler ROS2 + DepthAI integration
- improved stability for mixed inputs (images, puppets, text)

---

## Summary

The final system combines:
- YOLOv11 for real-time detection
- EasyOCR for text-based insect classification
- OAK-D edge pipeline for onboard inference
- ROS2 architecture for modular communication between components
