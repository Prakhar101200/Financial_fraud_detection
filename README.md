# Financial Fraud Detection Project

## Overview

This project focuses on building a predictive model to detect fraudulent financial transactions. The dataset consists of over 6 million transactions, each described by various features that might indicate fraudulent behavior. The goal is to identify and prevent fraudulent transactions in real-time.

## Project Structure

- **Data Cleaning**: Addressing missing values, handling outliers, and mitigating multi-collinearity to ensure the dataset is ready for modeling.
- **Feature Engineering**: Creating new features to capture potentially fraudulent patterns, such as `log_amount`, `high_amount_flag`, and `large_balance_change_flag`.
- **Model Building**: Developing predictive models using Random Forest and XGBoost classifiers.
- **Model Evaluation**: Assessing the models' performance using confusion matrices, ROC AUC scores, and classification reports.

## Data Cleaning

1. **Missing Values**: 
   - Numerical features: Imputed using the mean value.
   - Categorical features: Imputed using the most frequent category.

2. **Outliers**: 
   - Outliers were handled through feature engineering. For example, transaction amounts were transformed using a logarithmic scale to reduce skewness.

3. **Multi-Collinearity**: 
   - Features were selected based on their importance and lack of strong correlations with other features to avoid redundancy.

## Feature Engineering

Key features created include:

- `log_amount`: Logarithmic transformation of transaction amounts.
- `high_amount_flag`: A flag indicating unusually large transaction amounts.
- `large_balance_change_flag`: A flag indicating significant changes in account balances.
- `balance_change_ratio`: Ratio of the balance change relative to the transaction amount.
- `high_frequency_flag`: A flag for accounts with a high frequency of transactions.

These features were designed to enhance the model's ability to detect fraudulent behavior.

## Model Building

### Random Forest Classifier
- A robust ensemble model that combines multiple decision trees.
- **Note**: Hyperparameter tuning was attempted but failed due to computational power limitations.

### XGBoost Classifier
- An advanced gradient boosting model with high accuracy and efficiency.
- Uses GPU acceleration for faster computation on large datasets.

## Model Evaluation

- **Random Forest Classifier**:
  - ROC AUC Score: 0.857
  - Balanced performance with good recall and precision.
  
- **XGBoost Classifier**:
  - ROC AUC Score: 0.907
  - Higher specificity but lower recall, particularly in detecting fraudulent transactions.

## Key Findings

- **Important Features**:
  - `log_amount` was the most significant predictor of fraud.
  - Flags for large transactions and significant balance changes also played crucial roles.
  
- **Feature Importance**:
  - `log_amount`: 93.02%
  - `large_balance_change_flag`: 5.44%
  - `balance_change_ratio`: 1.02%
  - Other flags contributed marginally.

## Recommendations

- **Prevention Measures**:
  - Implement real-time monitoring using the model to flag potentially fraudulent transactions.
  - Automate fraud detection processes for timely intervention.
  - Regularly update the model with new data to adapt to evolving fraud patterns.

## Future Work

- **Hyperparameter Tuning**: Address computational limitations to fully optimize the Random Forest model.
- **Model Enhancement**: Experiment with additional algorithms and ensemble methods to improve detection accuracy.
- **Real-Time Deployment**: Integrate the model into a production environment for real-time fraud detection.

## Conclusion

This project provides a comprehensive approach to detecting fraudulent financial transactions. By leveraging advanced machine learning techniques and careful feature engineering, the model offers a robust tool for financial institutions to identify and mitigate fraudulent activities.

## Contact

For questions or further information, please contact Prakhar Raj Gupta at prakhargupta10900@gmail.com 
