# Product-Delivery-Time-Analysis
Учебный: Supply chain delivery prediction system using Logistic Regression, SVM, and Random Forest with comprehensive data preprocessing
---

## Project Overview

This project tackles the challenge of predicting whether products will be delivered on time in e-commerce supply chains. Using real-world delivery data, we build and compare multiple machine learning models to classify delivery outcomes.

### Business Problem
- **Problem**: Unpredictable delivery times lead to customer dissatisfaction and increased operational costs
- **Solution**: Build ML models to forecast delivery reliability
- **Impact**: Improve customer experience and optimize logistics operations

---

## Dataset Description

The dataset contains **10,999 records** with **12 features** describing delivery characteristics:

| Feature | Description | Type |
|---------|-------------|------|
| `Warehouse_block` | Warehouse storage division | Categorical |
| `Mode_of_Shipment` | Transportation method | Categorical |
| `Customer_care_calls` | Number of support calls | Numerical |
| `Customer_rating` | Customer satisfaction rating | Numerical |
| `Cost_of_the_Product` | Product cost | Numerical |
| `Prior_purchases` | Previous purchase count | Numerical |
| `Product_importance` | Product priority level | Categorical |
| `Gender` | Customer gender | Categorical |
| `Discount_offered` | Applied discount percentage | Numerical |
| `Weight_in_gms` | Product weight | Numerical |
| `Reached.on.Time_Y.N` | **Target**: Delivery on time | Binary |

---

## Technical Implementation

### Data Preprocessing Pipeline
1. **Missing Values Handling** - 3 strategies tested:
   - Strategy 1: Complete row removal
   - Strategy 2: Mean/mode imputation  
   - Strategy 3: Median/mode imputation + outlier removal **Selected**

2. **Feature Engineering**:
   - One-Hot Encoding for categorical variables
   - Standardization of numerical features
   - Binary feature preservation

3. **Dimensionality Reduction**:
   - L1 Regularization (Lasso)
   - Recursive Feature Elimination (RFE)
   - Decision Tree feature importance

### Models Compared
| Model | Train Accuracy | Test Accuracy | Difference |
|-------|----------------|---------------|------------|
| Logistic Regression | 52.74% | 53.42% | 0.68% |
| SVM | 52.50% | 52.48% | 0.02% |
| Random Forest | 100.00% | 49.17% | 50.83% |

---

## Results & Findings

### Best Performing Model
- **Logistic Regression** achieved **53.42% accuracy** on test data
- Most stable performance with minimal overfitting

### Key Insights
- **Random Forest** showed significant overfitting (50.83% difference)
- **Discount_offered** and **Weight_in_gms** were most important features
- **8 out of 16 features** provided optimal predictive power
- Data quality significantly impacted model performance

### Challenges Addressed
 Missing data (5% random missing values)
 Outlier detection and treatment  
 Categorical variable encoding
 Multicollinearity handling
