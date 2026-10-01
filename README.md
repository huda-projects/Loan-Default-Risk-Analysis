# Loan Default Risk: Exploratory Data Analysis and Baseline Model.

## 1. Project Objective and Research Question.
### Research Question
Can we identify borrowers who are at higher risk of default so that a financial institution can make better lending and credit-risk decisions?
### Project Objective
The objective of this project is to use historical borrower and loan data to investigate characteristics and patterns associated with loan default. The analysis will use data cleaning, exploratory data analysis, feature engineering, and visualization techniques to develop a better understanding of the factors related to default risk.
A baseline classification model will then be developed to establish an initial benchmark for predicting loan default. The model's performance will be evaluated using an appropriate evaluation metric, with the choice of metric justified according to the classification problem and business context.
The results of the analysis will be used to answer the research question and provide information that may help financial institutions better understand credit risk and make more informed lending decisions.

## 2. Data Used
The analysis uses the Loan Default Dataset, publicly available through Kaggle. The dataset contains historical information about loan applications, borrowers, financial characteristics, credit information, property characteristics, and loan outcomes.
Source: Kaggle — Loan Default Dataset
The dataset contains 148,670 observations and 34 features, including 33 predictor variables and one target variable (Status).
3. Analysis Approach
The analysis will follow a structured process designed to move from understanding the raw data to developing an initial predictive model.
First, the dataset will be inspected and cleaned to address issues such as missing values, duplicate observations, incorrect data types, and potentially invalid values. Next, exploratory data analysis will be conducted to examine distributions, patterns, and relationships among borrower characteristics, loan characteristics, and default outcomes.
Outliers and unusual observations will also be investigated and feature engineering will then be used where appropriate.
Following the exploratory analysis, the prepared data will be used to develop a baseline classification model. The model will be evaluated using an appropriate performance metric, and the result will be interpreted in relation to the research question and business problem.

## 3. Data Cleaning and Preparation
The dataset was cleaned and prepared to ensure that the analysis and modeling were based on reliable and meaningful information. Missing values were reviewed to understand their distribution and relationship with the target variable. The largest missing values were found in Upfront_charges, Interest_rate_spread, and rate_of_interest. 
For Upfront_charges and rate_of_interest, missing values were heavily concentrated among default observations. Removing these observations would have eliminated the default group needed for classification, so these features were removed rather than deleting the affected observations. Interest_rate_spread was also removed because it had no observed values for the default group (Status 1) and its available observations belonged only to the non-default group (Status 0), meaning it could not provide useful information for comparing the two target categories. The ID feature was removed because it is only an identifier, while yearwas removed because it contained the same value (2019) for all observations. 

The features construction_type, Secured_by, and Security_Type were also removed because each contained only 33 observations in one category and therefore provided very limited variation. Duplicate observations were checked, and none were identified.
The remaining data was further reviewed for unusual values and potential anomalies. In particular, LTV values above approximately 125% were identified as unusually high and were treated as anomalous based on both statistical analysis and their business interpretation. After the cleaning process, the dataset contained 120,422 observations and 26 features, including the target variable Status, with no remaining missing values. The cleaned dataset retained both target categories, with 100,878 non-default observations (Status 0) and 19,544 default observations (Status 1), providing a consistent dataset for exploratory analysis and baseline classification modeling.

## 4. Exploratory Data Analysis
The exploratory data analysis examined borrower and loan characteristics to identify patterns associated with loan default and to better understand which features may help distinguish borrowers with different levels of observed default risk. For categorical features, observed default rates were compared across categories. Five features showed the largest differences in default rates and were selected for further analysis: lump_sum_payment, Neg_ammortization, loan_type, 
business_or_commercial, and loan_purpose. Selected figures are included below.





