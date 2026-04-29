# InternShield

**InternShield** is a machine learning project that detects potentially fraudulent job and internship postings using Natural Language Processing (NLP).

The goal of this project is to help students and job seekers identify suspicious postings before sharing personal information, accepting fake offers, or engaging with scam recruiters.

---

## Problem Statement

Fake job postings often target students and early-career job seekers with:

- Unrealistic pay
- Vague job descriptions
- Urgent hiring language
- “No experience required” claims
- Suspicious check or equipment purchase instructions
- Requests for sensitive personal information

InternShield uses machine learning to classify job postings as likely real or potentially fraudulent, while also providing a scam risk score and red-flag explanation.

---

## Project Overview

This project takes a job posting as input and predicts whether it is likely to be:

- **Likely Legit**
- **Suspicious**
- **High Risk Scam**

The model is trained on job posting text using TF-IDF features and a Logistic Regression classifier.

---

## Features

- Detects potentially fake job or internship postings
- Generates a scam risk score
- Uses NLP to analyze job posting text
- Combines multiple job fields into one text-based model input
- Includes rule-based red flag detection for better explainability
- Tests custom job posting examples
- Evaluates performance using classification metrics

---

## Tech Stack

- Python
- Jupyter Notebook
- Pandas
- NumPy
- Scikit-learn
- SciPy
- Matplotlib
- Joblib

---

## Dataset

This project uses the **Real / Fake Job Posting Prediction** dataset from Kaggle.

The dataset contains real and fraudulent job postings with fields such as:

- Job title
- Company profile
- Description
- Requirements
- Benefits
- Employment type
- Required experience
- Required education
- Industry
- Function
- Fraudulent label

The target column is:

```
fraudulent
Where:
0 = real job posting
1 = fake job posting
> Note: The dataset is not included in this repository. Download it from Kaggle and place the CSV file inside a data/ folder.
```

Expected structure:
```
InternShield/
├── data/
│   └── fake_job_postings.csv
├── notebooks/
│   └── 01_fake_job_detector.ipynb
├── models/
│   ├── fake_job_model.pkl
│   └── tfidf_vectorizer.pkl
├── README.md
├── requirements.txt
```
└── .gitignore
