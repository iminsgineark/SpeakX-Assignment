## 📈 Predicting Customer Churn in a Telecommunications Company

## 🎯 Objective
The primary objective of this project is to develop a predictive model that can identify customers at risk of churning, enabling the company to take proactive measures to retain them.

## 📊 Data Collection and Preprocessing

### 📁 Dataset
We used the Telco Customer Churn dataset from Kaggle. The dataset includes various customer attributes and a binary target variable indicating whether the customer churned.

### 🔄 Preprocessing Steps

1. **Handling Missing Values:**
   - The `TotalCharges` column had some missing values. We converted the `TotalCharges` column to numeric, forcing errors to NaN, and then dropped rows with missing values.

2. **Encoding Categorical Variables:**
   - We used Label Encoding to convert categorical variables to numeric values for modeling. The `customerID` column was dropped as it is not relevant for prediction.

3. **Feature Scaling:**
   - Numerical features (`tenure`, `MonthlyCharges`, and `TotalCharges`) were standardized using the StandardScaler.

## 🔍 Exploratory Data Analysis (EDA)

### 🔗 Correlation Matrix
We plotted a correlation matrix to understand the relationships between numerical features. This helped in identifying multicollinearity and understanding feature interactions.

### 📊 Churn Distribution
A count plot showed the distribution of churn in the dataset, revealing that the data is imbalanced with more non-churned customers than churned ones.

### 🕒 Tenure vs Churn
A histogram showed the distribution of tenure for churned and non-churned customers, indicating that customers with shorter tenure are more likely to churn.

### 💸 Monthly Charges vs Churn
A histogram showed the distribution of monthly charges for churned and non-churned customers, indicating that higher monthly charges are associated with higher churn.

## 🛠️ Feature Engineering

### 📅 Tenure Groups
We created a new feature `tenure_group` by binning the `tenure` column into several groups: `0-12`, `12-24`, `24-48`, `48-60`, and `60-72` months. This categorical feature was then label encoded.

## 🤖 Model Building

We implemented three machine learning models for churn prediction:

1. **Logistic Regression:**
   - A simple, interpretable model suitable for binary classification problems.

2. **Random Forest:**
   - An ensemble model that reduces overfitting and improves accuracy by averaging multiple decision trees.

3. **Gradient Boosting:**
   - An advanced ensemble technique that builds models sequentially, each new model correcting errors from the previous ones.

## 🧮 Model Evaluation

We evaluated the models using accuracy, precision, recall, and F1-score. Here are the results:

| Model                | Accuracy | Precision | Recall | F1-score |
|----------------------|----------|-----------|--------|----------|
| Logistic Regression  | 0.8073   | 0.6700    | 0.5152 | 0.5827   |
| Random Forest        | 0.7932   | 0.6290    | 0.5182 | 0.5687   |
| Gradient Boosting    | 0.8052   | 0.6465    | 0.5395 | 0.5885   |

Gradient Boosting performed the best overall, with a balanced accuracy, precision, recall, and F1-score.

## ⚠️ Challenges

1. **Handling Missing Values:**
   - The `TotalCharges` column had missing values that needed to be handled appropriately.

2. **Encoding Categorical Variables:**
   - Choosing the right encoding technique was crucial for maintaining model performance.

## 🏁 Conclusion

Gradient Boosting emerged as the best model for predicting customer churn, providing a good balance of accuracy, precision, recall, and F1-score. Further tuning and additional feature engineering could potentially improve the model performance even more.

## 🚀 How to Run the Code

1. Clone the repository from GitHub.
2. Install the required libraries.
3. Run the provided Jupyter Notebook to preprocess the data, perform EDA, engineer features, build models, and evaluate them.
