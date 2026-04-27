# 🎬 Hybrid Movie Recommendation System

📎 **Colab Notebook (Full Project)**  
https://colab.research.google.com/drive/1WnH8d590LNreXpXnvEcJnWX0ea4ENHK5#scrollTo=tpUvZDqrfVvZ

---

## 🧠 Overview

This project builds a **hybrid movie recommendation system** using the MovieLens dataset. The goal is to predict how users would rate movies they have not seen and generate personalized recommendations.

The system combines:

- **Collaborative Filtering (SVD)** → learns hidden user preferences from rating behavior  
- **Machine Learning Models (Ridge Regression)** → uses structured features such as genres, user behavior, and movie popularity  
- **Hybrid Approach** → blends both methods for improved prediction accuracy and recommendation quality  

---

## 🎯 Objective

Build an end-to-end recommendation system that:

- Understands user preferences from sparse rating data  
- Predicts unseen ratings  
- Generates Top-N movie recommendations  
- Combines behavioral and feature-based modeling  

---

## 📊 Dataset

- **Source:** MovieLens Dataset  
- ~790,000 ratings  
- 5,000 users  
- ~24,000 movies  

---

## 🔍 Exploratory Data Analysis (EDA)

Key findings:

- **Rating Bias:** Most ratings fall between 3.0–4.5  
- **Sparsity:** ~99% of user–movie interactions are missing  
- **User Activity:** Highly skewed (few power users)  
- **Movie Popularity:** Long-tail distribution (many movies have very few ratings)  
- **Genre Patterns:** Certain genres (Drama, Crime, War) tend to have higher average ratings  

---

## 🤖 Models Built

### 1. Collaborative Filtering (SVD)

- Learns latent user preferences and movie characteristics  
- Uses matrix factorization to predict unseen ratings  

**Result:**  
RMSE: **0.8525**

---

### 2. Feature-Based Model (Ridge Regression)

- Uses:
  - Genre encoding  
  - User-level features (avg rating, activity)  
  - Movie-level features (popularity, avg rating)  

- Applies regularization to prevent overfitting  

**Result:**  
RMSE: **0.8653**

---

## 🔀 Hybrid Approach

Instead of choosing one model, this project follows a **hybrid recommendation strategy**:

- SVD captures **behavioral patterns**
- Ridge captures **feature-based patterns**

These can be combined to improve predictions:
hybrid_score = 0.7 * svd_prediction + 0.3 * ridge_prediction


---

## 📈 Evaluation

Model performance was evaluated using **RMSE (Root Mean Squared Error)**:

| Model | RMSE |
|------|------|
| SVD | 0.8525 |
| Ridge Regression | 0.8653 |

👉 SVD performs better overall, but Ridge adds valuable signal for hybrid modeling.

---

## 🎯 Key Takeaways

- Collaborative filtering captures deep user behavior patterns  
- Feature-based models provide stability and interpretability  
- Hybrid systems outperform single-method approaches  
- Sparse datasets require models that can generalize effectively  

---

## 🚀 Future Improvements

- Add **Random Forest and XGBoost** models  
- Build full **hybrid recommendation pipeline**  
- Deploy using **Streamlit (Top-N recommendations UI)**  
- Scale pipeline using **Databricks + Spark (medallion architecture)**  
- Convert predictions into a **“recommendation score / odds-style system”**

---

## 🧩 Tech Stack

- Python  
- pandas, NumPy  
- scikit-learn  
- Surprise (SVD)  
- Matplotlib  

---

## 💡 Why This Project Matters

This project mirrors real-world recommendation systems used by:

- Netflix  
- Spotify  
- Amazon  

It demonstrates:

- End-to-end data science workflow  
- Model comparison and evaluation  
- Hybrid system design  
- Product-level thinking  

---

## 👤 Author

Ethan Terzic, Hanna Kovacevic, Emma Kovacevic
