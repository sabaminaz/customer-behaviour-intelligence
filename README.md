# customer-behaviour-intelligence

![Python](https://img.shields.io/badge/Python-3.9-blue)
![PySpark](https://img.shields.io/badge/PySpark-Big%20Data-orange)
![ML](https://img.shields.io/badge/Machine%20Learning-Enabled-green)
![Status](https://img.shields.io/badge/Project-Completed-success)

---

##  Overview
This project analyzes large-scale user behavior data from a multi-category eCommerce platform to extract actionable insights related to **customer conversion, product segmentation, and sales forecasting**.

The dataset consists of **67.5M+ user events**, including:
- Product views  
- Cart additions  
- Purchases  

###  Project Phases
- **Phase I:** Exploratory Data Analysis using Pandas (sampled data)  
- **Phase II:** Distributed processing & ML using PySpark  

---

##  Dataset
- **Source:** Multi-category eCommerce logs (Oct 2019)  
- **Size:** `67,501,979 events`

### Features
- `event_time`, `event_type`  
- `product_id`, `category_id`, `category_code`  
- `brand`, `price`  
- `user_id`, `user_session`  

---

##  Data Engineering & Cleaning
- Chunk-based ingestion (500K rows/batch) to prevent memory issues  
- Removed invalid records (null IDs, negative prices)  
- Standardized timestamps and schema  
- Optimized categorical features  
- Scaled processing with PySpark  

 **Result:** Clean dataset with ~100% usable records at scale  

---

##  Exploratory Data Analysis (EDA)

### Key Insights
-  Significant funnel drop-off: `views >> cart >> purchase`  
-  Price distribution is right-skewed (low-cost dominance)  
-  Peak activity during mid-day & evening  
-  Category-level conversion differences  
-  High-activity sessions drive major engagement  

---

##  Machine Learning

###  User Conversion Prediction
**Goal:** Predict purchase likelihood per session  

**Models:**
- Logistic Regression  
- Random Forest  
- Gradient Boosted Trees  

| Model | Accuracy | F1 Score |
|------|----------|----------|
| Random Forest | **0.9858** | **0.9770** |
| Logistic Regression | 0.9780 | 0.9792 |
| GBT | 0.9770 | 0.9787 |

 **ROC-AUC ≈ 0.98**

---

###  Product Category Clustering
**Goal:** Segment categories based on user behavior  

- Model: **K-Means (k=5)**  
- **Silhouette Score:** `0.8454`  

 Enables targeted marketing & recommendations  

---

###  Sales Forecasting
**Goal:** Predict daily purchase volume  

| Model | RMSE | MAE |
|------|------|-----|
| Random Forest | **663.74** | **296.58** |
| Linear Regression | 695.41 | 311.49 |

 Random Forest captures nonlinear trends effectively  

---

##  Tech Stack
- **Languages:** Python  
- **Big Data:** PySpark, Spark SQL  
- **Machine Learning:** Spark MLlib, Scikit-learn  
- **Data Processing:** Pandas, NumPy  
- **Visualization:** Matplotlib, Seaborn  
- **Environment:** Jupyter Notebook  

---

##  How to Run

```bash
# Clone the repository
git clone https://github.com/your-username/repo-name.git

# Navigate into the project folder
cd repo-name

# Install dependencies
pip install -r requirements.txt
```

###  Run Notebooks
- **eda.ipynb**
- **phase2_modeling.ipynb**

 Ensure Spark is properly configured for large-scale processing.

---

##  Key Learnings
- Session-level behavioral features strongly predict purchase intent  
- Distributed machine learning is essential for large-scale datasets  
- Ensemble models outperform linear models  
- Category-level aggregation reveals meaningful patterns  

---

##  Future Improvements
- Add SHAP/LIME for explainability  
- Use LSTM/GRU for sequence modeling  
- Incorporate text embeddings for better clustering  
- Deploy as batch/streaming pipelines  

---

##  Highlights
-  Processed **67.5M+ events**  
-  Built scalable **PySpark pipelines**  
-  Achieved **98.6% prediction accuracy**  
-  Strong clustering with **0.84 Silhouette Score**  

---

##  Author
**Saba Minaz Taj** <br>
**Harsha Venkateshwara**
**Sphoorthy Selvaraj**
