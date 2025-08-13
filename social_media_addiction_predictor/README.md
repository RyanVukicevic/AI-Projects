# Social Media Addiction Prediction (Feedforward Neural Network)

## Overview
Predicts a student’s **Social Media Addiction Score (0–10)** from behavior, demographics, and lifestyle features using a feedforward network with **MAE < 1**.

---

## Dataset
- **Source:** [Social Media Addiction vs. Relationships (Kaggle)](https://www.kaggle.com/datasets/adilshamim8/social-media-addiction-vs-relationships)
- **Target:** `Addicted_Score` (integer 0–10)

---

## Process
1. **Data Preprocessing**
   - Dropped `Country`, `Age`; filtered to top platforms (Instagram, Twitter, TikTok, YouTube, Facebook)
   - Encodings: binary (Yes/No), ordinal (`Academic_Level`), one-hot (gender, platform, relationship)
   - Converted all features to numeric; **StandardScaler** on numerics
2. **Model Architecture**
   - Dense(32, ReLU) → Dense(16, ReLU) → Dense(1)
   - Optimizer: `adam` · Loss: `mse` · Metric: `mae`
3. **Evaluation**
   - 80/20 train–test split with validation monitoring
   - **MAE < 1** on test data

---

## Results
- **Low MAE** indicates accurate score predictions
- Strong associations with higher scores:
  - Greater daily usage hours
  - Lower sleep duration
  - Academic performance concerns

---

## Interactive Demo
CLI game:
- Shows anonymized user stats
- You guess the addiction score
- Compares your error vs. the model’s error

---

## Technologies
**Python**, **TensorFlow/Keras**, **Scikit-Learn**, **NumPy**, **Pandas**, **Matplotlib**
