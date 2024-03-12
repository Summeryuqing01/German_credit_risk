# German credit risk

## Objective
The primary objective of this project is to develop a predictive model using the German credit risk dataset that can accurately forecast the credit amount that potential borrowers are likely to receive.

## EDA
### Dataset:
<img width="419" alt="Screenshot 2024-03-12 at 00 14 14" src="https://github.com/Summeryuqing01/German_credit_risk/assets/56556388/45bd8a36-c3d1-4543-8c5d-7bb1b8565f9b">


Predictors: Age (numeric),  Sex (categorical),  Job (ordinal),  Housing (categorical), Savings (categorical), Checking (categorical),  Duration (numeric), Purpose (categorical)\
Response variable: credit amount (continuous)

<img width="383" alt="Screenshot 2024-03-12 at 00 22 21" src="https://github.com/Summeryuqing01/German_credit_risk/assets/56556388/d4af1dce-b5b2-48b6-aa1d-19bdc17de73c">

<img width="383" alt="Screenshot 2024-03-12 at 00 22 27" src="https://github.com/Summeryuqing01/German_credit_risk/assets/56556388/2bedd4c9-7f39-443c-a576-7ac8771080a4">\
The age distribution is skewed to the right, indicating a younger applicant trend, with fewer older individuals applying for credit.\
Job categories are unevenly distributed, with a significant majority occupying the second job category, which might indicate a mid-level professional status amongst the applicants.

<img width="400" alt="Screenshot 2024-03-12 at 00 22 34" src="https://github.com/Summeryuqing01/German_credit_risk/assets/56556388/594ac12f-7e16-465d-83d2-2f5dbc5824d2">\
The average credit amount varies significantly across different purposes, with 'vacation/others' and 'business' showing the highest averages, suggesting that credits for leisure and business tend to be larger.

<img width="535" alt="Screenshot 2024-03-12 at 00 22 42" src="https://github.com/Summeryuqing01/German_credit_risk/assets/56556388/ae8953d8-47a6-41cf-a24f-5b8d8dc73b5d">\
From a risk perspective, loans with a high credit-to-duration ratio might be riskier, as they could be harder for borrowers to repay in a shorter time frame.
The peak of the distribution occurs close to zero, suggesting that the majority of loans in the dataset have a small ratio of credit amount to the duration of the loan.


### Imputation: MissForest:
MissForest is an imputation method used in statistics and machine learning to handle missing data. It is specifically designed for imputing missing values in high-dimensional datasets where the variables (features) may have complex relationships. MissForest is an extension of the Random Forest algorithm, which is a popular ensemble learning technique.

In MissForest, the algorithm builds multiple decision trees based on the observed data, using the non-missing values as predictors to predict the missing values. It iteratively imputes missing values by using the predicted values from the decision trees. The process continues until convergence or a predefined stopping criterion is met.

MissForest is advantageous because it can handle different types of variables (continuous, categorical) and complex interactions between variables. It also provides flexibility in handling missing data patterns and tends to perform well in various types of datasets.

## Models:
### Linear Regression

### Dummy Variable Regression

### Polynomial Regression

### Random Forest Regression

### Neural Network
<img width="460" alt="Screenshot 2024-03-12 at 00 23 05" src="https://github.com/Summeryuqing01/German_credit_risk/assets/56556388/977acb1b-8df8-4b45-a399-9bd1f44f60e4">


## Model Comparison
<img width="697" alt="Screenshot 2024-03-12 at 00 09 00" src="https://github.com/Summeryuqing01/German_credit_risk/assets/56556388/d0c32a04-cff1-4e8e-817b-059845c18cfe">

## References:
[Miss Forest Imputation](https://cran.r-project.org/web/packages/missForest/missForest.pdf)

## Data source:
https://www.kaggle.com/datasets/uciml/german-credit/code

## Contributors:
Ian Rector\
Summer Xia\
Jiahao Zhang
