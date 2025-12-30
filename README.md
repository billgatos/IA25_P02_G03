# Olympic Games Data Mining Project (1896-2016)

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

This project performs a comprehensive analysis of the Olympic Games dataset, applying Data Science and Machine Learning techniques to extract business value. The project is divided into four main notebooks.

---

## ⚙️ Requirements

To run these notebooks, the following Python libraries are required:

* `pandas` & `numpy` (Data Manipulation)
* `matplotlib` & `seaborn` (Visualization)
* `scikit-learn` (Classification & Clustering)
* `mlxtend` (Association Rules)


---

## Project Solutions

### Notebook EDA: EDA 

**Filename:** `IA25_P02_G03_EDA.ipynb`

* **EDA:** Analyzes demographic evolution (using Decade grouping) and physical attributes.
* **Feature Engineering:** Aggregates data by `NOC` and `Year` for medal prediction regression.
Before diving into complex modeling, a comprehensive analysis of the dataset was performed to understand the historical evolution of the Olympic Games (1896-2016).

**Key Analyses:**
* **Data Quality Check:** Identification of missing values (especially in Age, Height, and Weight) and data consistency.
* **Temporal Analysis:** Creation of a `Decade` feature to visualize the exponential growth of athletes and the inclusion of different sports over time, filtering out noise from individual years.
* **Demographics:** Distribution analysis of physical attributes (Age, Height, Weight) to establish a baseline for "typical" athletes versus outliers.
* **Correlations:** Heatmaps used to identify strong relationships between physical traits (e.g., Height vs. Weight) and their potential influence on winning medals.

### Notebook 1: Automatic Classification

**Filename:** `IA25_P02_G03_Classificacao_NBK1.ipynb`

* **Goal:** Predict if an athlete wins a medal (Binary Classification).
* **Pipeline:** Imputation -> Scaling -> OneHotEncoding.
* **Models:** Logistic Regression vs. Random Forest.
* **Result:** **Random Forest** optimized with **GridSearchCV** provided the best F1-Score.

**Objective:** Predict whether an athlete will win a medal (Gold, Silver, or Bronze) based on their biometric and demographic profile.

**Methodology:**
* **Target Variable:** Created a binary target `Is_Medalist` (1 = Won a medal, 0 = Did not win).
* **Data Preparation:**
    * **Imputation:** Filled missing numeric values with the mean.
    * **Scaling:** Applied Standard Scaling to normalize Age, Height, and Weight.
    * **Encoding:** Converted categorical variables (`Sex`, `Season`) into numerical format using One-Hot Encoding.
* **Algorithms:**
    * **Logistic Regression:** Used as a baseline model to establish a performance benchmark.
    * **Random Forest:** Implemented to capture non-linear relationships between physique and success.
* **Optimization:** Hyperparameter tuning (GridSearchCV) was applied to the Random Forest model to optimize the number of trees and maximum depth.

### Notebook 2: Clustering

**Filename:** `IA25_P02_G03_Clustering_NBK2.ipynb`

* **Goal:** Identify physical biotypes.
* **Method:** K-Means Clustering ( determined by Elbow Method).
* **Analysis:**
* **Cluster 0:** Average build (Team sports).
* **Cluster 1:** Lightweight/Short (Gymnastics).
* **Cluster 2:** Tall/Heavy (Basketball).
* **Cluster 3:** Heavy/Strong (Wrestling/Judo).

**Objective:** Identify natural groupings (biotypes) of athletes based solely on physical attributes, without prior knowledge of their sport.

**Methodology:**
* **Feature Selection:** Focused exclusively on `Age`, `Height`, and `Weight`.
* **Preprocessing:** Strict removal of missing values and application of Standardization to ensure all features contribute equally to distance calculations.
* **Algorithm:** **K-Means Clustering**.
* **Optimization:** Utilized the **Elbow Method** to determine the optimal number of clusters ($K=4$).
* **Cluster Interpretation:**
    * **Cluster 0:** Average build (Team sports).
    * **Cluster 1:** Lightweight/Short (Gymnastics, Diving).
    * **Cluster 2:** Tall/Heavy (Basketball, Volleyball).
    * **Cluster 3:** Heavy/Strong (Wrestling, Judo, Throwing events).

### Notebook 3: Association Rules

**Filename:** `IA25_P02_G03_Association_Nbk3.ipynb`

* **Business Goal:** Identify profiles of success (e.g., "What attributes frequently appear together in Gold medalists?").
* **Methodology:**
* **Association Rules:** Uses the **Apriori Algorithm** to find patterns like `{Gymnastics} -> {Teenager}` using Support, Confidence, and Lift.
* **Algorithm:** Apriori (using `mlxtend`).
* **Preparation:** Filtered only medalists, discretized `Age` into bins (Teen, Adult, Veteran), and applied One-Hot Encoding.
* **Results:** generated rules based on **Lift** and **Confidence** to find links between Sport, Age, and Gender.

**Objective:** Discover hidden patterns and frequent associations among successful athletes (Medalists).

**Methodology:**
* **Scope:** The analysis was restricted to the subset of athletes who won medals.
* **Data Transformation:**
    * **Discretization:** Converted the continuous variable `Age` into categorical bins (`Teen`, `Young Adult`, `Adult`, `Veteran`).
    * **Transaction Creation:** Formatted data into a "basket" of attributes including Sport, Sex, Season, and Age Group.
* **Algorithm:** **Apriori Algorithm**.
* **Evaluation Metrics:**
    * **Support:** The frequency of the rule in the dataset.
    * **Confidence:** The reliability of the rule.
    * **Lift:** The strength of the association (Lift > 1 indicates a useful rule).
* **Insight Example:** Identifying strong links between specific sports and age groups (e.g., *Gymnastics* $\rightarrow$ *Teenagers*).


---

**Authors:** Grupo G03
