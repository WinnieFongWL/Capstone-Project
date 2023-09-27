# Capstone-Project
## Prediction on credit card default

![CreditCardPicture](https://github.com/WinnieFongWL/Capstone-Project/assets/144866583/9ac49301-0e64-4b5e-b9a6-a174882b7261)

The source of the dataset was taken fro
m https://www.kaggle.com/datasets/utkarshx27/default-of-credit-card-clients-dataset

**Objective**: As data analyst, we are to do a research on the case of customers default payments in Taiwan and compares the predictive accuracy of probability of default. 

**What is Credit Card default?**
Missing credit card payments once or twice does not count as a default. A payment default occurs when you fail to pay the Minimum Amount Due (MAD) on the credit card for a few consecutive months. Usually, the default notice is sent by the card issuer after 6 consecutive missed payments. However, the final call rests with the issuer. So, it is important to pay your credit card bill on time and in full to save yourself from high interest charges and being a defaulter.

**Credit Card default timeline: What happens after you miss payments?**
Your credit card account will not be marked as default on missing the first bill payment. Some issuers even give additional grace period after the payment due date during which no late payment charges will be levied. If you still do not pay the Minimum Amount Due then the issuer will report you as delinquent. You will be marked delinquent for the number of days you haven’t paid the credit card bill.

After this subsequent timeline, the issuer will increase their efforts to collect the debt from you. You will receive frequent phone calls, SMSs and emails. And, after 90 days, Loan Recovery Agents (LRAs) might pay you a visit. Some credit card providers might file a police complaint or send a legal notice while others might offer you a compromise in the form of a one-time settlement. If you do not pay off your bills for 190 days, that is, over 6 months, your credit card account will be put under the recovery pool. This is the final resolution the issuer can take. Under this scenario, the issuer will declare your account as a Non-Performing Asset (NPA). This means that the issuer sees your credit card account as a loss. Now, they may file a lawsuit against you or sell your debt to a debt collection agency.

This dataset consist of 30,000 entries.

File: default of credit card clients.xls

The original file downloaded from kaggle had 2 headings on each columns, the first heading labeled by X1, X2....X23 and last column label Y was removed and will use the second row heading instead. 

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

![Original dataset](https://github.com/WinnieFongWL/Capstone-Project/assets/144866583/99e6bc27-fefd-439b-ab04-c70c59167b26)

#### Import Library
- Pandas - is a library that offers fast and flexible data structures and operations for manipulating and processing tabular and multidimensional data.
- Numpy - It consists of in-built mathematical functions for easy computations, it supports large matrics and multi-dimensional data.
- Matplolib - Plot high defined figures like pie charts, histograms, scatterplots, graphs, etc.
- Seaborn - is a library for making statistical graphics in Python. It builds on top of matplotlib and integrates closely with pandas data structures.

#### Data Cleaning and Transformation
- Remove ID column
- Rename the headings by month so that it is easier to understand
- In metadata, there is no define for Education 0, 5 and 6 so I grouped it under 4 (Others)
- In metadata, there is no define for Marriage 0 so I grouped it under 3 (Others)

#### Predictive model
- **Logistic Regression Classification** - is a process of modeling the probability of a discrete outcome given an input variable. The most common logistic regression models a binary outcome; something that can take 2 values such as true/false, yes/no, and so on.
- **Decision Tree Classifier** - is a supervised learning technique. It is capable of working with both classification and regression techniques. It resembles a tree with nodes, as the name implies. The amount of criteria determines the branches. It divides data into these branches until it reaches a threshold unit. There are root nodes, child nodes, and leaf nodes in a decision tree.
- **Extra Tree Classifier** - (short for extremely randomized trees) like the random forests algorithm, creates many decision trees, but the sampling for each tree is random, without replacement. This creates a dataset for each tree with unique samples. A specific number of features, from the total set of features, are also selected randomly for each tree. The most important and unique characteristic of extra trees is the random selection of a splitting value for a feature.
- **Random Forest Classifier** - is also used for supervised learning. The main distinction from decision tree is that it does not rely on a single decision. It assembles randomized decisions based on many decisions and then creates a final decision depending on the majority.

### Accuracy score
|Model use |Score  |
|--|--|
|Logistic Regression |77.87%  |
|Decision Tree | 71.76% |
|Extra Tree | 80.87% |
|Extra Tree (estimators = 300) | 80.91% |
|Extra Tree (class bal) | 92.97% |
|Random Forest | 81.34% |
|Random Forest (estimators = 300) | 81.35% |
|Random Forest (class bal) | 89.48% |
