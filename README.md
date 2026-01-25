# NLP_Pipeline

# 📌 Sentiment Analysis with Logistic Regression (Three-Class Classification)

## Overview
This project implements a **three-class sentiment analysis system** using classical **Natural Language Processing (NLP)** techniques and **Logistic Regression**.  
Each text sample is classified into one of the following sentiment categories:

- **1** → Positive sentiment  
- **0** → Neutral sentiment  
- **-1** → Negative sentiment  

The workflow covers **text preprocessing, baseline rule-based scoring, feature extraction, model training, hyperparameter tuning, and evaluation**.

---

## Dataset
The dataset consists of movie review texts and sentiment labels, divided into:

- **Training set**
- **Validation set**
- **Test set**

Each record contains:
- **X** → Review text  
- **y** → Sentiment label (`1`, `0`, `-1`)

The data is loaded directly from **IBM Cloud Object Storage**.

---

## Text Preprocessing
The following preprocessing steps are applied to the text data:

- **Lowercasing** using `casefold()` for consistent word matching
- **Tokenization** using Python string splitting
- Inspection of text structure at both character and word level

These steps ensure uniformity across the dataset before feature extraction.

---

## Rule-Based Sentiment Scoring (Baseline)
Before applying machine learning, a simple **lexicon-based baseline approach** is implemented:

- A predefined list of **positive words** (e.g., *good, great, excellent*)
- A predefined list of **negative words** (e.g., *bad, dreadful, disastrous*)

For each review:
- The sentiment score **increases** when positive words are found
- The sentiment score **decreases** when negative words are found

This provides a **baseline sentiment prediction** for comparison with the machine learning model.

---

## Exploratory Analysis
Basic exploratory analysis is performed, including:

- Printing sample reviews from each sentiment class
- Identifying reviews with the highest and lowest sentiment scores
- Calculating average sentiment scores per class
- Visualizing sentiment score distributions using histograms

This helps validate that the scoring mechanism aligns with sentiment labels.

---

## Feature Extraction (Bag of Words)
Text data is converted into numerical form using **CountVectorizer**:

- Each document is represented as a vector of word counts
- A vocabulary is learned from the training data
- Sparse matrix representations are used for efficiency

A toy example is included to clearly demonstrate how words are mapped to numerical features.

---

## Model Training
A **Logistic Regression** classifier is trained using:

- Bag-of-words features
- Multiclass classification
- Regularization to reduce overfitting
