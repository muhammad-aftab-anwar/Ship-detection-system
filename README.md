# 🚢 Ship Detection Using YOLO

An object detection project that detects ships in aerial images using the YOLO (You Only Look Once) object detection framework. This project demonstrates dataset preparation, model training, evaluation, and inference using the Ultralytics YOLO implementation.

---

## 📌 Project Overview

This project uses a custom aerial image dataset to train a YOLO model for detecting ships. The model is trained on labeled images and evaluated using standard object detection metrics such as mAP, Precision, Recall, and Confusion Matrix.

---

## ✨ Features

- Ship detection in aerial images
- YOLO-based object detection
- Custom dataset training
- Automatic dataset configuration using YAML
- Model evaluation on test data
- Performance visualization
- Confusion Matrix
- mAP, Precision, and Recall metrics
- Easy inference on new images

---

## 📂 Dataset Structure

```
ships-aerial-images/
│
├── train/
│   ├── images/
│   └── labels/
│
├── valid/
│   ├── images/
│   └── labels/
│
├── test/
│   ├── images/
│   └── labels/
│
└── data.yaml
```

---

## 🛠 Technologies Used

- Python
- Ultralytics YOLO
- OpenCV
- NumPy
- Pandas
- Matplotlib
- Seaborn
- Kaggle Notebook

---

## 📦 Installation

Clone the repository

```bash
git clone https://github.com/YOUR_USERNAME/ship-detection-yolo.git
```

Move into the project folder

```bash
cd ship-detection-yolo
```

Install the required packages

```bash
pip install ultralytics
pip install opencv-python
pip install matplotlib
pip install seaborn
pip install pandas
pip install numpy
```

---

## 📁 Dataset

Download the Ship Detection dataset from Kaggle and place it in the appropriate directory.

Update the `data.yaml` file with the correct dataset path if necessary.

Example:

```yaml
path: /path/to/dataset

train: train/images
val: valid/images
test: test/images

nc: 1

names:
  0: ship
```

---

## 🚀 Training

```python
from ultralytics import YOLO

model = YOLO("yolo26n.pt")

model.train(
    data="data.yaml",
    epochs=20,
    imgsz=640,
    batch=64,
    workers=4,
    seed=42
)
```

---

## 📊 Model Evaluation

Evaluate the trained model using

```python
metrics = model.val(split="test")
```

Metrics include

- mAP@50
- mAP@50-95
- Precision
- Recall
- Confusion Matrix

---

## 🔍 Prediction

```python
from ultralytics import YOLO

model = YOLO("best.pt")

results = model.predict(
    source="image.jpg",
    conf=0.25,
    save=True
)
```

---

## 📈 Results

The project evaluates the model using:

- Mean Average Precision (mAP)
- Precision
- Recall
- Confusion Matrix
- Detection Examples

---

## 📷 Sample Output

Example output:

```
Input Image
        ↓
YOLO Detection
        ↓
Detected Ship
Confidence Score
Bounding Box
```

---

## 📁 Repository Structure

```
Ship-Detection-YOLO/
│
├── ship-detection.ipynb
├── data.yaml
├── README.md
├── requirements.txt
└── runs/
    └── detect/
        ├── train/
        └── predict/
```

---

## 🎯 Future Improvements

- Train on larger datasets
- Real-time ship detection
- Video object detection
- Deploy with Flask or FastAPI
- TensorRT optimization
- ONNX model export

---

## 👨‍💻 Author

**Muhammad Aftab Anwar**

AI & Deep Learning Developer

- Deep Learning
- Computer Vision
- Object Detection
- TensorFlow
- PyTorch
- YOLO

---

## ⭐ If you found this project useful

Please consider giving the repository a ⭐ on GitHub.
