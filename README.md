# 📊 Human Activity Recognition

This project classifies human activities (e.g., walking, sitting, standing) from smartphone sensor data using machine learning.

## 📁 Dataset Overview

- **Source**: [UCI HAR Dataset](https://archive.ics.uci.edu/ml/datasets/human+activity+recognition+using+smartphones)
- **Subjects**: 30 participants (age 19–48)
- **Device**: Samsung Galaxy S II
- **Sensors**: Accelerometer & Gyroscope (3-axial)
- **Activities**: Walking, Walking Upstairs, Walking Downstairs, Sitting, Standing, Laying

## 🛠️ Data Preprocessing

- Applied **Butterworth & median filtering** to reduce sensor noise.
- Segmented into **2.56s windows** (128 readings) with **50% overlap**.
- Extracted **561 features** from time/frequency domains.
- Features normalized to the range **[-1, 1]**.

- Noise Filtering:
**Median filter and 3rd order Butterworth filter (20 Hz)**
**Gravity separation with 0.3 Hz low-pass filter**
- Segmentation:
**2.56s sliding windows (128 samples/window) with 50% overlap**
- Feature Extraction:
**561 time- and frequency-domain features per window**
**Includes mean, std, entropy, FFT energy, skewness, kurtosis, etc.**
- Normalization:
**All features scaled to [-1, 1]**

📂 Data Structure
X_train.txt, X_test.txt: Feature vectors (561 features)
y_train.txt, y_test.txt: Activity labels
subject_train.txt, subject_test.txt: Participant IDs
Additional raw signal data in /Inertial Signals/ for custom feature engineering

## Utility of pre-processing steps

Ensure noise reduction and better signal clarity
Preserve temporal patterns in sensor data
Standardize inputs for model convergence
Prevent overfitting by subject-aware train/test split
