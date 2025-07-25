Automated Road Damage Detection Using UAV Images

This project focuses on detecting and classifying road surface damage from UAV (Unmanned Aerial Vehicle) imagery using deep learning techniques. The goal is to support automated infrastructure maintenance by identifying cracks, potholes, and other types of road deterioration efficiently.

## 🛰️ Project Overview

- **Domain**: Computer Vision / Deep Learning
- **Objective**: Detect and classify road damage from aerial images.
- **Input**: UAV-captured road images.
- **Output**: Annotated images with bounding boxes and damage class labels.

## 📂 Dataset

We used the [Road Damage Detection Dataset](https://github.com/sekilab/RoadDamageDetector/) captured by UAVs. The dataset contains:
- Annotated images in `.jpg` format
- Corresponding `.xml` files in Pascal VOC format
- 4 main damage categories:
  - D00: Longitudinal Cracks
  - D10: Lateral Cracks
  - D20: Alligator Cracks
  - D40: Potholes

## 🧠 Model Architecture

We use a pretrained deep learning object detection model fine-tuned on the road damage dataset:
- **Model**: YOLOv5 / Faster R-CNN (specify the one used)
- **Framework**: PyTorch
- **Pretrained Weights**: COCO

## 🛠️ Installation

Clone the repository:
```bash
git clone https://github.com/your-username/road-damage-detection.git
cd road-damage-detection

Install dependencies:

pip install -r requirements.txt

Download the dataset and place it in the data/ directory as follows:

road-damage-detection/
├── data/
│   ├── images/
│   └── annotations/

🚀 Training

To train the model on the dataset:

python train.py --data data.yaml --epochs 50 --weights yolov5s.pt

Replace yolov5s.pt with your choice of model weights.
📈 Evaluation

Evaluate the model performance using:

python val.py --data data.yaml --weights runs/train/exp/weights/best.pt

Metrics: mAP@0.5, Precision, Recall
🖼️ Inference

To run inference on UAV images:

python detect.py --weights runs/train/exp/weights/best.pt --source data/images/

Results will be saved to runs/detect/exp/.
📊 Results
Class	Precision	Recall	mAP@0.5
D00 (Long.)	0.87	0.81	0.84
D10 (Lat.)	0.90	0.86	0.88
D20 (Allig.)	0.78	0.74	0.76
D40 (Pothole)	0.91	0.89	0.90

(Replace with your actual metrics)
📌 Features

    Automatic bounding box detection for multiple damage types

    Real-time UAV image processing pipeline

    Easy to extend and retrain with new datasets

📚 References

    YOLOv5 GitHub

    Road Damage Dataset

    Pascal VOC Format# Automated-road-damage-detection-using-uav-iamges
