# Emotion-Aware Music Recommendation from Text

Follow-up study to my final-year project (Harmony Hub), a wellbeing app
that recommends content based on how the user feels. The original report
described the design; this notebook builds and evaluates it.

## What it does
- Classifies text into 6 emotions: sadness, joy, love, anger, fear, surprise
- Compares VADER, Naive Bayes, Linear SVM, Logistic Regression and a BiLSTM
- Maps each emotion to Spotify valence/energy (arousal–valence model) and
  recommends songs in "match my mood" or "uplift me" mode

## Key results (test set, 2,000 sentences)
- Best model: Logistic Regression, macro F1 ≈ 0.84, accuracy ≈ 0.88
- BiLSTM did not outperform the simpler linear models
- Removing stopwords improved all models on this dataset
- Most confused emotions: joy ↔ love, fear → surprise
- VADER (positive vs negative only): 0.798 accuracy

## Data
- Emotion dataset: Saravia et al. (2018), CARER, EMNLP
- Spotify Tracks dataset (81,343 unique tracks)

## Limitations
- Single-label data, while real emotions are often mixed
- Sentences mostly follow an "i feel…" style, unlike real user messages
- The emotion → music mapping is based on theory, not tested with users

## Run it
Open the notebook in Google Colab and click Runtime → Run all.
