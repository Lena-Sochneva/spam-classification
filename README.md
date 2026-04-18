# Spam Classification (SMS)

## 📌 Project Overview
This project focuses on detecting spam messages using classical machine learning and NLP techniques.

The goal is to build a model that can effectively distinguish between spam and legitimate (ham) messages, while analyzing trade-offs between precision and recall.

---

## 📊 Dataset
- SMS Spam Collection Dataset
- Total messages: 5572
- Spam: ~13.4%
- Imbalanced dataset

---

## ⚙️ Approach

### 1. Data Analysis (EDA)
- Checked class imbalance
- Analyzed message length distribution
- Extracted most frequent words in spam

### 2. Feature Engineering
- TF-IDF vectorization
- Stop-word removal
- Added n-grams (unigrams + bigrams)

### 3. Models
- Logistic Regression (baseline)
- Logistic Regression with class_weight="balanced"

---

## 📈 Evaluation Metrics
Due to class imbalance, accuracy is not reliable.

Used:
- Precision
- Recall
- F1-score
- ROC-AUC

---

## 📊 Results

### Baseline Model
- Precision: 1.00
- Recall: 0.80
- F1: 0.89

### Final Model (balanced + n-grams)
- Precision: 0.926
- Recall: 0.919
- F1: 0.923
- ROC-AUC: 0.985

---

## ⚖️ Threshold Tuning

Model performance depends on decision threshold:

| Threshold | Precision | Recall |
|----------|----------|--------|
| 0.3      | 0.72     | 0.95   |
| 0.5      | 0.93     | 0.92   |
| 0.7      | 0.99     | 0.87   |
| 0.9      | 1.00     | 0.62   |

Example:
- For banking systems → higher precision preferred (threshold ≈ 0.7)

---

## 📌 Key Insights
- Class imbalance significantly affects model behavior
- TF-IDF works well for text classification
- Adding n-grams improves context understanding
- Threshold tuning is critical for real-world applications

---

## 🛠 Tech Stack
- Python
- pandas, numpy
- scikit-learn
- matplotlib

---

## 🚀 Future Improvements
- Try LinearSVC
- Use transformer models (e.g. Hugging Face)
- Deploy as API or simple web app