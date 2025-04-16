# Human Activity Recognition

This project classifies human activities (e.g., walking, sitting, standing) from smartphone sensor data using machine learning.

## Dataset Overview

- **Source**: [UCI HAR Dataset](https://archive.ics.uci.edu/ml/datasets/human+activity+recognition+using+smartphones)
- **Subjects**: 30 participants (age 19–48)
- **Device**: Samsung Galaxy S II
- **Sensors**: Accelerometer & Gyroscope (3-axial)
- **Activities Tracked**:
  - WALKING  
  - WALKING_UPSTAIRS  
  - WALKING_DOWNSTAIRS  
  - SITTING  
  - STANDING  
  - LAYING

##  Data Preprocessing

- **Noise Filtering**:  
  Applied a median filter and 3rd order Butterworth low-pass filter (20 Hz) to reduce sensor noise.  
  Additional Butterworth filter (0.3 Hz) used to separate **gravity** and **body motion** components.

- **Segmentation**:  
  Sensor data is split into sliding windows of **2.56 seconds** (128 samples/window) with **50% overlap**.

- **Feature Extraction**:  
  Extracted **561 features** from each window using both time- and frequency-domain signals:  
  `mean`, `std`, `entropy`, `correlation`, `energy`, `skewness`, `kurtosis`, `angle`, `bandsEnergy`, etc.

- **Normalization**:  
  All features are scaled between **[-1, 1]** to ensure balanced input to the model.


## Data Structure

**Feature vectors (561 features)**: X_train.txt, X_test.txt
**Activity labels**: y_train.txt, y_test.txt
**Participant IDs**: subject_train.txt, subject_test.txt
Additional raw signal data in /Inertial Signals/ for custom feature engineering

## Utility of pre-processing steps

 Step               | Purpose                                                             |
|--------------------|---------------------------------------------------------------------|
| Filtering          | Removes high-frequency noise and isolates meaningful patterns       |
| Sliding Windows    | Preserves temporal patterns from continuous sensor data             |
| Feature Extraction | Converts raw signal into informative statistical and spectral data  |
| Normalization      | Prevents model bias and speeds up convergence                       |
| Subject Split      | Prevents overfitting and ensures generalization to unseen subjects  |

---

