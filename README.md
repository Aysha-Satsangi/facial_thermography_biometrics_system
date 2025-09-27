# Facial Thermography Analysis

A deep learning project for **facial thermal image analysis** to detect patterns and anomalies. This project demonstrates the use of computer vision and machine learning techniques for biometrics, health monitoring, and pattern recognition.

---

## Table of Contents
- [Overview](#overview)
- [Features](#features)
- [Dataset](#dataset)
- [Technologies](#technologies)
- [Results](#results)


---

## Overview
Facial thermography captures temperature variations across the human face. This project processes thermal images to extract features and detect anomalies. It uses Convolutional Neural Networks (CNNs) to classify patterns and provide accurate predictions.

---

## Features
- Preprocessing of thermal facial images for normalization and noise reduction.
- CNN-based model training for pattern recognition and anomaly detection.
- Real-time predictions on new facial thermal images.
- Training, validation, and testing monitoring with performance metrics.
- Supports scalable dataset integration for future improvements.

---

## Dataset
- **Training samples:** 1824 images  
- **Test samples:** 462 images  
- Images are labeled for pattern/anomaly detection.  
- *(Note: If using a public dataset, mention source. If private/custom dataset, note accordingly.)*

---

## Technologies
- Python 3.12  
- Keras / TensorFlow  
- OpenCV for image preprocessing  
- NumPy & Pandas for data handling  
- Matplotlib & Seaborn for visualization  

---

## Results

Training Accuracy: ~95.65%

Validation Accuracy: ~85%

Test Accuracy: 83.98%

The model effectively detects anomalies and patterns in facial thermal images with high reliability.
