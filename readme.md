# Drug Demand Forecasting & Inventory Optimization

## Project Overview
This project focuses on predicting the **Optimal Stock Level** for pharmaceutical drugs using historical demand data and restocking strategies. The goal is to build a reliable regression model that can help in inventory planning and reduce over- or under-stocking.

The complete workflow follows standard machine learning practices, starting from data understanding and preprocessing to model building, tuning, and evaluation.

---

## Dataset Description
The dataset contains the following columns:
- **Drug**: Name of the drug (categorical)
- **Demand_Forecast**: Predicted demand quantity (numerical)
- **Optimal_Stock_Level**: Target variable representing required stock (numerical)
- **Restocking_Strategy**: Frequency of restocking such as Weekly, Monthly, or Quarterly (categorical)

---

## Project Structure
```
Drug_Demand_Forecasting/
│
├── 01_EDA_Preprocessing.ipynb
├── 02_Modeling_Evaluation.ipynb
├── cleaned_data.csv
└── README.md
```

---

## Steps Performed

### 1. Data Loading & Understanding
- Loaded dataset and inspected structure, data types, and basic statistics
- Identified **Optimal_Stock_Level** as the target variable

### 2. Data Cleaning
- Checked for missing values and handled them using median (numerical) and mode (categorical)
- Detected and treated outliers using the IQR method

### 3. Exploratory Data Analysis (EDA)
- Visualized distributions of demand and stock levels
- Analyzed frequency of drugs and restocking strategies
- Studied correlations between numerical variables

### 4. Feature Engineering
- Basic feature engineering was explored
- Target-derived features were avoided in the final model to prevent data leakage

### 5. Encoding & Preprocessing
- Used **Pipeline** and **ColumnTransformer**
- Numerical features were scaled using `StandardScaler`
- Categorical features were encoded using `OneHotEncoder`

---

## Model Building & Evaluation

The following regression models were implemented using pipelines:

- **Linear Regression**
- **Random Forest Regressor**
- **Gradient Boosting Regressor**

Each model was evaluated using:
- Root Mean Squared Error (RMSE)
- 5-fold Cross-Validation RMSE

---

## Hyperparameter Tuning
- GridSearchCV was applied to:
  - Random Forest Regressor
  - Ridge Regression (as a regularized linear model)

The tuned Ridge Regression model provided stable performance with good generalization.

---

## Final Results
- Linear and Ridge Regression showed the best performance
- Very small difference between training and cross-validation error indicated no overfitting
- Ridge Regression was selected as the final model due to its simplicity and robustness

---

## Conclusion
This project demonstrates a clean, pipeline-based machine learning workflow for regression problems. The final model generalizes well and can be effectively used for inventory planning decisions in pharmaceutical supply chains.

---

## Tools & Libraries Used
- Python
- Pandas, NumPy
- Matplotlib, Seaborn
- Scikit-learn

---

## Author
*Project completed as part of a machine learning practice/academic assignment.*