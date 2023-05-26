# Credit-Card-Approval-Prediction
Machine learning models used to predict if the credit card application should be approved or not.
1. Introduction
Small businesses and giant corporations are having difficulty surviving in the current economic recession. A sophisticated risk control can help reduce unnecessary cost and avoid unwanted situations. Credit score check is one of the risk control methods in the financial industry and banks. They examine personal information and data from credit card applicants to predict the probability of debts occurring. Credit score checking is crucial for the bank to decide whether to issue a credit card to the applicant.

The goal of this project is to build a prediction model that can determine the credit approval rate from each customer. We will use XGboost, logistic regression, and decision tree algorithms to answer our research question. Our dataset contains a lot of personal information and attributes about applicants, which will be used to build our models. Additionally, we will investigate the most influential factor in determining "good" clients and "bad" clients.

2. Exploratory Data Analysis
The dataset used in this project is from Kaggle website called "Credit Card Approval Prediction". It contains information of credit card users including genders, number of children, number of properties, their repayment dates, etc. Machine learning models could be established based on this dataset to help banks and financial institutions in judging whether a customer has good credit or not, so that the bank could make decisions on whether to lend a credit card to a certain customer or not.

2.1 Analysis Description
In this part, several analyses have been implemented through the goal of creating a model-ready dataset. During EDA, the following tasks were carried out:

Analysis of the structure of the dataset
Outliers' detection and solution
NA and duplicate value analysis and solution
Feature analysis, synthesis, and transformation
Encode categorical variables
Correlation analysis
2.2 Data Extraction
The dataset was downloaded from the Kaggle website using the "open datasets" package in Python. This package allows direct downloading of datasets from a given website (Kaggle in this case) by inputting the username and the corresponding key.

2.3 Data Cleanup
2.3.1 Structure of the Datasets
The dataset consists of two datasets: "application" and "credit_record". The "application" dataset contains information about customers who applied for a credit card, and the "credit_record" dataset contains information regarding credit histories for each customer. The structure and data types of both datasets were examined.

2.3.2 Check Outliers
Outliers were checked by looking at the boxplots of all numerical variables in the dataset. The outliers in the "AMT_INCOME_TOTAL" variable were identified and decided to be dropped.

2.3.3 Check Duplicated and Null Values
There were no duplicate records in either dataset. The "credit_record" dataset had no null values, but the "application" dataset had null values in the 'OCCUPATION_TYPE' variable. The null values in the 'OCCUPATION_TYPE' variable were replaced with "Unknown".

2.3.4 Convert 'DAYS_BIRTH' and 'DAYS_EMPLOYED'
The 'DAYS_BIRTH' and 'DAYS_EMPLOYED' variables were converted to more understandable formats. 'DAYS_BIRTH' was converted to 'age' (the age of the customer), and 'DAYS_EMPLOYED' was converted to the number of days the customer was employed.

2.3.5 Create Dependent Variable
A dependent variable was created to identify the clients based on their credit status. Customers who were past due for more than 60 days were designated as "0" (bad customers), and customers who paid off all debts or had no debts.

2.3.6 Feature Engineering
Several new features were created based on the existing variables to provide more information for the prediction model. These new features included:

'INCOME_PER_CHILD': Calculated as the ratio of the customer's income to the number of children they have.
'CREDIT_INCOME_PERCENT': Calculated as the ratio of the credit amount to the customer's income.
'ANNUITY_INCOME_PERCENT': Calculated as the ratio of the loan annuity to the customer's income.
'EMPLOYMENT_LENGTH': Categorized the length of employment into several groups.
2.3.7 Encode Categorical Variables
Categorical variables in the dataset were encoded using one-hot encoding to convert them into numerical format for the machine learning models. This process expanded the categorical variables into multiple binary columns.

2.3.8 Correlation Analysis
A correlation matrix was created to analyze the relationships between the variables. This helped identify any strong correlations between variables and potential multicollinearity issues.

3. Model Building and Evaluation
3.1 Data Preparation
The dataset was split into training and testing sets with a 70:30 ratio. The training set was used to train the models, while the testing set was used to evaluate their performance.

3.2 Model Selection
Three different algorithms were selected for this project: XGboost, logistic regression, and decision tree. These algorithms were chosen for their ability to handle both numerical and categorical variables and their suitability for classification tasks.

3.3 Model Training and Evaluation
Each model was trained on the training set and evaluated on the testing set using appropriate evaluation metrics such as accuracy, precision, recall, and F1-score. The models were tuned using cross-validation and grid search techniques to find the optimal hyperparameters.

3.4 Model Comparison
The performance of each model was compared based on the evaluation metrics to determine the best-performing model for credit card approval prediction.

4. Results and Conclusion
After training and evaluating the models, the results showed that the XGboost model achieved the highest accuracy, precision, recall, and F1-score compared to logistic regression and decision tree. Therefore, the XGboost model was selected as the best model for credit card approval prediction.

The important factors in determining "good" clients and "bad" clients were identified using feature importance analysis provided by the XGboost model. These factors can be used by banks and financial institutions to make informed decisions on credit card approvals and minimize the risk of bad debts.

In conclusion, this project successfully developed a credit card approval prediction model using machine learning algorithms. The model can effectively predict the credit approval rate from each customer, providing valuable insights for banks and financial institutions in making credit decisions.
