
### Universal Bank Loan Promotion Model

#### Problem Statement:

Universal Bank has initiated a consumer loan program to encourage existing customers to borrow. They tested a loan promotion on a random sample of 5,000 customers, with 480 accepting the offer. The bank aims to reduce promotional costs while targeting only a subset of customers most likely to accept the offer. The cost per customer promotion is $10, and the profit from obtaining a loan customer is $100. Hence, the net profit formula is:

- **Profit for TP**: $90  
- **Profit for FP**: -$10  
- **Profit for TN**: $0  
- **Profit for FN**: -$90  

The goal is to build a predictive model to maximize net profit by identifying the subset of customers most likely to accept the loan offer.


### Approach:

1. **Data Preprocessing**:
   - The dataset `UniversalBank.csv` includes features such as demographics, financial information, and loan details. Unnecessary columns like 'ID' and 'ZIP Code' were dropped.
   - The target variable is `Personal Loan`, which indicates whether a customer accepts the loan offer.

2. **Model Development**:
   - Two models were developed: Logistic Regression and Random Forest Classifier.
   
3. **Logistic Regression**:
   - Data was split into training (70%) and testing (30%) sets using a stratified split to ensure an even distribution of loan acceptance across both sets.
   - A custom profit-based scoring function was created to evaluate model performance.
   - **Grid Search** was used to tune hyperparameters (`C` and `penalty`) for Logistic Regression, resulting in the best performing model with `C=10` and `penalty='l1'` (Lasso regression).
   - The final Logistic Regression model achieved a net profit of $3840 on the test dataset of 1500 members.

4. **Random Forest Classifier**:
   - Similar steps were followed for Random Forest, with tuning hyperparameters like `n_estimators` and `max_depth`.
   - Grid Search found the best Random Forest model with `n_estimators=200` and `max_depth=None`.
   - This model achieved a higher net profit of $9890 for the 1500 members in the test dataset.


### Results:

- **Logistic Regression**:
  - Best Parameters: `C=10`, `penalty='l1'`
  - Net Profit: $3840 for 1500 members
  
- **Random Forest**:
  - Best Parameters: `n_estimators=200`, `max_depth=None`
  - Net Profit: $9890 for 1500 members

- **Conclusion**:
  - The Random Forest Classifier outperforms Logistic Regression in identifying the target customers and maximizing profit for Universal Bank.

This project highlights the importance of tailored predictive modeling to achieve business objectives efficiently.
