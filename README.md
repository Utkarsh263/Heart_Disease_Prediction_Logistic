# ❤️ Heart Disease Prediction using Logistic Regression (Recall Optimized)

## 📌 Overview
Heart disease prediction is a high-risk medical classification problem where **missing a patient (False Negative)** can be life-threatening.  
This project focuses on building a **Logistic Regression model optimized for maximum Recall**, ensuring that most heart disease cases are correctly detected.

---

## 🧠 Problem Statement
Given clinical and demographic patient data, predict whether a patient has heart disease.

Target variable:
- 1 → Heart disease present
- 0 → No heart disease

The main objective is **high Recall**, not just high Accuracy.

---

## 🚨 Why Recall is the Priority
In medical diagnosis:
- False Negative (FN) = patient has disease but model predicts healthy ❌
- False Positives (FP) are acceptable compared to FN

Recall formula:

Recall = TP / (TP + FN)

Higher Recall ⇒ fewer missed patients ❤️

---

## ❌ Why Basic Logistic Regression is Not Enough
A basic Logistic Regression model:
- Optimizes **log loss**, not medical risk
- Assumes balanced classes
- Can overfit training data
- Depends heavily on a single train-test split

This may give good accuracy but **poor Recall**, which is unsafe in healthcare.

---

## 📉 Logistic Regression Basics

### Sigmoid Function
The model predicts probability using:

p = 1 / (1 + e^(-z))

where:

z = w0 + w1x1 + w2x2 + ... + wnxn

---

### Log Loss (Binary Cross-Entropy)
Basic Logistic Regression minimizes:

Log Loss = 
- [ y · log(p) + (1 − y) · log(1 − p) ]

This loss treats all errors equally ❌  
Medical problems do not.

---

## 🛡️ Why Regularization is Needed
Large weights cause overfitting.  
To prevent this, **L2 Regularization** is used.

L2 penalty:

L2 = w1² + w2² + ... + wn²

---

### Final Loss Function
Regularized loss becomes:

Total Loss = Log Loss + (1 / C) × L2

Where:
- C = inverse regularization strength
- Small C → strong regularization
- Large C → weak regularization

This improves generalization ✅

---

## ⚖️ Handling Class Imbalance
Heart disease datasets usually have **fewer positive cases**.

To fix this, class weights are applied:

Class Weight = Total Samples / (2 × Samples in Class)

Effect:
- Minority class (heart disease) gets higher importance
- False Negatives are penalized more
- Recall improves significantly 💪

---

## 🔁 Why Cross-Validation is Required
Instead of relying on a single split, k-Fold Cross-Validation is used.

If dataset size = N and k = 5:

Fold size = N / 5

Each fold:
- Trains on 4 folds
- Validates on 1 fold

Benefits:
- Stable performance estimation
- Reliable Recall score
- Better generalization 🧪

---

## 🎯 Hyperparameter Tuning (Recall-Focused)
There is no universal best value for C.

Therefore:
- Multiple values of C are tested
- Performance is evaluated using **Recall**
- Best parameter is chosen using Cross-Validation

This ensures Recall is **consistently high**, not accidental.

---

## 📊 Evaluation Metrics

### Confusion Matrix

|              | Predicted 0 | Predicted 1 |
|-------------|------------|------------|
| Actual 0    | TN         | FP         |
| Actual 1    | FN ❌      | TP ✅      |

---

### Metric Formulas

Accuracy = (TP + TN) / (TP + TN + FP + FN)

Precision = TP / (TP + FP)

Recall = TP / (TP + FN) ⭐

Primary goal → **minimize FN**

---

## ✅ Key Outcome
By combining:
- Regularization
- Class weight balancing
- Feature scaling
- Cross-validation
- Recall-based tuning

The model becomes **safe, reliable, and suitable for medical diagnosis** 🏥

---

## 🧾 Conclusion
This project demonstrates why naive machine learning models are insufficient for healthcare applications. By prioritizing Recall and reducing False Negatives, the model aligns with real-world medical decision-making and patient safety.

---

## 👨‍💻 Author
**Utkarsh Kohli**
