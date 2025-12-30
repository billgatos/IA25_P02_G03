# 🏅 Olympic Games Data Mining Project (1896-2016)

**Course:** IA25 | **Group:** G03  
Alunos:
  * Roberto Rodrigues -- a5278
  * Gonçalo Oliveira  -- a18559
  * Pedro Duarte      -- a27990
  * Rodrigo Moura     -- a27995
  * Mário Júnior      -- a27989

**Dataset:** 
[Kaggle  - 120 Years of Olympic History: Athletes and Results](https://www.kaggle.com/datasets/heesoo37/120-years-of-olympic-history-athletes-and-results?resource=download)

## 📖 Project Overview

This project performs a comprehensive analysis of the Olympic Games dataset, applying Data Science and Machine Learning techniques to extract business value. The project is divided into three main notebooks.

---

## 🛠️ Requirements

```bash
pip install pandas numpy matplotlib seaborn scikit-learn mlxtend

```

---

## 📂 Project Solutions

### 1️⃣ Notebook EDA: EDA 

**Filename:** `IA25_P02_G03_EDA.ipynb`

* **EDA:** Analyzes demographic evolution (using Decade grouping) and physical attributes.
* **Feature Engineering:** Aggregates data by `NOC` and `Year` for medal prediction regression.


### 2️⃣ Notebook 1: Automatic Classification

**Filename:** `IA25_P02_G03_Classificacao_NBK1.ipynb`

* **Goal:** Predict if an athlete wins a medal (Binary Classification).
* **Pipeline:** Imputation -> Scaling -> OneHotEncoding.
* **Models:** Logistic Regression vs. Random Forest.
* **Result:** **Random Forest** optimized with **GridSearchCV** provided the best F1-Score.

### 3️⃣ Notebook 2: Clustering

**Filename:** `IA25_P02_G03_Clustering_NBK2.ipynb`

* **Goal:** Identify physical biotypes.
* **Method:** K-Means Clustering ( determined by Elbow Method).
* **Analysis:**
* **Cluster 0:** Average build (Team sports).
* **Cluster 1:** Lightweight/Short (Gymnastics).
* **Cluster 2:** Tall/Heavy (Basketball).
* **Cluster 3:** Heavy/Strong (Wrestling/Judo).

### 4️⃣ Notebook 3: Association Rules

**Filename:** `IA25_P02_G03_Association_Nbk3.ipynb`

* **Business Goal:** Identify profiles of success (e.g., "What attributes frequently appear together in Gold medalists?").
* **Methodology:**
* **Association Rules:** Uses the **Apriori Algorithm** to find patterns like `{Gymnastics} -> {Teenager}` using Support, Confidence, and Lift.
* **Algorithm:** Apriori (using `mlxtend`).
* **Preparation:** Filtered only medalists, discretized `Age` into bins (Teen, Adult, Veteran), and applied One-Hot Encoding.
* **Results:** generated rules based on **Lift** and **Confidence** to find links between Sport, Age, and Gender.


---

**Authors:** Grupo G03
