# 📊 CWRU Bearing Dataset Overview

## 🔍 About the Dataset
The **CWRU Bearing Dataset** is a widely used dataset in **predictive maintenance and fault detection** for rolling element bearings. It was collected by **Case Western Reserve University (CWRU)** and contains **vibration signal measurements** recorded from electric motors under different fault conditions. These faults include:
- **Ball Defects**  
- **Inner Race Defects (IR)**  
- **Outer Race Defects (OR)**  
- **Normal Operation**  

The dataset provides **pre-extracted time-domain features** from raw vibration signals, enabling machine learning models to classify different bearing conditions effectively.

---

## 📂 Dataset File: `feature_time_48k_2048_load_1.csv`
This dataset file contains **pre-processed statistical features** extracted from vibration signals. It was sampled at **48 kHz**, using a **2048-sample window size**, under a specific load condition (`load_1`).

### **🛠 Features in the Dataset**
Each row in the dataset represents vibration signal measurements for a given time window. The features include:

✅ **Time-domain statistical metrics:**
- **Mean** – Average signal amplitude.
- **Standard Deviation** – Measure of signal dispersion.
- **Skewness** – Indicates asymmetry in the signal distribution.
- **Kurtosis** – Measures the sharpness or flatness of the signal peak.
- **Root Mean Square (RMS)** – Represents the power content of the signal.
- **Peak-to-Peak Amplitude** – Maximum signal variation.
- **Crest Factor** – Ratio of peak value to RMS, useful for detecting impulsive faults.

✅ **Target Variable (`fault`)**
- Labels each row based on the specific bearing condition.
- Possible values include:
  - **Ball_007_1**, **Ball_014_1**, **Ball_021_1** (Ball Defects)
  - **IR_007_1**, **IR_014_1**, **IR_021_1** (Inner Race Defects)
  - **OR_007_6_1**, **OR_014_6_1**, **OR_021_6_1** (Outer Race Defects)
  - **Normal_1** (Healthy Bearing)

---

## 🔗 Dataset Source
The dataset is publicly available on **Kaggle**:  
[CWRU Bearing Dataset on Kaggle](https://www.kaggle.com/datasets/brjapon/cwru-bearing-datasets?select=feature_time_48k_2048_load_1.csv)

---

## 📌 Why This Dataset?
This dataset is crucial for **machine learning applications in predictive maintenance**, as it helps engineers and researchers develop algorithms that can:
✅ **Detect early-stage bearing failures**  
✅ **Reduce downtime and maintenance costs**  
✅ **Enhance industrial system reliability**  

This makes it an excellent dataset for Supervised Machine Learning and Deep Learning applications in fault detection and condition monitoring.

---

## 📜 How to Use This File in the Project
1. **Download the dataset** from the Kaggle link provided.
2. **Ensure the dataset is placed inside the `data/` folder** in this repository.
3. **Run the Jupyter Notebook (`Ball_Bearing_Fault_Prediction.ipynb`)**, which processes and uses this dataset for training machine learning models.

---
