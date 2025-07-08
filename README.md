# Customer Segmentation Using K-Means Clustering
 
## Project Overview
This project focuses on segmenting wholesale customers based on their **annual spending habits** using **K-Means Clustering**. The goal is to identify distinct customer groups to enable **data-driven marketing**, **inventory planning**, and **personalized business strategies**.

The project includes:
- A complete Python analysis using `pandas`, `matplotlib`, `seaborn`, and `scikit-learn`
- A professional PowerPoint presentation summarizing EDA, methodology, modeling, insights, and business recommendations

---

## Dataset Summary

**Source**: UCI Machine Learning Repository  
**Dataset**: Wholesale Customers Data  
**Records**: 440  
**Variables**:

| Feature            | Description                                       | Data Type |
|--------------------|---------------------------------------------------|-----------|
| Channel            | Customer Channel (1=Horeca, 2=Retail)             | Integer   |
| Region             | Geographic Region (1=Lisbon, 2=Oporto, 3=Other)   | Integer   |
| Fresh              | Annual spending on fresh products                 | Integer   |
| Milk               | Annual spending on milk products                  | Integer   |
| Grocery            | Annual spending on grocery items                  | Integer   |
| Frozen             | Annual spending on frozen items                   | Integer   |
| Detergents_Paper   | Annual spending on cleaning supplies              | Integer   |
| Delicassen         | Annual spending on delicatessen products          | Integer   |

---

##  Methodology

### Techniques Used:
- **K-Means Clustering**: To group customers based on similar purchasing patterns
- **StandardScaler**: To normalize features for fair distance measurement
- **Elbow Method & Silhouette Score**: To determine optimal cluster count
- **PCA**: Used for 2D cluster visualization

### No Train-Test Split
- Since clustering is unsupervised, the entire dataset was used for model training.

---

## Exploratory Data Analysis (EDA)

- Distribution plots of each product category
- Correlation heatmap revealed strong co-purchase behavior:
  - Grocery ↔ Detergents_Paper (0.92)
  - Milk ↔ Grocery (0.73)
- Boxplots with and without outliers
- Spending patterns analyzed across **Channel** and **Region**
- Outlier and skew detection

---

## Cluster Evaluation

### Elbow Method:
- Inertia decreases with more clusters, with a **notable bend at K=4**
- K=4 chosen as the **optimal trade-off** between simplicity and granularity

### Silhouette Score:
- Highest score at **K=2 (~0.35)** → best statistical separation
- **K=4 (~0.30)** still acceptable for **finer business segmentation**

---

## Cluster Profiles

###  **K=2 Model** (High-level segmentation)

| Cluster | Spending Focus                  | Likely Customers         |
|---------|----------------------------------|---------------------------|
| 0       | High Fresh & Frozen              | Horeca (restaurants, etc.)|
| 1       | High Grocery, Milk, Detergents   | Retailers (supermarkets) |

###  **K=4 Model** (Detailed segmentation)

| Cluster | Spending Focus                               | Likely Customers             |
|---------|------------------------------------------------|-------------------------------|
| 0       | High Fresh & Frozen, low Detergents_Paper     | Restaurants / Horeca         |
| 1       | High Milk, Grocery, Detergents_Paper          | Large Retailers / Supermarkets|
| 2       | Low spending across all categories            | Infrequent buyers / Small biz |
| 3       | Balanced spending across categories           | Cafes / Local stores          |

---

## Business Recommendations

### By Cluster
- **Cluster 0 (Horeca)**: Fresh + Frozen bundle promos, seasonal offers
- **Cluster 1 (Retail)**: Volume discounts, subscription-based delivery
- **Cluster 2 (Low Spenders)**: Reactivation campaigns (limited-time offers)
- **Cluster 3 (Balanced buyers)**: Loyalty programs, trial campaigns

### By Region
- **Region 3 (Other)**: Highest spenders → prioritize with bulk deals
- **Region 1 & 2 (Lisbon & Oporto)**: Moderate spenders → upsell niche products

---

## Deliverables

-  **Jupyter Notebook**: Fully documented Python code and analysis
-  **PowerPoint Presentation**: 20+ slides with:
  - EDA visuals (10+ charts)
  - Modeling & Evaluation
  - Cluster Profiles
  - Targeted Strategies
  - Recommendations

---

## Dependencies

```txt
pandas
matplotlib
seaborn
numpy
