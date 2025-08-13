

## **Social Media Addiction Prediction — `social_media_addiction/README.md`**
```markdown
#  Social Media Addiction Prediction (Feedforward Neural Network)

##  Overview
This project predicts a student's **Social Media Addiction Score** (0–10) based on behavioral and demographic data.  
A feedforward neural network is trained to minimize **Mean Absolute Error (MAE)** and delivers **MAE < 1** on test data.

---

##  Dataset
- **Source:** [Social Media Addiction vs Relationships (Kaggle)](https://www.kaggle.com/datasets/adilshamim8/social-media-addiction-vs-relationships?resource=download)
- **Target Variable:** `Addicted_Score` (integer 0–10)

---

## Process
1. **Data Preprocessing**
   - Removed unnecessary columns (`Country`, `Age`).
   - Filtered to top 5 most-used platforms.
   - Encoded categorical variables:
     - Binary mapping for yes/no.
     - Ordinal encoding for education level.
     - One-hot encoding for gender, platform, relationship status.
   - Scaled numerical features with `StandardScaler`.
2. **Model Architecture**
   - Dense(32, ReLU) → Dense(16, ReLU) → Dense(1)  
     *(No activation for regression output)*
   - Optimized with `adam` and `mse` loss.
3. **Training**
   - 100 epochs, batch size = 16.
   - Used validation split for monitoring.
4. **Evaluation**
   - Achieved **MAE < 1** on test data.

---

## Results
- **Test MAE:** < 1
- Model accurately predicted scores within ±1 of actual values for most students.

---

## Interactive Demo
The script includes a CLI game where:
- A random student's stats are shown.
- You guess their addiction score.
- The model’s prediction and both errors (yours vs. model) are displayed.

---

## Technologies
- **Python**
- **TensorFlow / Keras**
- **Scikit-Learn**
- **NumPy, Pandas**
- **Matplotlib**

