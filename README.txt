# Scrap Material Classification Internship Project

## Overview
This project demonstrates an end-to-end machine learning pipeline for classifying scrap materials using images. The pipeline trains a YOLOv8 image classification model and simulates automated sorting via a dummy conveyor loop.

## Dataset
- **Name:** TrashNet (Stanford)
- **Classes:** Metal, Plastic, Glass, Paper, Cardboard, Trash
- **Download:** [TrashNet Kaggle Link](https://www.kaggle.com/datasets/feyzazkefe/trashnet)
- **Structure:** `dataset-resized/train/[class]/`, `dataset-resized/val/[class]/`

## Model
- **Architecture:** YOLOv8 (Ultralytics)
- **Transfer Learning:** Started from `yolov8n-cls.pt`
- **Training:** 10 epochs, batch size 32, image size 128x128
- **Final Accuracy:** ~90% (Top-1), ~99% (Top-5)
- **Exported formats:** TorchScript and ONNX (`model.torchscript`, `model.onnx`)

## ML Pipeline Steps
1. Dataset downloaded, organized, split into train/val.
2. YOLOv8 model trained, metrics logged.
3. Accuracy/loss curves plotted.
4. Exported trained model.
5. Dummy conveyor loop simulates real-time classification; predictions and confidence logged in `conveyor_results.csv`.

## Dummy Conveyor Loop Simulation
- Takes image files one by one.
- Runs model prediction, outputs class label and probability.
- Logs result in CSV and prints to console.

## Results
- **Accuracy Curve:** ![accuracy_curve.png](attach if image available)
- **Loss Curve:** ![loss_curve.png](attach if image available)
- **Sample Predictions:** See `conveyor_results.csv`
- **Confusion Matrix:** ![confusion_matrix.png](attach if image available)

## How to Run
1. Clone/download this repo or notebook.
2. Download dataset as per above, organize into YOLO format.
3. Install dependencies:

