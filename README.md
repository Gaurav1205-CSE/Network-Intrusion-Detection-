# Intelligent Network Intrusion Detection System using Machine Learning

[![Python](https://img.shields.io/badge/Python-3.x-blue.svg)](https://www.python.org/)
[![Scikit-Learn](https://img.shields.io/badge/scikit--learn-Latest-orange.svg)](https://scikit-learn.org/)
[![Streamlit](https://img.shields.io/badge/Streamlit-App-red.svg)](https://streamlit.io/)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](https://opensource.org/licenses/MIT)

An Intelligent Network Intrusion Detection System (INIDS) designed to automatically learn patterns from network traffic data and classify connections as normal or malicious. This project demonstrates the implementation of supervised machine learning algorithms to effectively categorize network attacks into **DoS, Probe, R2L, and U2R** categories, while addressing the limitations of traditional signature-based Intrusion Detection Systems (IDS).

This project was developed as part of the **Practical School-II (PS1102)** course at **JK Lakshmipat University, Jaipur**.

---

## 📋 Table of Contents
- [Project Overview](#project-overview)
- [Problem Statement](#problem-statement)
- [Dataset](#dataset)
- [Technology Stack](#technology-stack)
- [Implemented Features](#implemented-features)
- [Model Performance](#model-performance)
- [Streamlit Dashboard](#streamlit-dashboard)
- [Installation and Setup](#installation-and-setup)
- [Author & Acknowledgements](#author--acknowledgements)

---

## 🎯 Project Overview
With the rapid growth of digital communication, network security is a critical challenge. Traditional signature-based IDS are limited against zero-day attacks and suffer from high false positive rates. This project utilizes machine learning to generalize from training data, allowing the system to adapt to new threats over time.

**Key Objectives:**
- Design and implement an ML-based IDS using the benchmark **NSL-KDD dataset**.
- Classify network traffic as `Normal` or into 4 attack categories: `DoS` (Denial of Service), `Probe`, `R2L` (Remote to Local), and `U2R` (User to Root).
- Evaluate and compare multiple ML algorithms to maximize detection accuracy and minimize false alarms.

---

## 🚨 Problem Statement
Existing signature-based systems face critical limitations:
1. Inability to detect unknown/zero-day attacks.
2. High false-positive rates causing alert fatigue.
3. Lack of proper classification limiting targeted defensive actions.
4. Heavy reliance on constant manual rule updates.

**INIDS** addresses these by adopting a data-driven approach that learns anomalous behaviors directly from network traffic statistics and payload features.

---

## 📊 Dataset
The system is trained and evaluated using the **[NSL-KDD Dataset](https://www.unb.ca/cic/datasets/nsl.html)**, which is an improved version of the KDDCup 1999 dataset. It contains 41 features per connection (derived from TCP/IP headers, content payloads, and traffic statistics).

- **Training Set:** 125,973 records
- **Test Set:** 22,544 records

---

## 🛠️ Technology Stack
- **Language:** Python 3.x
- **Data Manipulation & Analysis:** Pandas, NumPy
- **Machine Learning:** Scikit-Learn
- **Feature Selection:** Recursive Feature Elimination (RFE)
- **Data Visualization:** Matplotlib, Seaborn
- **Web App / UI:** Streamlit, Pyngrok
- **Environment:** Jupyter Notebook / Google Colab

---

## ⚙️ Implemented Features
- **Robust Preprocessing Pipeline:** Automated handling of categorical encoding (Label Encoding, One-Hot Encoding), missing values, and Feature Scaling (StandardScaler).
- **Feature Selection:** Utilized RFE with Random Forest to extract the most significant features for each attack class.
- **Multiple Classifications:**
  - **Binary Classification:** Identifies traffic as simply `Normal` or `Attack`.
  - **Multi-Class (5-Class) Classification:** Categorizes attacks into `Normal`, `DoS`, `Probe`, `R2L`, and `U2R`.
- **Model Implementations:** - Random Forest Classifier (Best Performing)
  - Logistic Regression
  - Support Vector Machines (LinearSVC)
  - K-Nearest Neighbors (KNN) & Decision Trees (Baseline)

---

## 📈 Model Performance
*Performance metrics based on the NSL-KDD Test Set:*

### 1. Binary Random Forest Model (Normal vs Attack)
- **Accuracy:** ~99.56%
- **Precision (Attack):** 1.00
- **Recall (Attack):** 0.99 

### 2. Multi-Class (5-Class) Random Forest Model
- **Overall Accuracy:** ~70.25% (Class-weight balanced for highly imbalanced attack classes like U2R)
- *Note: Ensemble methods strongly outperformed linear baseline models on this dataset.*

### 3. Binary Support Vector Machine (LinearSVC)
- **Accuracy:** ~81.33%

---

## 🖥️ Streamlit Dashboard
An interactive real-time dashboard is built using Streamlit. Features include:
1. **Data Preview:** Upload custom `.csv` or `.txt` network capture logs for batch prediction.
2. **Visualizations:** Bar graphs illustrating the volume of `Normal` vs. `Attack` traffic, and detailed 5-class category distributions.
3. **Evaluation Metrics:** On-the-fly display of Precision, Recall, F1-Score, and Support.
4. **Single Traffic Analysis:** Manually input connection features (duration, protocol type, flags, etc.) to get an instant prediction of the traffic type.

---

## 🚀 Installation and Setup

1. **Clone the Repository:**
   ```bash
   git clone [https://github.com/Gaurav1205-CSE/Network-Intrusion-Detection-.git](https://github.com/Gaurav1205-CSE/Network-Intrusion-Detection-.git)
   cd Network-Intrusion-Detection-
