# Customer Satisfaction Analysis

This project aims to analyze customer satisfaction based on survey data using multivariate analysis techniques. Through clustering, Factor Analysis, and Linear Discriminant Analysis (LDA), we extract key insights into the underlying factors driving customer satisfaction and segment customers into meaningful groups.

---

## 📁 Project Structure

- `BASE MODELO DE SATISFACCIÓN - GRUPO 2.sav`: Raw survey data in SPSS format.
- `Client_Satisfaction.ipynb`: Jupyter notebook containing the full analysis pipeline.
- `README.md`: This documentation file.

---

## ⚙️ Setup Instructions

### Requirements

The project primarily runs in **R**, using either RStudio or a Jupyter Notebook with an R kernel.

### Required Libraries

Install the following packages to run the analysis:

```r
install.packages(c("dplyr", "ggplot2", "factoextra", "cluster", "stats", 
                   "tidyverse", "haven", "ggfortify"))
```

---
## 📁 Dataset Overview

- **Total responses:** 4,231
- **Number of observed variables:** 17
- **Variables include:**
  - Store Location
  - Counter Efficiency
  - Staff Engagement
  - Friendliness
  - Product & Service Offering
  - Product Knowledge
  - Information Clarity
  - Waiting Time
  - Service Time
  - Process Simplicity
  - Flexibility
  - Promotional Activities
  - Organization
  - Cleanliness
  - Staff Appearance
  - Facility Infrastructure
  - Comfort
  - Staff Identification	
  - Overall Satisfaction	

---
## 🔍 Project Description

This analysis focuses on evaluating various satisfaction metrics and identifying groups of customers with similar satisfaction levels. To achieve this, we applied:

- **Clustering**: To segment customers into homogeneous groups based on their responses.
- **Exploratory Factor Analysis (EFA)** to uncover the latent structure of satisfaction dimensions.
- **LDA (Linear Discriminant Analysis)**: To visualize and interpret the separation between clusters and assess classification performance.

---

## 🎯 Objectives

1. Discover patterns in customer satisfaction data.
2. Segment customers based on their satisfaction profiles using clustering techniques.
3. Apply PCA to understand the major sources of variation.
4. Use LDA to evaluate the quality of clustering and visualize class separation.

---

## 📊 Key Findings

### 🔍 Factor Loadings

| Variable                 | Factor 1 | Factor 2 |
|--------------------------|---------:|---------:|
| Store Location           |  0.7815  |  0.2690  |
| Counter Efficiency       |  0.8266  |  0.2648  |
| Counter Staff Engagement |  0.8369  |  0.2778  |
| Friendliness             |  0.8088  |  0.2874  |
| Product Knowledge        |  0.8053  |  0.2903  |
| Information Clarity      |  0.8264  |  0.2889  |
| Waiting Time             |  0.7089  |  0.2245  |
| Service Time             |  0.8099  |  0.2583  |
| Process Simplicity       |  0.8529  |  0.2779  |
| Flexibility              |  0.8436  |  0.2732  |
| Promotional Activities   |  0.2914  |  0.6710  |
| Organization             |  0.2803  |  0.8155  |
| Cleanliness              |  0.2858  |  0.8237  |
| Staff Appearance         |  0.3821  |  0.7342  |
| Facility Infrastructure  |  0.2532  |  0.8109  |
| Comfort                  |  0.2514  |  0.7918  |

### ✅ Factor Interpretation

- **Factor 1 – Service Efficiency**  
  High loadings on variables related to staff behavior, clarity, speed, and flexibility.

- **Factor 2 – Environment & Infrastructure**  
  High loadings on physical environment, cleanliness, organization, and comfort.

### 📈 Factor Scores

Each respondent received a score for both extracted factors. These scores can be used for clustering, segmentation, or dashboarding.

Example of the first few rows:

| ID | Factor1 | Factor2 |
|----|--------:|--------:|
| 1  | -1.03   |  1.24   |
| 2  |  0.70   |  0.76   |
| 3  |  0.68   |  0.84   |
| 4  |  0.69   |  0.69   |
| 5  |  0.37   |  0.93   |


### Clustering

- Three main customer segments were identified.
- LDA visualization revealed that **Cluster 3** was well-separated, while **Clusters 1 and 2** showed significant overlap.
- Classification error rates per cluster:
  - **Cluster 1**: 17.77% misclassification rate
  - **Cluster 2**: 20.22% misclassification rate
  - **Cluster 3**: 0.04% misclassification rate (very well defined)

  ### 🔍 ANOVA Summary Table

| Source      | Df   | Sum Sq | Mean Sq | F value | Pr(>F)    |
|-------------|------|--------|---------|---------|-----------|
| Cluster     | 2    | 1615   | 807.3   | 1305    | < 2e-16 *** |
| Residuals   | 4228 | 2615   | 0.6     |         |           |


### ✅ Interpretation

- The **cluster variable is highly significant** in explaining differences in overall customer satisfaction (**p < 2e-16**).
- The **F-statistic (1305)** is extremely high, indicating that the **between-group variance** is much larger than the **within-group variance**.
- This confirms that the clusters **represent truly distinct segments** with different satisfaction profiles.

## LDA Classification Performance

### Confusion Matrix

| Predict \ Real |   1  |  2  |  3   |
|---------------|-------|-----|-------|
| **1**         | 935   | 22  | 1     |
| **2**         | 0     | 288 | 0     |
| **3**         | 202   | 51  | 2732  |


---

### Error Rate

- The overall classification error rate is **6.52%**.
- This means that the LDA model correctly classified **93.48%** of the cases.
- A relatively low error rate indicates good predictive performance and clear separation between clusters.

---

## ✅ Conclusion

The customer satisfaction analysis successfully uncovered distinct patterns in survey responses using multivariate techniques. Two key latent factors were identified:

- **Service Efficiency**
- **Environment & Infrastructure**

These factors summarize the underlying drivers of customer satisfaction and enabled meaningful customer segmentation through clustering. The application of **LDA** not only confirmed the effectiveness of these clusters but also demonstrated strong predictive power, with a low overall error rate of **6.52%**.

Key takeaways:

- The segmentation revealed **three well-defined customer groups**, with Cluster 3 being the most distinct.
- **ANOVA results** confirmed that differences in satisfaction across clusters are statistically significant.
- The model provides a robust foundation for targeted marketing strategies, service improvements, and decision-making based on customer feedback.

This multivariate approach offers valuable insights for enhancing customer experience and aligning services with client expectations.
