**_Creadit Risk Modeling_**
_From the Customer Data, we have to predict weather or not to give a loan to a customer_

**_Paradox of Banking System_**
_Bank lends money to those who don't need money_

- Target Column: Possible answers => P1, P2, P3, P4
- P1 > P2 > P3 > P4 This is the priority of a customer for a bank to decide upon giving loan.
- By calculating, Bank assests and liablity with Customers previous records of loan, TL, PAR, DPD; I have calculate target variable.
- The dataset which have been used are 1) Cibil Dataset which is publically available on Kaggle and 2) Bank's internal dataset which is private.
- By looking at Cusotmer's porfolio and bank's status the target variable will be decided.

_Dataset Information_

### The internal Dataset:

- The shape of dataset: (51336, 26)
- The column having count of null values < 10,000 ; I have removed those rows from the dataset

### The external dataset:

- The shape of dataset: (51336, 62)
- The columns containing null count > 10,000 ; I have removed those columns from the dataset because otherwise delinquency level will be higher and I don't want to give such data in my model.

### Combining two datasets:

- I have used inner join for combining two dataset with having common column 'PROSPECTID' -> Primary key.
- The reason behind using inner join is because, It will contain only those values which are common in both the datasets.
- So, there will be no null values in the final combined dataset.
- Both the dataset are having the customer information, so I have combined the both datasets into one after cleaning all both the datasets

### Dividing the columns into 2 parts

1. Categorical columns

- Now, how much categorical columns are related to output columns that is going to checked by chi^2 contingency.
- Using chi2 contingency, I am doing feature selection for categorical columns.
- For all those columns having pval <= alpha(0.05) , I'll select only those columns as a deciding factor in predicting my targer column.

2. Numerical columns

- By calculating multi-colinearity using VIF (Variance Inflation Factor), the threshold for this project is "6".
- If any column crosses this threshold, I am going to drop those columns from my IVs.
