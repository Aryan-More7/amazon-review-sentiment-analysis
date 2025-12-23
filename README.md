# Amazon Review Sentiment Analysis

This project performs supervised sentiment analysis on large-scale Amazon customer reviews.  
The goal is to classify reviews as **positive** or **negative** based on review text and to understand what language drives sentiment predictions.

## Project Summary

Customer reviews contain valuable information about product quality and user satisfaction.  
In this project, I built an end-to-end sentiment analysis pipeline that processes Amazon review text and classifies reviews as either **positive** or **negative** sentiment.

The analysis uses text preprocessing, TF-IDF feature extraction, and a Logistic Regression classifier to learn patterns in customer feedback.  
In addition to model performance, the project includes visual analysis to better understand customer behaviour and model decision-making.

## Dataset

The project uses the **Amazon Reviews Polarity dataset** released by the Stanford Network Analysis Project (SNAP).

- Source: Amazon product reviews collected over an 18-year period
- Labels:
  - `1` → Negative sentiment (ratings 1–2)
  - `2` → Positive sentiment (ratings 4–5)
- Neutral reviews (rating 3) are excluded
- Each review includes:
  - Review title
  - Review text

Due to the large size of the dataset, a representative sample was used for training and evaluation to ensure efficient processing while preserving sentiment balance.

## Methodology

The sentiment analysis pipeline follows these steps:

1. **Data preparation**
   - Filter valid sentiment labels
   - Convert labels to binary format (negative = 0, positive = 1)
   - Combine review title and review text into a single input

2. **Text preprocessing**
   - Convert text to lowercase
   - Remove punctuation and unnecessary characters
   - Normalise whitespace

3. **Feature extraction**
   - Convert cleaned text into numerical features using **TF-IDF**
   - Use unigrams and bigrams to capture important words and short phrases
   - Limit vocabulary size to control model complexity

4. **Model training**
   - Train a **Logistic Regression** classifier on the TF-IDF features
   - Learn which words and phrases are associated with positive and negative sentiment

5. **Evaluation**
   - Test the model on unseen reviews
   - Measure performance using accuracy, precision, recall, and F1 score

   ## Performance Metrics

Model: **Logistic Regression** (TF-IDF features)

Evaluation was performed on a held-out test sample.

- **Accuracy:** [ADD_YOUR_ACCURACY]
- **Precision / Recall / F1-score:** see classification report below

```text
Accuracy: 0.55
              precision    recall  f1-score   support

           0     0.0000    0.0000    0.0000         9
           1     0.5500    1.0000    0.7097        11

    accuracy                         0.5500        20
   macro avg     0.2750    0.5000    0.3548        20
weighted avg     0.3025    0.5500    0.3903        20

