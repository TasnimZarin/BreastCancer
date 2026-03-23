# 🔬 Breast Cancer Detection

A deep-learning project to detect **Invasive Ductal Carcinoma (IDC)** from breast histopathology image patches using transfer learning with three pre-trained models:

- VGG16
- InceptionV3
- ResNet50

---

## 📚 Project Overview

- **Goal:** Binary classification — detect cancerous (IDC+) vs non-cancerous (IDC−) patches from histopathology slides
- **Pipeline:** Data preparation → Transfer learning → Evaluation (accuracy, precision, recall, F1, confusion matrix)
- **Key Finding:** ResNet50 achieved the highest accuracy at 92%, outperforming VGG16 (80%) and InceptionV3 (88%)

---

## 🗂️ Dataset

- - Source: [Kaggle — Breast Histopathology Images](https://www.kaggle.com/datasets/paultimothymooney/breast-histopathology-images) — 277,524 image patches (50×50px) from 162 patients
- Used a balanced subset of **4,000 images** (2,000 IDC+, 2,000 IDC−)
- Split: 70% train / 15% validation / 15% test

---

## ⚙️ Preprocessing

- Resized all images to model-specific input sizes
- Normalized using ImageNet mean/std
- Applied data augmentation: horizontal flip, rotation, zoom
- Used PyTorch/Keras DataLoaders for pipeline management

---

## 🧠 Models

| Model | Architecture | Test Accuracy |
|---|---|---|
| VGG16 | 16-layer deep CNN | 80% |
| InceptionV3 | Inception modules | 88% |
| ResNet50 | Residual connections | 92% |

All models used:
- Pre-trained ImageNet weights (frozen base layers)
- Custom classification head with sigmoid output
- Dropout for regularization
- EarlyStopping to prevent overfitting

---

## 📊 Results

- **Best model:** ResNet50 at 92% test accuracy
- Evaluated with confusion matrices, precision, recall, and F1-score
- ResNet50's residual connections provided the best generalization on histopathology data

---

## 🛠️ Tech Stack

- **Language:** Python
- **Frameworks:** TensorFlow/Keras, PyTorch
- **Models:** VGG16, InceptionV3, ResNet50
- **Libraries:** scikit-learn, NumPy, Matplotlib, PIL
- **Techniques:** Transfer Learning, EarlyStopping, Dropout, Data Augmentation
- **Metrics:** Accuracy, Precision, Recall, F1-score, Confusion Matrix
