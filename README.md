# Hypoxia Explainability using SHAP

This repository provides an explainability-focused analysis for the prediction of fetal hypoxia / IUGR using **Logistic Regression** and **SHAP (SHapley Additive exPlanations)**.

This project is an extension of the main Hypoxia ML model and focuses exclusively on **interpreting model decisions** using non-invasive Doppler ultrasound features.

---

## Dataset

The dataset is **not included** in this repository due to medical privacy restrictions.

To run the notebook, place the dataset in the project folder with the name: Overall_dataset_noninvasive.xlsx

Final non-invasive features used (same as the main project):

- **Gestational_Age**  
- **Maternal_Age**  
- **PI_MCA**  
- **PI_UA**  
- **PI_MCA_UA** (Cerebroplacental Ratio)

Target label encoding:
- **Normal → 0**  
- **IUGR → 1**

---

## Methods

### 1. Model
A **Logistic Regression** model is trained with:
- Standardized features  
- 80/20 train-test split  
- Balanced class weights to handle class imbalance  

### 2. Explainability (SHAP)
We use SHAP to understand how each Doppler feature contributes to prediction outcomes.

The notebook generates:

#### Global Explanations
- **Beeswarm plot:** Distribution of feature contributions  
- **Bar plot:** Ranked feature importance  

#### Local Explanations
- **Waterfall plot:** Case-level reasoning showing which features push a prediction toward IUGR vs Normal  

These results help reveal the underlying physiological patterns the model relies on.

---

## Notebook

All analysis is contained in: 
Hypoxia_SHAP_Explainability.ipynb


You can run it in **Google Colab** or any Python/Jupyter environment with SHAP installed.

---

## Installation

Install dependencies with:
pip install -r requirements.txt


---

## Privacy Note
The data used in this analysis involve clinical, non-invasive Doppler features.  
The dataset is not distributed publicly. Users must provide their own local copy.

---

## Project Purpose

This repository demonstrates:

- Transparent machine-learning decision support  
- Clinically meaningful explainability  
- How Doppler ultrasound features influence IUGR prediction  
- Integration of SHAP with classical statistical ML models  

It complements the main hypoxia prediction project by focusing exclusively on model interpretation rather than classification performance.

### Interpretation Summary
SHAP analysis confirmed that **PI_UA**, **PI_MCA**, and their ratio (PI_MCA_UA)** have the largest influence on model predictions. Higher PI_UA values strongly pushed cases toward the IUGR class, while higher PI_MCA pulled predictions toward Normal.  
The waterfall plots also showed that individual predictions were driven by intuitive Doppler patterns, demonstrating that the logistic model behaves in a physiologically consistent and transparent way.








