

# **Predicting House Prices**

## **Introduction**
This project aims to predict the sale price of houses based on various factors, including property size, location, quality, and condition. Using a dataset with 80 variables and 1459 observations, this analysis applies machine learning models to identify the key determinants of house prices and build predictive models.

### **Dataset**
The dataset consists of:
- **Training Set**: Includes features and sale prices for model training.
- **Test Set**: Contains features for prediction, with sale prices withheld for evaluation.
- **Data Description**: Documentation explaining each column.

---

## **Hypotheses**
The project explores the following hypotheses:
1. **Quality**: Properties with higher overall quality (`OverallQual`) have higher sale prices.
2. **Size**: Larger properties, measured by `GrLivArea` (above-ground living area) and `TotalSF` (total square footage), have higher sale prices.
3. **Neighborhood**: Neighborhood (`Neighborhood`) significantly impacts sale prices due to location desirability.

---

## **Feature Engineering**
A new feature, `TotalSF`, was created by summing:
- `TotalBsmtSF` (basement area),
- `1stFlrSF` (first-floor area),
- `2ndFlrSF` (second-floor area).

This feature captures the overall size of the property and improves the predictive power of the models.

---

## **Methodology**
### **Data Split**
- Training set: 80% of the data.
- Validation set: 20% of the data, ensuring the model generalizes well to unseen data.

### **Exploratory Data Analysis**
- **Sale Price Distribution**:
  - Right-skewed, with most houses sold between $150,000 and $200,000.
  - Outliers include houses priced above $700,000.
- **Feature Correlation**:
  - Strong positive correlations with `OverallQual`, `GrLivArea`, and `TotalSF`.
  - Neighborhood-specific trends in sale prices.

---

## **Model Training and Evaluation**
### **Models Used**
1. **Linear Regression**: A simple baseline model.
2. **Random Forest Regressor**: Combines multiple decision trees for robust predictions.
3. **Gradient Boosting Regressor**: Sequentially builds models to correct previous errors.
4. **XGBoost Regressor**: An advanced boosting algorithm for improved performance.

### **Performance Metrics**
- **Root Mean Squared Error (RMSE)**:
  - Measures the average error in predicting house prices.

| **Model**                | **Cross-Validated RMSE** | **Validation RMSE** |
|--------------------------|--------------------------|----------------------|
| Linear Regression        | N/A                      | 45,370.19           |
| Random Forest Regressor  | 32,298.51               | 33,824.99           |
| Gradient Boosting        | 30,329.68               | 32,613.42           |
| XGBoost Regressor        | 34,118.30               | 34,292.25           |

- **Best Model**: Gradient Boosting Regressor was selected for its lowest RMSE values in both cross-validation and validation sets.

---

## **Key Findings**
1. **Quality**: Strong positive correlation between `OverallQual` and `SalePrice`. Higher quality homes command significantly higher prices.
2. **Size**: `GrLivArea` and `TotalSF` are strongly correlated with `SalePrice`, confirming that larger properties tend to be more expensive.
3. **Neighborhood**: While neighborhood significantly impacts sale prices, the effect varies by location.

---

## **Future Work**
1. Create interaction terms and polynomial features to capture complex relationships.
2. Explore additional advanced models for further performance improvements.
3. Analyze trends in sale prices over time and across demographic data.

---

## **How to Run the Project**
1. **Clone the Repository**:
   ```bash
   git clone https://github.com/adosbuyu/CapstoneTwo
   ```
2. **Install Dependencies**:
   ```bash
   pip install -r requirements.txt
   ```
3. **Run the Analysis**:
   - Jupyter Notebooks are available in the `notebooks/` directory for step-by-step exploration.

---

---

## **Acknowledgments**
- Dataset: Provided as part of a Kaggle competition on house price prediction.
- Libraries: Scikit-learn, Pandas, NumPy, Matplotlib, Seaborn, XGBoost.

---
