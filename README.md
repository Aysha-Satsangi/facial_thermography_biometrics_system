# Thermal Face Recognition using MobileNetV2

A robust and efficient deep learning pipeline for biometric identification using thermal infrared face images. This project implements a full system—data preprocessing, augmentation, transfer learning, evaluation, and benchmarking—built on the MobileNetV2 architecture.

---

## Table of Contents

- [Project Overview](#project-overview)
- [System Architecture](#system-architecture)
- [Dataset & Preprocessing](#dataset--preprocessing)
- [Model Architecture](#model-architecture)
- [Training & Evaluation](#training--evaluation)
- [Results](#results)
- [Performance Benchmarking](#performance-benchmarking)
- [How to Run](#how-to-run)
- [Applications](#applications)
- [Challenges & Next Steps](#challenges--next-steps)
- [References](#references)

---

## Project Overview

This project addresses the challenge of reliable face recognition in low/variable lighting and spoof-prone scenarios. By leveraging thermal imaging and modern deep learning (CNN, transfer learning), it enables:

- **Biometric identification irrespective of external light**
- **Contactless authentication** suitable for hygienic or secure environments
- **State-of-the-art accuracy** with efficient deployment on resource-limited hardware

---

## System Architecture


**Modules:**
- **Thermal Camera Input**: Captures 128×128 grayscale thermal images
- **Preprocessing**: Grayscale→RGB, normalization, augmentation
- **MobileNetV2 Backbone**: Pre-trained feature extractor (ImageNet weights)
- **Custom Classification Head**: Dense(256, L2)+Dropout+Softmax(18)
- **Output**: ID of the recognized subject
- **Database Storage**: For features and authorized user templates
- **User Interface**: Enrollment, monitoring, and management

---

## Dataset & Preprocessing

- **Total Samples:** 18,220 training images, 4,564 testing images, 18 classes
- **Image Processing:** Conversion to 128×128 RGB, normalization to [0,1]
- **Augmentation:** Rotation, shift, zoom, horizontal flip (boosts robustness)
- **Label Encoding:** Integer conversion and one-hot vectors

---

## Model Architecture

- **Backbone:** MobileNetV2 (pre-trained, frozen/unfrozen in phases)
- **Head:** Flatten → Dense(256, L2 regularization, ReLU) → Dropout(0.4) → Softmax(18)
- **Parameters:** ~7.5 million; size: ~28.6MB

---

## Training & Evaluation

### Strategy
- Phase 1 (Feature Extraction): Freeze backbone, train head, lr=1e-3, 10 epochs
- Phase 2 (Fine-tuning): Unfreeze last 100 layers, lr=1e-5, 6 epochs
- **Callbacks:** EarlyStopping, ReduceLROnPlateau  
- **Loss:** Categorical cross-entropy  
- **Metrics:** Accuracy, Precision, Recall, F1-score (per-class)

### Typical Commands

Validation Accuracy: ~85%

Test Accuracy: 83.98%

The model effectively detects anomalies and patterns in facial thermal images with high reliability.
