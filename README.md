## Credit Risk Analysis (Supervised Machine Learning : Classification)

<img width="400" alt="leaflet-logo" src="https://github.com/user-attachments/assets/4ac6c91f-55bc-41b8-aee5-e58aecd64ebb">

**Purpose of the Analysis:**

The purpose of this analysis is to evaluate the performance of a logistic regression model in predicting credit risk for a loan company. The analysis aims to assess how well the model identifies healthy loans (low-risk) and high-risk loans (likely to default), using a labeled dataset of historical loan data. The objective is to determine whether this model can be used to make informed lending decisions that minimize financial risk for the company while maximizing profitability.

The dataset contained financial information on loans, with features including loan size, interest rate, borrower income, debt-to-income ratio, number of accounts, derogatory marks, total debt, and the loan status. The goal was to predict the loan_status, which indicates whether a loan is healthy (low-risk) or high-risk.

**Target Variable:** 

The variable being predicted was loan_status, which had two possible values: 0 for healthy loans and 1 for high-risk loans. A value_counts analysis provided insight into the distribution of these two classes.

**Machine Learning Process: The analysis followed several stages:**
- **Data Preparation:** The data was split into features (X) and labels (y) using the loan_status as the target variable.
- **Data Splitting:** The dataset was split into training and testing sets using train_test_split from the sklearn library to ensure the model could be trained and evaluated effectively.
- **Model Training:** A logistic regression model was created using the LogisticRegression algorithm to predict the likelihood of a loan being high-risk or healthy.
- **Model Evaluation:** Performance metrics were calculated using the accuracy_score, balanced_accuracy_score, confusion_matrix, and classification_report from the sklearn metrics module.
- **Methods Used:** The logistic regression model was chosen for its effectiveness in binary classification tasks.

**Additionally:**
Metrics such as accuracy_score and balanced_accuracy_score were used to assess the overall performance.
Confusion matrix and classification_report provided detailed insights into the prediction results.
From the imbalanced-learn library, classification_report_imbalanced was employed to handle the imbalanced nature of the dataset.

## Results
* Based on Machine Learning :Logistic Regression model

<img width="400" alt="leaflet-logo" src="https://github.com/user-attachments/assets/13546fb7-abdf-403a-b351-0238341caf30">

**Class 0 (Healthy Loans : Low Risk):**

- **Precision(pre):100** : This indicates that all the loans predicted as healthy (class 0) are indeed healthy with perfect precision.

- **Recall(rec): 0.99** :Out of all actual healthy loans 99% were correctly identified, This shows very high sensitivity.

- **F1 score (f1):1** : This score is harmonic mean of percision and recall. A perfect score indicates a strong balance between percision and recall for healthy loans.

- **Support(sup) : 18765** : This indicates that out of total 75036 records, 18,765 were selected as a samples in class 0(healthy loans), indicating that the majority of the data consists of healthy loans.

**Class 1 (Non-Healthy Loans : High Risk):**

- **Precision(pre):84** : The model correctly identified 84% of the loans predicted as risky. Some risky loans are misclassified as healthy, as shown by this lower percision compared to class 0.

- **Recall(rec): 0.94** : This shows that the model is able to identify 94% of all actual risky loans , which is quite high for a minority class in imbalanced data. 

- **F1 score (f1):0.89** : The F1 score is a bit lower than for healthy loans but still good , indicating a solid balance between percision and recall for risky loans.

- **Support(sup) : 619** : There are significantly fewer risky loan samples compared to heealthy loans. 

**Ovarall Metrics:**

- **Avg/Total Accuracy (avg / total ): 0.99** : The overall accuracy is very high, meaning the model is generally perfoming well on both classes.

## Summary

Based on the confusion matrix and classification report, the model has performed well in distinguishing between healthy loans and high-risk loans:

**Confusion Matrix:**

<img width="400" alt="leaflet-logo" src="https://github.com/user-attachments/assets/39d4d065-d0c8-4fff-b9d8-a60544ccf524">

- **True Positives**  (High-Risk Loans correctly identified): 583
- **True Negatives**  (Healthy Loans correctly identified): 18,655
- **False Positives**  (Healthy Loans classified as High-Risk): 110
- **False Negatives**  (High-Risk Loans classified as Healthy): 36

**Justification for Model Recommendation:**

The logistic regression model demonstrates strong performance overall, particularly for predicting healthy loans, which make up the majority of the dataset. Below are key factors that justify using the model for the company's credit risk analysis:

High Accuracy (99%): The model correctly classifies 99% of the loans, providing confidence in the system's overall reliability.

**Excellent Performance for Healthy Loans:**

With a precision of 1.00 and recall of 0.99 for healthy loans, the model nearly perfectly classifies healthy loans. This minimizes the risk of mistakenly approving high-risk loans as healthy, thus avoiding potential losses.
Solid Performance for High-Risk Loans:

The model successfully identifies 94% of all high-risk loans (recall), ensuring that the majority of risky loans are flagged. Although there are some false positives (16% of loans classified as high-risk are actually healthy), this conservative approach is preferable in risk-averse lending scenarios where missed risky loans could result in defaults and financial losses.
Balanced Handling of Class Imbalance:

The dataset is imbalanced, with many more healthy loans (18,765) than high-risk loans (619). Despite this, the model manages to achieve macro-averaged precision (0.92) and macro-averaged recall (0.97), indicating that the model treats both classes fairly well.

**From a business perspective:**

Healthy Loans Misclassified as High-Risk (110 False Positives): These misclassified loans (110 out of 18,765) represent missed business opportunities. The company might decline these loans or offer worse terms (higher interest rates, stricter conditions) to borrowers who are actually low-risk, potentially pushing them to competitors or leaving revenue on the table.

High-Risk Loans Misclassified as Healthy (36 False Negatives): These 36 loans pose a more significant financial risk, as they represent high-risk borrowers who might default. The company may lose money if these loans are extended under favorable conditions (low interest rates) and later default.

**Final Recommendation:**
While the model demonstrated reasonable accuracy, precision, and recall, its performance may not be sufficient for deployment in a real-world scenario where misclassifying a healthy loan as high-risk could lead to lost business opportunities. If the model’s precision and recall are insufficient for the company's risk appetite, further model tuning or alternative models (such as decision trees or random forests) may be explored to improve performance.

In conclusion, the logistic regression model offers a basic yet effective approach to classifying loan risks, and it serves as a starting point for more complex model development in the future.

**References**
Data for this dataset was generated by edX Boot Camps LLC, and is intended for educational purposes only.




