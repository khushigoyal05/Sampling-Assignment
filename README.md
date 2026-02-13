# Sampling Assignment
**Name:** Khushi Goyal  
**Roll Number:** 102303993  

## Project Overview
[cite_start]This project addresses a highly imbalanced credit card dataset[cite: 11]. [cite_start]The goal was to balance the data, apply five different sampling techniques, and evaluate five machine learning models[cite: 12].

## Methodology
1. **Balancing:** The original imbalanced dataset (763 legitimate, 9 fraud) was balanced using `RandomOverSampler` to create a dataset with 763 samples per class.
2. **Sampling Techniques:** - Simple Random Sampling
   - Systematic Sampling
   - Stratified Sampling
   - Cluster Sampling
   - Bootstrap Sampling
3. **Models:** Logistic Regression (M1), Decision Tree (M2), Random Forest (M3), SVM (M4), and KNN (M5).

## Results Table
| Model | Sampling1 | Sampling2 | Sampling3 | Sampling4 | Sampling5 |
|-------|-----------|-----------|-----------|-----------|-----------|
| M1    | 91.83     | 92.81     | 92.48     | 86.27     | 93.46     |
| M2    | 97.06     | 99.35     | 96.73     | 92.81     | 97.06     |
| M3    | 99.35     | 100.00    | 100.00    | 98.69     | 99.02     |
| M4    | 63.73     | 66.01     | 64.05     | 70.26     | 73.86     |
| M5    | 93.46     | 94.12     | 93.46     | 74.84     | 93.79     |

## Discussion
- **Best Model:** Random Forest (M3) consistently outperformed other models across all samples, reaching perfect accuracy on Systematic and Stratified samples.
- **Best Sampling Technique:** Sampling 2 (Systematic Sampling) and Sampling 5 (Bootstrap) yielded the highest overall accuracies across most models.
- **Observation:** SVM (M4) struggled compared to tree-based models, likely due to the high-dimensional nature of the PCA-transformed features in the credit card dataset.