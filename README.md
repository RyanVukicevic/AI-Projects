# AI & Deep Learning Projects

This repository contains end-to-end AI and machine learning projects that apply deep learning, natural language processing, and regression techniques to real-world datasets. Each project includes full data preprocessing, model training, evaluation, and an **interactive CLI demonstration**.

---

## Projects

### 1. Fake News Detection by Headline (LSTM + Keras/TensorFlow)
**Goal:** Predict whether a news headline is real or fake using only its text.  
**Dataset:** [Fake and Real News Dataset (Kaggle)](https://www.kaggle.com/datasets/clmentbisaillon/fake-and-real-news-dataset?resource=download&select=Fake.csv)  
**Key Features:**
- Text preprocessing with tokenization, padding, and out-of-vocabulary handling
- Embedding + LSTM architecture for sequence learning
- Dropout regularization to reduce overfitting
- Achieved **~99% accuracy** on test set
- Interactive CLI quiz: guess if a headline is real or fake, compare to model’s prediction

[**View Project Code →**](fake_news_classifier/fake_news_classifier.py)  
[**View Detailed README →**](fake_news_classifier/README.md)

---

### 2. Social Media Addiction Prediction (Feedforward Neural Network)
**Goal:** Predict a student’s social media addiction score (0–10) from behavioral and demographic data.  
**Dataset:** [Social Media Addiction vs Relationships (Kaggle)](https://www.kaggle.com/datasets/adilshamim8/social-media-addiction-vs-relationships?resource=download)  
**Key Features:**
- Data cleaning, categorical encoding, and numerical scaling
- Feedforward regression model with ReLU activations
- Achieved **MAE < 1** on test data
- Interactive CLI game: guess the addiction score from user stats and compare to model

[**View Project Code →**](social_media_addiction/social_media_addiction.py)  
[**View Detailed README →**](social_media_addiction/README.md)

---

## Tech Stack
- **Languages:** Python  
- **Frameworks:** TensorFlow, Keras, Scikit-Learn  
- **Data Processing:** Pandas, NumPy, StandardScaler, Tokenizer  
- **Visualization:** Matplotlib, Seaborn
