# Sampling Assignment - Credit Card Fraud Detection
**Name:** Khushi Goyal  
**Roll Number:** 102303993  
**University:** Thapar Institute of Engineering & Technology  

## 📌 Project Overview
[cite_start]This project addresses the challenge of working with a highly imbalanced credit card dataset[cite: 11]. [cite_start]Real-world fraud detection datasets often contain very few fraud instances compared to legitimate transactions, which can significantly skew model performance[cite: 11]. 

The objective of this assignment is to:
1. [cite_start]Balance the dataset using oversampling[cite: 12, 17].
2. [cite_start]Apply five distinct sampling techniques to the balanced data[cite: 18, 19].
3. [cite_start]Evaluate the performance of five different machine learning models across these samples[cite: 20].
4. [cite_start]Identify which sampling technique provides the highest accuracy for each model[cite: 22].

## 🛠️ Methodology

### 1. Data Balancing
The original dataset was highly imbalanced (763 legitimate cases vs. 9 fraud cases). I utilized the `RandomOverSampler` to balance the classes, resulting in a dataset with an equal distribution (763:763).

### 2. Sampling Techniques
Five samples (S1-S5) were generated with a target size determined by the formula for finite populations:
* **Sampling 1: Simple Random Sampling** - Every element has an equal chance of being selected.
* **Sampling 2: Systematic Sampling** - Elements selected at fixed intervals ($k$) after a random start.
* **Sampling 3: Stratified Sampling** - Ensures equal representation of both classes in each sample.
* **Sampling 4: Cluster Sampling** - Dividing the population into clusters and randomly selecting entire clusters.
* **Sampling 5: Bootstrap Sampling** - Random sampling with replacement.

### 3. Machine Learning Models
The following models were trained on each of the five samples:
* **M1:** Logistic Regression
* **M2:** Decision Tree
* **M3:** Random Forest
* **M4:** Support Vector Machine (SVM)
* **M5:** K-Nearest Neighbors (KNN)

## 📊 Results Table
The models were evaluated on a consistent hold-out test set from the balanced data. The accuracy (%) results are as follows:

| Model | Sampling1 | Sampling2 | Sampling3 | Sampling4 | Sampling5 |
|-------|-----------|-----------|-----------|-----------|-----------|
| **M1** (Logistic Reg) | 91.83 | 92.81 | 92.48 | 86.27 | 93.46 |
| **M2** (Decision Tree) | 97.06 | 99.35 | 96.73 | 92.81 | 97.06 |
| **M3** (Random Forest) | 99.35 | **100.00** | **100.00** | 98.69 | 99.02 |
| **M4** (SVM) | 63.73 | 66.01 | 64.05 | 70.26 | 73.86 |
| **M5** (KNN) | 93.46 | 94.12 | 93.46 | 74.84 | 93.79 |

## 💡 Discussion and Conclusion
* **Top Performer:** **Random Forest (M3)** emerged as the most robust model, achieving 100% accuracy on both Systematic (Sampling 2) and Stratified (Sampling 3) samples.
* **Sampling Impact:** **Sampling 2 (Systematic)** and **Sampling 5 (Bootstrap)** generally provided higher accuracy across most models compared to Cluster Sampling (Sampling 4).
* **Observation:** The SVM model (M4) showed significantly lower accuracy compared to tree-based methods, suggesting that the non-linear boundaries in the resampled data were better captured by ensemble methods like Random Forest.

## 📁 Repository Structure
* `data/`: Contains the raw and balanced CSV data.
* `notebooks/`: Jupyter Notebook containing the full implementation code.
* `scripts/`: Python scripts for model utility functions.
* `requirements.txt`: List of dependencies required to run the project.