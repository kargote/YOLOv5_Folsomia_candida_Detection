# YOLO-Folsomia

Reproducible pipeline for training, evaluating, and applying YOLOv5 to detect and count *Folsomia candida* in lab microcosms. This repository includes code, model weights, data structure, and documentation related to:

Argote, K.; Santonja, M.; Geslin, B.; Miranda-Fuentes, J.; Albert C.H. (2025).
YOLO-Folsomia: A model to detect and count soil mesofauna in laboratory settings.
Ecological Informatics.

---

## Project Overview

- Trained YOLOv5 model on a dataset of 200 images containing 9,498 annotated individuals of *Folsomia candida*.
- Compared different YOLOv5 model variants and input resolutions.
- Selected the best-performing model: YOLOv5l with 1280 px input resolution (`best_1280px_v5l.pt`).
- Provided scripts for training, evaluation, inference, and result visualization.

---

## Repository Structure

/models
├── best_1280px_v5l.pt # Best model weights
├── dataset200img1280px_v100 # Training logs and outputs for 1280px dataset
├── dataset200img640px_v100 # Training logs and outputs for 640px dataset
└── results_csv # CSV summaries of model performance

/detection_results
├── run1_test-dataset_1280_v5l # YOLOv5 inference outputs for experiment 1
├── run2_exp-density_1280_v5l # YOLOv5 inference outputs for experiment 2
├── run3_exp-networks_1280_v5l # YOLOv5 inference outputs for experiment 3
└── run4_exp-biomass_1280_v5l # YOLOv5 inference outputs for experiment 4

/yolov5_forked
├── modified YOLOv5 codebase and utilities used in this project
├── training scripts
└── inference scripts

/data
├── annotations_json # Original annotation files in JSON format
├── input_dataset # Training images (original and augmented)
└── outputs # Training logs and validation results

---

## Installation

It is recommended to create a new Python virtual environment:

python -m venv yolov5-env
source yolov5-env/bin/activate  # macOS/Linux
.\yolov5-env\Scripts\activate   # Windows

Install the required packages with:
pip install -r requirements.txt
The requirements.txt includes all dependencies needed to run training, inference, and evaluation scripts.

##  Usage

Training: Modify and run the training scripts in /yolov5_forked to retrain or fine-tune models.
Inference: Use provided inference scripts with best_1280px_v5l.pt weights to detect and count Folsomia candida in new images.
Evaluation: Scripts generate detection statistics and bounding box visualizations.

## Citation

Please cite our paper if you use this code or dataset:
Argote, K.; Santonja, M.; Geslin, B.; Miranda-Fuentes, J.; Albert C.H. (2025).
YOLO-Folsomia: A model to detect and count soil mesofauna in laboratory settings.
Ecological Informatics.

## Contact
Karolina Argote
Email: karolina.ARGOTE-DELUQUE@univ-amu.fr
ORCID: 0000-0001-9922-3439
