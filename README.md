### 🧠 Predicting Treatment-Resistant Schizophrenia (TRS)

This repository contains the project developed for the **Introduction to Machine Learning (IAA)** laboratory at **UPC** (Academic Year 2025/26). The objective is to build a predictive model capable of identifying patients with schizophrenia who exhibit resistance to standard antipsychotic treatment (Treatment-Resistant Schizophrenia, TRS).

### Project Overview

Early identification of TRS remains a critical clinical challenge. This project leverages a multimodal dataset—incorporating clinical, genetic, and neuroimaging data from 9,000 patients—to provide decision support in medical environments through machine learning.

### Implemented Models

- **SVM (Support Vector Machine):** Developed using normalization preprocessing and Principal Component Analysis (PCA).
- **XGBoost:** Optimized specifically to handle class imbalance within the dataset.
- **Custom Logistic Regression:** Implemented from scratch using mini-batch gradient descent.
- **EBM (Explainable Boosting Machine):** The final selected model, chosen for its transparency and high recall.

### Selected Final Model: EBM

The **Explainable Boosting Machine (EBM)** was selected as the optimal solution due to its "glass-box" nature. This interpretability is essential in a real-world clinical setting, as it allows practitioners to understand the factors driving each individual prediction.

### Performance (Test Set)

- **Accuracy:** 0.59
- **Recall (TRS):** 0.59 (Prioritized to minimize clinical false negatives)
- **Precision (TRS):** 0.40
- **F1-Score:** 0.47

### Data Source and Citation

The clinical foundation and biomarkers utilized in this study are based on the research conducted by Khoodoruth et al. (2025):

- **Reference:** Khoodoruth, M. A. S., et al. (2025). "Peripheral inflammatory and metabolic markers as potential biomarkers in treatment-resistant schizophrenia: Insights from a Qatari Cohort." *Psychiatry Research*, 344, 116307. [https://doi.org/10.1016/j.psychres.2024.116307](https://doi.org/10.1016/j.psychres.2024.116307).
