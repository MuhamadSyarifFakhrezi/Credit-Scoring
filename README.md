# Credit Scoring Analysis

## Business Understanding

Despite providing various tech-based financial solutions, credit risk checks when individuals and businesses apply for loans are still done manually. After operating for one year, Finance Merdeka has collected data related to the financial and credit status of all customers, this data is expected to be leveraged to optimise the credit risk checking process when loan applications are ongoing.

### Business Problems

The credit risk checking process is entirely done manually by the Risk Analytics Analyst team, this process definitely takes a lot of time and is very inefficient, by optimizing this process it is expected to cut the resource usage of the company.

### Project Scope

To address this business problem, we will use the collected data to develop a machine learning-based system to predict the credit risk of a customer. In the development process, we will experiment with several machine learning algorithms and compare them to find the best performance model, and then develop a simple prototype of the system.

## Data Understanding

Data Source: [data.csv](https://www.kaggle.com/datasets/parisrohan/credit-score-classification)

Customer financial profile and credit history dataset, which contains the following informations:
- ID: Unique identifier for each entry in the dataset.
- Customer_ID: Identifier for each customer.
- Month: Month of data collection.
- Name: Name of the customer.
- Age: Age of the customer.
- SSN: Social Security Number of the customer.
- Occupation: Occupation of the customer.
- Annual_Income: Annual income of the customer.
- Monthly_Inhand_Salary: Monthly salary after deductions.
- Num_Bank_Accounts: Number of bank accounts the customer has.
- Num_Credit_Card: Number of credit cards the customer has.
- Interest_Rate: Interest rate applied on loans.
- Num_of_Loan: Number of loans the customer has.
- Type_of_Loan: Type of loan taken by the customer.
- Delay_from_due_date: Number of days delayed from due date for payments.
- Num_of_Delayed_Payment: Number of delayed payments made by the customer.
- Changed_Credit_Limit: Indicates if the credit limit has been changed.
- Num_Credit_Inquiries: Number of credit inquiries made by the customer.
- Credit_Mix: Mix of different types of credit accounts held by the customer.
- Outstanding_Debt: Amount of outstanding debt.
- Credit_Utilization_Ratio: Ratio of credit used to credit available.
- Credit_History_Age: Age of credit history.
- Payment_of_Min_Amount: Indicates if minimum payment amount is met.
- Total_EMI_per_month: Total Equated Monthly Installment (EMI) paid by the customer.
- Amount_invested_monthly: Amount invested monthly by the customer.
- Payment_Behaviour: Payment behavior of the customer.
- Monthly_Balance: Monthly balance in the account.
- Credit_Score: Credit score of the customer. -> Target variable

## Data Cleaning

- Customize the data type.
- Overcome invalid values.
- Overcome missing values.

## Exploratory Data Analysis

How do customers behave based on their credit score?

![categorical](https://github.com/user-attachments/assets/f55147bf-f2ab-4715-95c7-84a78371b3c8)

- Customers with a Good credit score have the ability to manage their credit well.
- Customers with Poor and Standard credit scores tend to only make minimum payments as seen in the Payment_of_Min_Amount column.
- Customers with Poor and Standard credit scores usually have a profile of 'Low_spent_Small_value_payments' in the Payment_Behaviour feature.

![numerical](https://github.com/user-attachments/assets/6dc48726-55f4-437f-8e4a-8789e28be6e5)

- Customers who have a Good credit score tend to have an older age.
- The higher the credit history age of a customer, the better the credit score the customer has.
- Customers with a Poor credit score tend to have multiple bank accounts, multiple credit cards, a large amount of debt, and high credit card interest rates. In addition, they also tend to make delinquent payments.

## Data Preprocessing

- Apply the undersampling technique to handle imbalanced data in the training data.
- Perform encoding with One Hot Encoder and scaling with Min Max Scaler.
- Apply the Principal Component Analysis (PCA) method to overcome multicollinearity in independent variables.

## Modeling

We compare three models with different algorithms and then use the one with the best performance, the three algorithms are Decision Tree Classifier, Random Forest Classifier, and Extreme Gradient Boosting Classifier.

## Evaluation
![xgb](https://github.com/user-attachments/assets/735d4dce-f170-4610-a659-37a8af67bb8c)


Based on results, the Extreme Gradient Boosting model has the best performance in identifying customers with Poor credit scoring, both based on f-1 score (72% of accuracy) and confusion_matrix. We used this model to create a simple prototype to identify customer credit risk.

========================================================================================================================================================================

**Jupyter Notebook**

Source Code Link (Jupyter Notebook): [notebook.ipnyb](https://github.com/MuhamadSyarifFakhrezi/Credit-Scoring/blob/main/notebook.ipynb)

**Preparation**

Setup environment:
- Via Google Colabolatory:
   1. Open the [notebook.ipynb](https://github.com/MuhamadSyarifFakhrezi/Credit-Scoring/blob/main/notebook.ipynb) file in Google Colaboratory
   2. Run the following code
      ```
      !pip install -r requirements.txt
      ```
- Via Local:
   Run the following code in terminal/shell
   ```
   mkdir credit_scoring_customers
   cd credit_scoring_customers
   pipenv install
   pipenv shell
   pip install -r requirements.txt
   ```

**Run Streamlit App**

```
streamlit run app.py
```
Streamlit Prediction App Link: [Streamlit Web App](https://student-dropout-analysis-msyarif.streamlit.app/)
