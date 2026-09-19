# Sign Language Detection using YOLOv5

A custom Sign Language Detection project using **YOLOv5**, **Python**, **Roboflow**, and **OpenCV** to detect and classify sign-language gestures from images.

The model is trained on a custom annotated dataset containing **6 sign-language classes** and is capable of detecting the corresponding gesture along with a bounding box and class label.

---

## 📌 Project Overview

Sign language provides an important means of communication for people with hearing or speech disabilities. This project aims to detect commonly used sign-language gestures from images using an object detection approach.

A custom dataset was collected and annotated using **Roboflow**, then used to train a customized **YOLOv5s** object detection model.

The trained model can identify the following sign-language gestures:

- Hello
- I Love You
- No
- Please
- Thanks
- Yes

The current implementation focuses on **image-based sign-language detection**.

---

## 🚀 Features

- Custom sign-language dataset
- Image annotation using Roboflow
- YOLO-format dataset preparation
- Custom YOLOv5 model training
- Model validation and evaluation
- Detection of sign-language gestures from images
- Bounding-box visualization
- Class-label prediction for detected gestures
- Performance evaluation using Precision, Recall, mAP@0.5, and mAP@0.5:0.95

---

## 🛠️ Technologies Used

- **Python**
- **YOLOv5**
- **PyTorch**
- **OpenCV**
- **Roboflow**
- **Google Colab**
- **NumPy**
- **Matplotlib**
- **Git & GitHub**

---

## 📂 Project Structure

```text
SignLanguageDetection1/
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
├── yolov5/
│   ├── models/
│   ├── detect.py
│   ├── train.py
│   ├── val.py
│   └── ...
│
├── data.yaml
├── Sign_language_data.zip
├── Untitled2.ipynb
└── README.md
```

---

## 🚀 Project Workflow

```text
Image Collection
       ↓
Image Annotation
       ↓
Dataset Preparation using Roboflow
       ↓
YOLOv5 Training
       ↓
Model Evaluation
       ↓
Sign Detection on Images
```
---
## 📈 Model Performance

The trained model was evaluated on the validation dataset using YOLOv5's evaluation metrics.

<img width="836" height="332" alt="Screenshot 2026-09-19 193639" src="https://github.com/user-attachments/assets/62fd0ea0-672d-4a4b-a55f-3c43cccc9d79" />

## 🔍 Image Detection

After training, the model can be tested on unseen images.

Example detection command:

```text
python detect.py \
    --weights runs/train/yolov5s_results/weights/best.pt \
    --img 416 \
    --conf 0.5 \
    --source path/to/image.jpg
```

The model generates an output image containing:

Bounding box around the detected hand/sign
Predicted sign-language class
Confidence score

Detection results are saved inside:
```text
runs/detect/
```

## 💻 Running the Project
1. Clone YOLOv5

```text
git clone https://github.com/ultralytics/yolov5.git
```

3. Move into the YOLOv5 directory

```text
cd yolov5
```

5. Install dependencies
```text
pip install -r requirements.txt
```

7. Train the model

Use the training command described above.

5. Run image detection

```text
python detect.py \
    --weights runs/train/yolov5s_results/weights/best.pt \
    --img 416 \
    --conf 0.5 \
    --source path/to/image.jpg
```
### 📁 Output

After detection, YOLOv5 saves the resulting images in:

```text
runs/detect/exp/
```

The output contains the predicted sign label and bounding box around the detected gesture.

## 🔬 Model Improvement

Potential improvements for future versions include:

- Increasing the size of the training dataset
- Collecting images from different backgrounds
- Using different lighting conditions
- Including different hand positions and distances
- Improving class balance
- Improving annotation quality
- Increasing input resolution from 416 to 640
- Experimenting with additional YOLOv5 model sizes
- Adding more sign-language classes
- Testing on a larger unseen dataset
