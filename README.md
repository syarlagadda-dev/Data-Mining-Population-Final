# Global Healthcare Access Analysis

## Project Overview
This project analyzes the relationship between healthcare access and various health outcomes across different countries worldwide. Using clustering techniques and linear regression, we examine how factors like healthcare infrastructure (access percentage, doctors per capita, hospital beds per capita) relate to health metrics such as mortality rates, disease prevalence, and disease burden (DALYs).

## Research Questions
- How does healthcare access vary across countries globally?
- What are the distinct patterns of healthcare infrastructure development?
- How does healthcare access relate to health outcomes within different access clusters?
- What additional factors (treatment costs, recovery rates) correlate with health outcomes?

## Dataset
**Source:** [Global Health Statistics Dataset](https://www.kaggle.com/datasets/malaiarasugraj/global-health-statistics) (Kaggle)

**Dataset Characteristics:**
- **Size:** Comprehensive country-level health data spanning 2000-2020
- **Key Features:**
  - Healthcare Infrastructure: Access percentage, doctors per 1000, hospital beds per 1000
  - Health Outcomes: Mortality rate, prevalence rate, DALYs (Disability-Adjusted Life Years)
  - Demographics: Age groups, gender, population affected
  - Economic: Treatment costs, per capita income, education index
  - Disease Information: 20+ disease types across multiple categories

**Data Quality:**
- No missing values detected
- Data types optimized (categorical variables converted for efficiency)
- Standardized numerical features for clustering analysis

## Methodology

### 1. Data Preprocessing
- **Type Conversion:** Optimized data types for memory efficiency
  - Converted string categorical variables to pandas `category` dtype
  - Ensured numerical consistency for analysis
- **Feature Scaling:** Standardized healthcare access features using `StandardScaler`
- **No Missing Data:** Dataset required no imputation

### 2. Clustering Analysis
**Objective:** Group countries by healthcare infrastructure patterns

**Process:**
- **Features Used:** Healthcare Access (%), Doctors per 1000, Hospital Beds per 1000
- **Algorithm:** K-Means clustering
- **Optimal Cluster Selection:**
  - Evaluated k=2 through k=10
  - Used Elbow Method (inertia) and Silhouette Scores
  - Selected **k=5** for optimal balance between detail and interpretability
  
**Identified Clusters:**

| Cluster | Name | Healthcare Access | Doctors/1000 | Beds/1000 | Characteristics |
|---------|------|-------------------|--------------|-----------|-----------------|
| 0 | Limited, Moderate Access | 74.1% | 1.52 | 2.78 | Moderate access, limited resources |
| 1 | Bed-Lopsided, High Access | 86.8% | 1.70 | 7.46 | High access via hospitals, lower physician density |
| 2 | Well-Rounded, High Access | 88.5% | 3.92 | 5.07 | Balanced, high-quality systems |
| 3 | Bed-Lopsided, Low Access | 62.0% | 2.82 | 7.83 | High bed capacity, low overall access |
| 4 | Doctor-Lopsided, Low Access | 63.1% | 3.81 | 3.01 | Strong physician workforce, weaker infrastructure |

### 3. Regression Analysis
*(Planned for subsequent analysis)*
- Linear regression within clusters
- Examine healthcare access vs. health outcomes
- Control for cluster-specific characteristics

## Key Findings

### Clustering Insights
1. **Healthcare Access is Multi-Dimensional:** Countries can have similar access levels but vastly different resource distributions (doctors vs. beds)

2. **Infrastructure Imbalances:** Many countries show lopsided development:
   - Some invest heavily in hospitals but lack physicians (Cluster 1, 3)
   - Others have strong physician networks but weaker hospital systems (Cluster 4)

3. **Elite vs. Struggling Systems:** 
   - Cluster 2 represents optimal, balanced healthcare systems
   - Clusters 3 & 4 show how partial development fails to achieve high population-level access

### Model Performance
- **Silhouette Score (k=5):** ~0.35-0.40
  - Indicates reasonably distinct clusters
  - Validates meaningful healthcare access patterns
  
- **Elbow Point:** Observed at k=4-5
  - Minimal inertia improvement beyond 5 clusters
  - Confirms cluster stability

## Impact & Ethical Considerations

### Positive Impacts
- **Policy Guidance:** Identifies specific infrastructure gaps for targeted investment
- **Resource Allocation:** Helps prioritize spending (physicians vs. facilities)
- **Comparative Analysis:** Countries can benchmark against similar clusters

### Potential Negative Impacts
1. **Oversimplification Risk:** 
   - Clustering may mask within-country inequalities
   - Urban-rural disparities not captured in national averages

2. **Resource Competition:**
   - Identification of "low access" clusters could stigmatize countries
   - May affect international aid distribution unfairly

3. **Historical Context Missing:**
   - Analysis doesn't account for recent conflicts, economic crises
   - Could penalize countries with temporary setbacks

4. **Data Sovereignty:**
   - Aggregated health data raises privacy concerns
   - Potential for misuse in geopolitical contexts

### Mitigation Strategies
- Supplement with qualitative, localized studies
- Regular dataset updates to reflect current conditions
- Transparent methodology disclosure
- Collaboration with local health authorities

## Technical Details

### Technologies Used
- **Python 3.13**
- **Libraries:**
  - Data: `pandas`, `numpy`
  - ML: `scikit-learn` (KMeans, StandardScaler, LinearRegression)
  - Visualization: `matplotlib`, `seaborn`





## Learning Outcomes
Throughout this project and course, I've gained:
- **Technical Skills:** Advanced pandas operations, clustering optimization, model evaluation
- **Critical Thinking:** Recognizing when simple metrics hide complex realities
- **Ethical Awareness:** Understanding how data analysis can both help and harm policy decisions
- **Storytelling:** Translating technical findings into actionable insights


