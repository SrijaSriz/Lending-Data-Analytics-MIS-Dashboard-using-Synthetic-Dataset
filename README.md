Synthetic Lending Dataset Project for MIS Analysis 📈
This project's goal is to create a synthetic dataset that mimics real-world lending operations. This dataset serves as a foundation for building dashboards, analyzing key performance indicators (KPIs), and deriving insights to support decision-making for Management Information Systems (MIS) Analyst roles. The project helps in practicing reporting, dashboarding, and analytical tasks common to an MIS Analyst's responsibilities.


Data Dictionary and Engineering 🛠️
The dataset simulates common lending operation data, including customer behavior, loan performance, repayment trends, and risk indicators.

Dataset Columns
Column	Type	Description
Customer_ID	String	
Unique customer identifier (e.g., CUSTXXXX) 


Age	Integer	
Age of borrower, range [18–70] 


Gender	Categorical	
Male / Female 

Income	Numeric	
Annual income, range [₹30,000 – ₹30,00,000] 


Employment_Type	Categorical	
Salaried / Self-Employed 

Loan_ID	String	
Unique loan identifier (e.g., LOANXXXX) 


Loan_Type	Categorical	
Home / Auto / Education / Personal 

Loan_Amount	Numeric	
Loan principal amount 

Interest_Rate	Float	
Annual % rate, range [5% – 25%] 


Tenure_Months	Integer	
Duration of loan in months 

Application_Date	Date	
Loan application date 

Approval_Status	Categorical	
Approved / Rejected 

EMI_Amount	Numeric	
Monthly repayment amount 

Disbursal_Date	Date	
Date loan amount credited 

EMIs_Paid	Integer	
Number of EMIs successfully paid 

Default_Status	Categorical	
Yes / No (default if 

EMIs_Paid < Tenure_Months and Outstanding Balance > 0) 


Outstanding_Balance	Numeric	
Remaining balance if loan is active 


Export to Sheets
Feature Engineering
New variables were created to enhance predictive power. These include:


Debt-to-Income Ratio: The ratio of the requested loan amount to the applicant's income, which helps assess repayment capacity.


EMI Burden: The proportion of EMI to income, indicating monthly affordability stress.


Payment Progress: The percentage of EMIs paid relative to the total tenure, which highlights repayment discipline.


Application-to-Disbursal Days: The processing time between the loan application and disbursal, which can capture operational or fraud-related delays.


Loan-to-Tenure Ratio: A normalized monthly loan burden.


Categorical Encoding: Conversion of categorical features like Employment_Type, Loan_Type, and Approval_Status into machine-readable numeric variables.

Exploratory Data Analysis (EDA) & Insights 📊
The EDA process involved checking for missing values and duplicates and creating visualizations to gain basic insights.


Key Findings

Correlation Analysis: Numerical variables have low-to-moderate correlations, with a moderate positive relationship between Loan_Amount and Income. This suggests that higher-income applicants tend to apply for larger loans.



Distributions & Outliers: Variables like Income and Loan_Amount are right-skewed and contain notable outliers that may affect model performance. * 

Categorical Variables & Loan Approval: Salaried applicants have a higher approval rate than self-employed applicants.


Default Risk Indicators: Self-employed applicants show a higher likelihood of default compared to salaried ones. Younger applicants (<30) and older applicants (>55) show slightly higher default risks, whereas mid-age groups (30–45) appear more stable.


Predictive Modeling 🤖
Machine learning models were applied to predict loan default probability. The dataset was split into training (80%) and testing (20%) sets using stratified sampling to maintain class balance. 


StandardScaler was used for feature normalization.

Models and Results
The models were evaluated using a confusion matrix, classification report (Precision, Recall, F1-score), and ROC-AUC score.


Logistic Regression: Achieved an accuracy of 99.7% and a perfect ROC-AUC score of 1.0, showing excellent separation between defaulters and non-defaulters.



Decision Tree Classifier: Also reached 99.7% accuracy, but with a slightly lower ROC-AUC of 0.997. There were minor misclassifications, including 1 false positive and 2 false negatives.




Random Forest Classifier: This model was the strongest, achieving a perfect 100% accuracy and an ROC-AUC score of 1.0. It effectively eliminated misclassifications by combining multiple trees.



------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------


  POWER BI DASH BOARD (MIS DASHBOARD)
  The Lending MIS Dashboard enables monitoring of loan portfolio performance, approval efficiency, and risk exposure. With interactive visuals and DAX measures,slicers,RLS,WHAT-IF, it provides actionable insights for lending decision-making. 
