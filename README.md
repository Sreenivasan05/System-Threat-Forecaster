#  System Threat Forecaster – Malware Infection Prediction

##  Project Overview

The **System Threat Forecaster** project aims to predict whether a machine is
infected by malware using system configuration, hardware, OS, and security
telemetry data.

This is a **binary classification problem**, where:
- `1` → Machine is infected
- `0` → Machine is not infected

The project follows a complete **end-to-end machine learning workflow**:
EDA → preprocessing → modeling → evaluation → Kaggle submission.

---

##  Problem Statement

Modern systems generate high-dimensional security telemetry. Identifying
patterns that indicate malware infection can help improve proactive threat
detection.

Given:
- A **training dataset** with system characteristics and infection labels
- A **test dataset** with only system characteristics

The objective is to build a model that accurately predicts malware infection
status for unseen machines.

---

##  Dataset Description

The dataset contains a mix of:
- **Hardware features** (RAM, disk, processor details)
- **OS features** (build versions, architecture, edition)
- **Security configuration** (firewall, real-time protection, TPM, secure boot)
- **Geographic & regional identifiers**
- **Temporal features** (OS update and malware signature dates)

The target variable is:
- `target` → malware infection status (binary)

---

##  Exploratory Data Analysis (EDA)

Key observations from EDA:

- Dataset contains **high-dimensional mixed feature types**
- Both **numerical and categorical features** are present
- **Missing values** and placeholder values (`UNKNOWN`, `Unspecified`) are common
- Categorical features exhibit **varying cardinality**
- Temporal features suggest **system update and malware signature patterns**
- No severe class imbalance in the target variable

These findings guided preprocessing and model selection decisions.

---


##  Modeling Approach

Multiple models were trained and evaluated:

### Models Used:
- Logistic Regression (baseline)
- LightGBM (gradient boosting)
- XGBoost (default and tuned)

### Evaluation Strategy:
- Train-validation split with stratification
- Accuracy, precision, recall, and F1-score
- ROC-AUC used during hyperparameter tuning

---

##  Final Model & Submission

- The **tuned XGBoost model** was selected as the final model
- The model was retrained on the **entire preprocessed training dataset**
- Predictions were generated for the test dataset using the same preprocessing
  pipeline
- A Kaggle submission file was created in the required format

###  Kaggle Result
- **Best Public Leaderboard Score:** **0.6362**

This score aligns well with offline validation performance, indicating good
generalization.

---

##  Tech Stack

- Python
- NumPy, Pandas
- Matplotlib
- Scikit-learn
- LightGBM
- XGBoost

---

[Kaggle competition link](https://www.kaggle.com/competitions/System-Threat-Forecaster)

