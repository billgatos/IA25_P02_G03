# 🏅 Olympic Games Data Mining Project (1896-2016)

**Course:** IA25 | **Group:** G03  

**Dataset:** 120 Years of Olympic History: Athletes and Results

## 📖 Project Overview

This project performs a comprehensive analysis of the Olympic Games dataset, applying Data Science and Machine Learning techniques to extract business value. The project is divided into three main notebooks.

---

## 🛠️ Requirements

```bash
pip install pandas numpy matplotlib seaborn scikit-learn mlxtend

```

---

## 📂 Project Solutions

### 1️⃣ Notebook 1: EDA & Association Rules

**Filename:** `IA25_P02_G03_Solucao_Completa_V3.ipynb`

* **EDA:** Analyzes demographic evolution (using Decade grouping) and physical attributes.
* **Feature Engineering:** Aggregates data by `NOC` and `Year` for medal prediction regression.
* **Association Rules:** Uses the **Apriori Algorithm** to find patterns like `{Gymnastics} -> {Teenager}` using Support, Confidence, and Lift.

### 2️⃣ Notebook 2: Automatic Classification

**Filename:** `IA25_P02_G03_Classificacao.ipynb`

* **Goal:** Predict if an athlete wins a medal (Binary Classification).
* **Pipeline:** Imputation -> Scaling -> OneHotEncoding.
* **Models:** Logistic Regression vs. Random Forest.
* **Result:** **Random Forest** optimized with **GridSearchCV** provided the best F1-Score.

### 3️⃣ Notebook 3: Clustering

**Filename:** `IA25_P02_G03_Clustering.ipynb`

* **Goal:** Identify physical biotypes.
* **Method:** K-Means Clustering ( determined by Elbow Method).
* **Analysis:**
* **Cluster 0:** Average build (Team sports).
* **Cluster 1:** Lightweight/Short (Gymnastics).
* **Cluster 2:** Tall/Heavy (Basketball).
* **Cluster 3:** Heavy/Strong (Wrestling/Judo).



---

**Authors:** Grupo G03
