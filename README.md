# 🎬 Hybrid Movie Recommendation System

📎 **Colab Notebook (Full Project)**
https://colab.research.google.com/drive/1WnH8d590LNreXpXnvEcJnWX0ea4ENHK5#scrollTo=tpUvZDqrfVvZ

---

## 🧠 Overview

This project builds a **hybrid movie recommendation system** using the MovieLens dataset. The goal is to predict how users would rate unseen movies and generate personalized recommendations.

The system combines:

* **Collaborative Filtering (SVD)** → learns latent user preferences from rating behavior
* **Machine Learning Models (XGBoost, Ridge)** → capture structured relationships using genres, popularity, and user behavior
* **Hybrid Ranking System** → blends behavioral and feature-based predictions with additional ranking constraints

---

## 🎯 Objective

Build an end-to-end recommendation system that:

* Learns user preferences from highly sparse data
* Predicts unseen ratings with strong generalization
* Generates Top-N personalized recommendations
* Combines collaborative filtering and feature-based modeling
* Applies ranking logic to improve real-world recommendation quality

---

## 📊 Dataset

* **Source:** MovieLens Dataset
* ~790,000 ratings
* 5,000 users
* ~24,000 movies

---

## 🔍 Exploratory Data Analysis (EDA)

Key findings:

* **Rating Bias:** Most ratings fall between 3.0–4.5
* **Sparsity:** ~99% of user–movie interactions are missing
* **User Activity:** Highly skewed (few power users dominate ratings)
* **Movie Popularity:** Long-tail distribution (many movies have very few ratings)
* **Genre Patterns:** Certain genres (Drama, Crime, War) trend higher in ratings

---

## 🤖 Models Built

### 1. Collaborative Filtering (SVD)

* Matrix factorization using the Surprise library
* Learns latent user and item embeddings

**Result:**
RMSE: **~0.63**

---

### 2. Feature-Based Models

* **Ridge Regression**
* **Random Forest**
* **XGBoost (best ML model)**

Features include:

* Genre encoding
* User-level aggregates (avg rating, activity)
* Movie-level aggregates (popularity, avg rating)

**Best ML Result (XGBoost):**
RMSE: **~0.85**

---

## 🔀 Hybrid Model

The final system combines SVD and XGBoost:

```python
hybrid_score = w1 * svd_prediction + w2 * xgb_prediction
```

Initial optimization favored SVD heavily, but hybrid scoring was retained to:

* Improve cold-start handling
* Incorporate feature-based signals
* Enable more flexible ranking

---

## 🧠 Recommendation System Design

Beyond prediction, a full **ranking system** was built to improve recommendation quality:

* ✅ **Hybrid scoring (SVD + XGBoost)**
* ✅ **Genre preference integration (soft + constrained)**
* ✅ **Popularity filtering (300+ ratings)**
* ✅ **Franchise diversity constraint** (prevents repetition)
* ✅ **Interactive user input (rate/skip system)**

This transforms the model from a predictor into a **product-style recommender system**.

---

## 📈 Evaluation

| Model   | RMSE  |
| ------- | ----- |
| SVD     | ~0.63 |
| XGBoost | ~0.85 |
| Hybrid  | ~0.68 |

**Key Insight:**
SVD performs best on known users, while hybrid modeling improves flexibility and system design.

---

## 🎯 Key Takeaways

* Collaborative filtering captures deep behavioral patterns
* Feature-based models add stability and interpretability
* Hybrid systems enable real-world recommendation flexibility
* Ranking logic is just as important as prediction accuracy
* Sparse datasets require careful generalization strategies

---

## 🚀 Next Steps

* Refactor and clean code for readability and modular design
* Convert the notebook into an interactive **Streamlit application**
* Rebuild the pipeline in **Databricks using Spark (medallion architecture)**
* Simulate a full production system with scalable data pipelines
* Extend the project into a **PrizePicks-style prediction app** (portfolio concept)

---

## 🧩 Tech Stack

* Python
* pandas, NumPy
* scikit-learn
* XGBoost
* Surprise (SVD)
* Matplotlib

---

## 💡 Why This Project Matters

This project mirrors real-world systems used by:

* Netflix
* Spotify
* Amazon

It demonstrates:

* End-to-end data science workflow
* Model comparison and evaluation
* Hybrid system architecture
* Ranking system design
* Product-level thinking

---

## 👤 Author

Ethan Terzic, Hanna Kovacevic, Emma Kovacevic


