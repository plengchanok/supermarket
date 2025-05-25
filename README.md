# Customer Personality Analysis

## 📌 Project Overview

This project aims to help supermarket retailers enhance marketing strategy, increase revenue, and improve customer retention by:
- Performing **customer segmentation** using clustering techniques.
- Identifying **high-value customer groups**.
- Discovering **product association rules** for cross-sell and upsell opportunities.

The project leverages unsupervised learning (K-Means) and association rule mining (Apriori) on a real-world marketing dataset.

---

## 📊 Dataset

- **Source**: [Kaggle - Customer Personality Analysis](https://www.kaggle.com/datasets/imakash3011/customer-personality-analysis)
- **Size**: 2,240 rows × 29 features
- **Features**: Demographics (age, income, marital status, education), shopping behavior (spending, channel), response to campaigns, and product purchases.

### Data Preprocessing
- Imputed 24 missing income values with median.
- Capped outliers: `Age < 90`, `Income < 600K`.
- Engineered features: `Total Spending`, `Age`, `Family Size`, `Recency`, interaction terms.
- Grouped categorical variables (e.g., Education → 3 levels).
- One-hot encoding for categorical features, standard scaling for numerical features.

---

## 🧠 Methods

### Dimensionality Reduction
- Applied **Principal Component Analysis (PCA)** to retain 80% variance (7 components selected).

### Clustering
- Used **Elbow Method** and **Silhouette Score** to choose **4 clusters**.
- Applied **K-Means** clustering to segment customers by behavior and spending.

### Market Basket Analysis
- Used **Apriori Algorithm** to identify frequently bought together items by customer segment.

---

## 🔍 Cluster Profiles

| Cluster | Description                        | Avg Spend | Key Traits                                     |
|---------|------------------------------------|-----------|------------------------------------------------|
| 0       | Low-Spending, Older Families       | $170      | Value-conscious, moderate store use            |
| 1       | High-Income, Digitally Active      | $875      | Prefer web/catalog, deal-responsive            |
| 2       | Very High-Income, High-Spending    | $1,415    | Loyal, affluent, least responsive to deals     |
| 3       | Young, Low-Income, Low-Spending    | $97       | Browsers, high web activity, low conversion    |

---

## 💡 Key Findings

### Apriori Insights (Product Associations)
- **Cluster 0**: Wine + Meats, Fruits + Meats  
- **Cluster 1**: High individual value products (e.g., Meat, Gold, Wine)  
- **Cluster 2**: Meat + Fish + Sweets bundles  
- **Cluster 3**: Sweets → Meat/Fruits combos (potential in group marketing)

### Cross-Segment Rules
- Customers who buy **Sweets** often buy **Fish and Fruits**.
- Customers who buy **Meat** tend to buy **Wine**.
- Many purchase relationships show strong lift and confidence values.

---

## 📈 Recommendations

### 1. Segment-Based Targeted Marketing
- VIP perks for high-spending groups.
- Social and influencer campaigns for younger, low-spending groups.

### 2. Data-Driven Product Bundling
- Promote “Buy A, Get B” offers using Apriori insights.

### 3. Smarter Product Placement
- Group commonly bought items together in-store and online (UX improvement).

### 4. Product Development & Inventory Strategy
- Create segment-specific SKUs.
- Forecast demand by segment to optimize inventory and reduce waste.

---

## 👩‍💻 Authors
- Ian Hash  
- Pleng Witayaweerasak  

---

## 🚀 Tools & Libraries
- Python, Pandas, Scikit-learn, mlxtend (for Apriori), Matplotlib/Seaborn
