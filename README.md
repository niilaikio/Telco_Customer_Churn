Business Problem:

 - Customer loyalty to telecom providers is down 22% post-pandemic (1.)
 - Churn can be described as customers ending or not choosing to continue their subscription
 - Customer churn causes financial challenges to telecom companies by losing revenue and by increasing customer acquisiton costs
 - If the factors that cause customers to churn can be identified, companies are able to take actions in reducing customer churn and increase longetivity with customers

Dataset:

 - IBM Sample Data
 - 7034 Observations
 - 21 Variables
 - ‘Churn’ is the target variable
 - Dataset doesn’t need cleaning 

Descriptive Analysis:

 - First we wanted to identify how many customer have churned 
 - We found that 26.6% of customers churned within the last month
 - Dataset is clearly unbalanced
 - We also found out that the spread between customers by tenure had two opposite sides: customers who have been subscribing for a longer period tend to stay

![image](https://github.com/user-attachments/assets/f589ef83-1fca-4c6b-b73b-35cfd7b58f12) <img width="421" alt="image" src="https://github.com/user-attachments/assets/5ff2bbae-d1af-4a8a-b41e-50e1aadfb5a6">

 - We wanted to identify which variables had the highest correlation with ‘Churn’
 - Month-to-month contract and lack of online security had the highest correlation leading to churn
 - Two-year contract and lack of internet service had negative correlation to churn, so those variables seemed to make customers stay

![image](https://github.com/user-attachments/assets/41dc3d04-c333-4ae9-b371-737de0e8e8b9)

Data Manipulation

 - Dropped ‘customerID’ since it is only a identifying value which has no use in our analysis
 - ’TotalCharges’ had 11 missing values, which were deleted
 - Made dummies for binary variables
 - Since the data was unbalanced we used SMOTE to create synthetic observations to balance the data
 - The data was split 30:70 to the training and testing set

Model Selection

 - Since our data was unbalanced, we wanted to see the difference between balanced and unbalanced models
 - Models used:
    - Decision Tree
    - Linear Regression
    - XGBoost
    - For Linear Regression and Decision Tree, we used balanced and unbalanced datasets

Model Evaluation

 - Balanced Logistic Regression had the best AUC score of 0.835
 - All of the models performed quite well
 - We proceeded with the best 3 models which were:
    - Balanced Logistic Regression
    - Unbalanced Logistic Regression
    - XGBoost

![image](https://github.com/user-attachments/assets/4bc279b6-7d25-4bc2-91cb-4b18582ec987)

Confusion Matrix Evaluation

![image](https://github.com/user-attachments/assets/c5278dc4-680e-46dc-81e5-38043287e343) ![image](https://github.com/user-attachments/assets/48ac732f-e840-4622-a0c0-1a8841eea82d) ![image](https://github.com/user-attachments/assets/7e4fc335-8a01-45c1-99d0-94bdec8c494d)

 - XGBoost & Unbalanced Logistic Regression models were good when identifying True Negatives
 - Balanced Logistic Regression model proved to be better overall, when identifying True Negatives & True Positives

Important Features

 - We were able to identify features which have the most amount of influence on the model’s performance:
  - They were total money charged, month-to-month contract
  - At the opposite side is tenure, two-year contract

<img width="429" alt="image" src="https://github.com/user-attachments/assets/748e649b-27fa-4457-be3c-9746d4aa4bb4">

Business Implications

 - To reduce customer churn, telecom companies must predict which customer are at high risk of churning
 - To reduce their churn rate, the company should target customers who are on month-to-month contract, use fiber optic internet, have higher monthly charges on average and who have shorter tenure
 - Balanced Logistic Regression is our model of choice: best F1-score, AUC, RMSE and identifyes both TNR and TPR relatively well
    - Logistic Regression model is more interpretable than XGBoost.




