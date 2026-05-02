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

Note: The dataset is not included in this repository. Download it from Kaggle and place the CSV file inside a data/ folder.
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
└── .gitignore
```

---

## Approach

1. Data Loading

    The dataset is loaded using Pandas.

2. Text Preprocessing

    Important text columns are combined into one feature called combined_text.

    Columns used include:
    ```
    title
    company_profile
    description
    requirements
    benefits
    employment_type
    required_experience
    required_education
    industry
    function
    ```
3. Feature Extraction

    The combined job text is converted into numerical features using:
        ```
   TF-IDF Vectorization
        ```
   
5. Model Training

    A Logistic Regression model is trained to classify job postings as real or fake.

    The model uses:
   ```
   class_weight="balanced"
   ```
    This helps handle the imbalance between real and fake job postings.

7. Evaluation

    The model is evaluated using:
    ```
    Accuracy
    Precision
    Recall
    F1-score
    Confusion matrix
    ```
    Because fake postings are less common than real postings, F1-score and recall are especially important.

---

## How to Run the Project

1. Clone the repository
   ```
    git clone https://github.com/sea-rii/InternShield.git
    cd InternShield
   ```
   
2. Create and activate a virtual environment
     ```
    python -m venv venv
    source venv/bin/activate
    ```

For Windows:
    ```
    venv\Scripts\activate
    ```
    
3. Install dependencies
    ```
    pip install -r requirements.txt
    ```
     
4. Add the dataset

    Download the Kaggle dataset and place it here:
    ```
    data/fake_job_postings.csv
    ```

5. Open Jupyter Notebook
    ```
    jupyter notebook
    ```

    Then open:
    ```
    notebooks/01_fake_job_detector.ipynb
    ```

    Run all cells from top to bottom.

---

## Disclaimer

InternShield is an educational machine learning project. It should not be used as the only source of truth for determining whether a job posting is legitimate.

Users should always verify job postings through official company websites, recruiter profiles, and trusted career platforms before sharing personal information.

---

## Created By

**Sai Siri Chittineni**
