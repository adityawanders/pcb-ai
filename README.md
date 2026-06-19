# PCB-AI

AI-powered Computer Vision system for PCB component inspection and capacitor polarity marker classification.

## Project Overview

PCB-AI is a deep learning-based image classification system developed to identify the polarity marker orientation of electrolytic capacitors mounted on Printed Circuit Boards (PCBs).

The system classifies capacitor polarity markers into four categories:

* Top
* Right
* Bottom
* Left

The project serves as a foundation for automated PCB inspection and future polarity defect detection systems.

---

## Dataset

### Data Collection

| Stage                 | Images |
| --------------------- | -----: |
| Original Dataset      |    218 |
| Cleaned Dataset       |    174 |
| Final Labeled Dataset |    193 |

### Class Distribution

| Class  | Samples |
| ------ | ------: |
| Top    |      55 |
| Left   |      63 |
| Bottom |      43 |
| Right  |      32 |

### Preprocessing

* Auto orientation correction
* Resize to 224×224 pixels
* Pixel normalization
* Stratified train/validation/test split (80/10/10)

### Data Augmentation

The training dataset was augmented using:

* Brightness adjustment
* Contrast adjustment
* Translation
* Zoom
* Noise injection

A total of **18 augmentations per image** were generated.

**Note:** Rotation augmentation was intentionally excluded because capacitor orientation is the target feature.

---

## Model Architectures

### Custom CNN Models

* CNN_V1
* CNN_V2
* CNN_V3

### Transfer Learning Models

* MobileNetV2
* MobileNetV3
* MobileNetV3.1
* MobileNetV3.2
* ResNet50V2
* EfficientNetB0

---

## Training Configuration

### Common Settings

* Image Size: 224×224
* Optimizer: Adam
* Loss Function: Sparse Categorical Crossentropy
* Split Ratio: 80/10/10
* Evaluation Metrics:

  * Accuracy
  * Macro F1 Score
  * Per-Class F1 Scores
  * Test Loss

### Regularization Techniques

* Dropout
* L2 Regularization
* Early Stopping
* Model Checkpointing

---

## Experiment Tracking

Experiments were tracked using MLflow.

Logged Metrics:

* Test Accuracy
* Macro F1 Score
* Test Loss
* Bottom F1
* Left F1
* Right F1
* Top F1

---

## Experimental Results

| Rank | Model          | Accuracy (%) | Macro F1 (%) |   Loss | Epochs |
| ---- | -------------- | -----------: | -----------: | -----: | -----: |
| 🥇   | ResNet50V2     |        82.61 |        81.45 |   0.75 |      9 |
| 🥈   | MobileNetV3.2  |        82.61 |        80.00 | 0.8961 |      5 |
| 🥉   | EfficientNetB0 |        78.95 |        77.67 | 1.2998 |     17 |
| 4    | CNN_V3         |        78.95 |        77.38 | 1.6065 |     21 |
| 5    | MobileNetV3    |        78.26 |        67.00 | 1.3033 |      6 |
| 6    | CNN_V1         |        74.07 |        73.39 | 0.9833 |     11 |
| 7    | CNN_V2         |        74.07 |        72.64 | 1.3383 |     11 |
| 8    | MobileNetV2    |        73.68 |        71.02 | 1.8689 |     25 |
| 9    | MobileNetV3.1  |        65.22 |        58.00 | 1.2186 |      2 |

---

## Best Model Performance

### ResNet50V2

| Metric   |  Value |
| -------- | -----: |
| Accuracy | 82.61% |
| Macro F1 | 81.45% |
| Loss     |   0.75 |
| Epochs   |      9 |

### Per-Class F1 Scores

| Class  | F1 Score |
| ------ | -------: |
| Bottom |    66.67 |
| Left   |    92.00 |
| Right  |    91.00 |
| Top    |    80.00 |

---

## Key Findings

* ResNet50V2 achieved the best overall performance with 82.61% accuracy and 81.45% Macro F1 score.
* MobileNetV3.2 matched ResNet50V2 in accuracy while requiring fewer training epochs.
* EfficientNetB0 and CNN_V3 achieved comparable performance despite using fundamentally different architectures.
* CNN_V3 was the strongest custom architecture, demonstrating that a carefully designed CNN can compete with pretrained models.
* Macro F1 score provided a more balanced evaluation than accuracy alone due to class imbalance.
* The Right class generally achieved strong performance across most models, while the Bottom class remained the most challenging category.

---

## Evaluation

Model evaluation included:

* Accuracy
* Macro F1 Score
* Classification Reports
* Confusion Matrices
* Per-Class F1 Analysis

All evaluations were performed on an unseen test dataset.

---

## Tech Stack

* Python
* TensorFlow / Keras
* OpenCV
* NumPy
* Scikit-Learn
* Matplotlib
* MLflow
* Google Colab

---

## Project Structure

```text
PCB-AI/
│
├── dataset/
├── notebooks/
├── models/
├── mlruns/
├── train_model.py
├── evaluate_model.py
├── app.py
├── requirements.txt
└── README.md
```

---

## Future Work

* Capacitor detection using object detection models
* YOLO-based PCB component localization
* Automated polarity verification
* PCB defect detection
* Real-time PCB inspection pipeline
* Web deployment using Flask or Streamlit

---

## Author

Aditya Sarella

B.Tech Computer Engineering

Computer Vision & Deep Learning Project
