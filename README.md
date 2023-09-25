# Capstone-Project
## Prediction on credit card default

The source of the dataset was taken from https://www.kaggle.com/datasets/utkarshx27/default-of-credit-card-clients-dataset

**Objective**: As data analyst, we are to do a research on the case of customers default payments in Taiwan and compares the predictive accuracy of probability of default. 

This dataset consist of 30,000 entries.

File: default of credit card clients.xls

The original file downloaded frok kaggle had 2 headings on each columns, the first heading labeled by X1, X2....X23 and last column label Y was removed and will use the second row heading instead. 

### Metadata 
|Column |Description  |
|--|--|
|ID |ID  |
|LIMIT BALANCE  |Amount of the given credit (TWD): it includes both the individual consumer credit and his/her family (supplementary) credit.  |
|SEX  |Gender (1 = male; 2 = female).  |
|EDUCATION  |Education (1 = graduate school; 2 = university; 3 = high school; 4 = others).  |
|MARRIAGE  |Marital status (1 = married; 2 = single; 3 = others).  |
|AGE  |Age (year).  |
|PAY_0  |History of past payment. The repayment status in September 2005.  |
|PAY_2  |History of past payment. The repayment status in August 2005  |
|PAY_3  |History of past payment. The repayment status in July 2005  |
|PAY_4  |History of past payment. The repayment status in June 2005  |
|PAY_5  |History of past payment. The repayment status in May 2005  |
|PAY_6  |History of past payment. The repayment status in April 2005  |
|BILL_AMT1  |Amount of bill statement (TWD) in September 2005.  |
|BILL_AMT2  |Amount of bill statement (TWD) in August 2005.  |
|BILL_AMT3  |Amount of bill statement (TWD) in July 2005.  |
|BILL_AMT4  |Amount of bill statement (TWD) in June 2005.  |
|BILL_AMT5  |Amount of bill statement (TWD) in May 2005.  |
|BILL_AMT6  |Amount of bill statement (TWD) in April 2005.  |
|PAY_AMT1  |Amount of previous payment (TWD) in September 2005.  |
|PAY_AMT2  |Amount of previous payment (TWD) in August 2005.  |
|PAY_AMT3  |Amount of previous payment (TWD) in July 2005.  |
|PAY_AMT4  |Amount of previous payment (TWD) in June 2005.  |
|PAY_AMT5  |Amount of previous payment (TWD) in May 2005.  |
|PAY_AMT6  |Amount of previous payment (TWD) in April 2005.  |
|default payment next month  |Target Column - binary variable, default payment (Yes = 1, No = 0).  |

The measurement scale for the repayment status is: -1 = pay duly; 1 = payment delay for one month; 2 = payment delay for two months;..; 8 = payment delay for eight months; 9 = payment delay for nine months and above

#### Import Library
- Pandas
- Numpy
- Matplolib
- Seaborn

#### Data Cleaning and Transformation
- Remove ID column
- Rename the headings by month so that it is easier to understand
- In metadata, there is no define for Education 0, 5 and 6 so I grouped it under 4 (Others)
- In metadata, there is no define for Marriage 0 so I grouped it under 3 (Others)

#### Predictive model
- Logistic Regression Classification
- Decision Tree Classifier
- Extra Tree Classifier
- Random Forest Classifier
