# Agro Insect Detection — Master Repo
**Authors:** Riccardo Serraino, Giuliano Livi

This repository links the two implementations developed to detect agricultural insects — **bee**, **butterfly**, and **ladybug** — in the context of a real field robotics competition held in **Germany, 2026**.

Insects appear in the competition field as **real animals**, **printed images**, or **puppets**, and must be detected in real time from a robot camera.

---

## Repositories

### 🔗 [YOLO Detection](https://github.com/riccardoserraino/Insect_Detection_YOLO.git)
Fine-tuned **YOLOv11** model detecting 4 classes: bee, butterfly, ladybug, and text.  
When a text label is detected, **EasyOCR** is triggered to read and classify the insect described.

### 🔗 [CNN & MobileNet Detection](https://github.com/riccardoserraino/Insect_Detection_CNN_MobileNet.git)
Earlier classification models used during prototyping:
- **Custom CNN** — built from scratch, used as baseline
- **MobileNet** — pretrained backbone, ready for fine-tuning

---

## Approach

| Stage | Model | Notes |
|---|---|---|
| Prototyping | Custom CNN | Baseline classifier |
| Prototyping | MobileNet | Transfer learning |
| Final | YOLOv11 + EasyOCR | Real-time detection, 4 classes |

For more info about the project consider opening the link of a specific repo.
