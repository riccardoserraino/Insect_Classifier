# Agro Insect Detection — Master Repo
**Authors:** Riccardo Serraino, Giuliano Livi

This repository links the two implementations developed to detect agricultural insects — **bee**, **butterfly**, and **ladybug** — in the context of a field robotics competition held in Germany in 2026 - [FRE2026](https://www.fieldrobotevent.eu/).

We participated in the competition representing [Politecnico di Milano](https://www.polimi.it/) as part of the [AIRLab team](https://airlab.deib.polimi.it/).

Insects appear in the competition field as **puppets**, **printed images**, or **text**, and must be detected in real time from a robot camera.

---

## Repositories

### 🔗 [YOLOv11 Detection](https://github.com/riccardoserraino/Insect_Detection_YOLO.git)
**YOLOv11** model detecting 4 classes: bee, butterfly, ladybug, and text.  
When a text label is detected, **EasyOCR** is triggered to read and classify the insect described. Full workflow testing available at this repo. 

### 🔗 [YOLOv6 Detection](https://github.com/riccardoserraino/Insect_Detection_YOLO6.git)
**YOLOv6** (stable) model fine-tuning and training pipeline for Luxonics OAK-D Pro camera model development. Also this model will employ **EasyOCR** for text reading. Note that this workspace has some bugs and not fully working, but YOLOv11 turned out to work on OAK D Pro cameras. 

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
| Prototyping | YOLOv6 | Not fully working workspace|
| Final | YOLOv11 + EasyOCR | Real-time detection locally, 4 classes + text reading classification|



For more info about each project step consider opening the link of a specific repo.
