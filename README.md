# Ball-Bearing-Fault-Prediction-using-SVM-and-NTK
## 📌 Overview
This project explores the use of **Support Vector Machines (SVM) with Neural Tangent Kernel (NTK)** for predicting faults in ball bearings. Ball bearing failures can cause significant operational issues, and traditional fault detection methods often fall short due to data complexity. 

By leveraging NTK, which models the behavior of infinitely wide neural networks, we provide a robust kernel for SVM. This approach involves:

- **Preprocessing vibration signal data** 🛠️
- **Splitting data into training and testing sets** 📊
- **Computing the NTK using a neural network architecture** 🧠
- **Optimizing SVM hyperparameters via randomized search with cross-validation** 🔍
- **Evaluating model performance on unseen data** ✅

## 🚀 Features
- Uses **Support Vector Machines (SVM)** with **Neural Tangent Kernel (NTK)**
- Handles vibration signal data for predictive maintenance
- Hyperparameter tuning via **randomized search with cross-validation**
- Provides improved fault detection for industrial applications

## 📂 Project Structure
- `data/`: Contains datasets.
- `notebooks/`: Jupyter Notebooks for analysis.
## 📊 Results & Discussion

This section presents the **performance comparison** of different **Support Vector Machine (SVM) models** using **Linear Kernel, Radial Basis Function (RBF) Kernel, and Neural Tangent Kernel (NTK)**.

### 🔍 Summary of Model Performance
| **Kernel Type** | **Accuracy (%)** | **F1-Score (Weighted Avg.)** | **Best Hyperparameters** |
|---------------|----------------|---------------------|----------------|
| **Linear Kernel** | 93% | 0.93 | `C=100` |
| **RBF Kernel** | 71% | 0.68 | `C, gamma optimized` |
| **Best SVM Model** | 97% | 0.97 | `C=100, gamma=scale, kernel=linear` |
| **Neural Tangent Kernel (NTK)** | 95% | 0.95 | `C=59.97` |

---

## 📌 Classification Report Breakdown

### 1️⃣ Linear Kernel
- **Overall Accuracy:** **93%**
- **Best Performing Classes:**
  - **IR_014_1, OR_014_6_1, Normal_1** (100% precision and recall)
- **Challenging Classes:**
  - **OR_021_6_1** (72% precision, 81% recall)
- **Key Takeaway:**  
  - **Linear SVM performed well**, but struggled slightly with **OR_021_6_1** due to feature overlap.

### 2️⃣ RBF Kernel
- **Overall Accuracy:** **71%** (Much lower than Linear Kernel)
- **Best Performing Classes:**
  - **IR_007_1, IR_021_1, OR_014_6_1** (92-100% precision and recall)
- **Challenging Classes:**
  - **Ball_014_1 (1% recall!)** – Model completely fails to classify this class.
- **Key Takeaway:**  
  - **RBF Kernel is not well-suited** for this dataset.
  - The model **fails to classify Ball_014_1 correctly** and struggles with high-dimensional feature separation.

### 3️⃣ Best SVM Model (Tuned)
- **Overall Accuracy:** **97%**
- **Best Performing Classes:**
  - **IR_014_1, OR_014_6_1, Normal_1** (100% precision and recall)
- **Key Takeaway:**  
  - After **hyperparameter tuning (`C=100` and `gamma=scale`)**, the **Linear Kernel performed the best**, improving accuracy and stability.

### 4️⃣ Neural Tangent Kernel (NTK)
- **Overall Accuracy:** **95%**
- **Best Performing Classes:**
  - **IR_014_1, OR_014_6_1, Normal_1** (100% precision and recall)
- **Challenging Classes:**
  - **OR_021_6_1 (89% precision, 89% recall)**
- **Key Takeaway:**  
  - **NTK performs very well** and is comparable to the **Best SVM Model**.
  - It **captures feature relationships better** than RBF but takes longer to train.

---

## 📌 Visual Results
To help visualize model performance, below are the **confusion matrices** for each model:

### Confusion Matrix (Linear Kernel)
![image](https://github.com/user-attachments/assets/177e0a02-6d57-4f04-93ca-dbda2bf58c90)


### Confusion Matrix (RBF Kernel)
![image](https://github.com/user-attachments/assets/0548439d-1af3-44bd-9328-7b09338c591c)

### Confusion Matrix (NTK Kernel)
![image](https://github.com/user-attachments/assets/cc3bc075-f691-409d-8f73-7d62632a37a9)

---

## 📌 Discussion & Insights

### 💡 Key Observations
1. **Linear Kernel performed the best** after hyperparameter tuning, achieving **97% accuracy**.
2. **RBF Kernel struggled significantly**, with an accuracy drop to **71%**, failing on certain classes.
3. **Neural Tangent Kernel (NTK) was competitive** with **95% accuracy**, showing that deep kernel methods help in feature separation.
4. **Certain classes were harder to classify**:
   - **OR_021_6_1** was challenging for all models, indicating feature overlap.
   - **Ball_014_1 had almost 0% recall in RBF**, meaning it was often misclassified.

### 🚀 Recommendations
✅ **For Best Performance:** Use **Linear Kernel SVM** with hyperparameter tuning (`C=100`).  
✅ **If Deep Learning Methods Are Allowed:** NTK can be an alternative, as it generalizes well.  
✅ **For Future Improvements:**
   - **Feature Engineering** – Extract more meaningful features to help classification.
   - **Data Augmentation** – Increase dataset size to improve generalization.
   - **Try Deep Learning Models** – CNNs or RNNs could capture patterns better in vibration signals.

---

## 📌 Final Conclusion
- The **SVM with Linear Kernel (after hyperparameter tuning)** performed **the best**, achieving **97% accuracy**.
- **Neural Tangent Kernel (NTK)** was slightly behind with **95% accuracy**, showing potential for advanced kernel methods.
- **RBF Kernel performed the worst**, likely due to poor feature separation.
- This study highlights the **importance of kernel selection in SVM models** for fault detection in ball bearings.

---


## Setup Instructions
1. **Clone the repository:**
   ```bash
   git clone https://github.com/Wjha2/Ball-Bearing-Fault-Prediction-using-SVM-and-NTK.git
   cd Ball-Bearing-Fault-Prediction-using-SVM-and-NTK
