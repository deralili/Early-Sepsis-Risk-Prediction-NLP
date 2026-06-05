# Early Sepsis Risk Prediction from Clinical Notes Using Machine Learning and NLP

This repository contains the code, experiments, and documentation for my Major Research Project (MRP) in the Master of Data Science and Analytics program at Toronto Metropolitan University.

## Project Overview

Sepsis is a life-threatening condition caused by a dysregulated response to infection and remains a leading cause of mortality in intensive care units (ICUs). Early identification is critical because delays in treatment can significantly increase the risk of adverse outcomes.

This project investigates whether unstructured clinical notes can be used to predict sepsis risk during the early stages of ICU admission. Using the MIMIC-III critical care database, clinical notes from the first 24 hours of ICU admission are extracted and analyzed using Machine Learning and Natural Language Processing (NLP) techniques.

The study compares traditional machine learning approaches based on TF-IDF feature representations with transformer-based models such as ClinicalBERT.

## Objectives

* Construct a sepsis cohort using ICD-9 diagnosis codes.
* Extract and preprocess clinical notes from ICU admissions.
* Develop baseline machine learning models using TF-IDF features.
* Fine-tune ClinicalBERT for sepsis prediction.
* Compare model performance using clinically relevant evaluation metrics.
* Evaluate model interpretability using explainability techniques.

## Dataset

* MIMIC-III Clinical Database (PhysioNet)
* Adult ICU patients only
* First ICU stay per patient
* Clinical notes recorded within the first 24 hours of ICU admission

### Main MIMIC-III Tables Used

* ADMISSIONS
* PATIENTS
* ICUSTAYS
* DIAGNOSES_ICD
* NOTEEVENTS

### Processed Datasets

The preprocessing pipeline generates the following datasets:

* `sepsis_cohort.csv` – Final patient cohort after cohort construction and sepsis labeling.
* `first24h_notes.csv` – Clinical notes extracted from the first 24 hours of ICU admission.
* `clean_notes.csv` – Preprocessed clinical notes used for machine learning and NLP modeling.

Due to dataset size constraints and licensing considerations, the processed datasets are not stored in this repository. They can be reproduced by running the preprocessing notebooks provided in the `notebooks/` directory.

### Data Access

The original MIMIC-III database files are not included in this repository. Researchers interested in reproducing this work must obtain credentialed access through PhysioNet:

https://physionet.org/content/mimiciii/1.4/

## Project Workflow

Data Inspection → Cohort Creation → Note Extraction → Text Preprocessing → TF-IDF Models → ClinicalBERT → Model Evaluation → Explainability

## Repository Structure

```text
Early-Sepsis-Risk-Prediction-NLP/
│
├── notebooks/
│   ├── 01_Data_Inspection.ipynb
│   ├── 02_Cohort_Creation.ipynb
│   ├── 03_Note_Extraction.ipynb
│   ├── 04_Text_Preprocessing.ipynb
│   ├── 05_Baseline_TFIDF_Models.ipynb
│   ├── 06_ClinicalBERT_Model.ipynb
│   ├── 07_Model_Evaluation.ipynb
│   └── 08_Explainability.ipynb
│
├── outputs/
│
├── models/
│
├── reports/
│
├── README.md
├── requirements.txt
└── .gitignore
```

## Technologies

* Python
* Pandas
* NumPy
* Scikit-learn
* XGBoost
* PyTorch
* Hugging Face Transformers
* ClinicalBERT
* Jupyter Notebook

## Author

* Amadike Chidera Lilian
* Master of Data Science and Analytics
* Toronto Metropolitan University
