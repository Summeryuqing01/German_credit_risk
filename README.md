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
<img width="280" alt="Screenshot 2024-03-12 at 18 27 27" src="https://github.com/Summeryuqing01/German_credit_risk/assets/56556388/32c3d354-b192-45a7-9f2e-dc4c5db0c0b1"> \
<img width="216" alt="Screenshot 2024-03-12 at 18 27 32" src="https://github.com/Summeryuqing01/German_credit_risk/assets/56556388/33194b72-d16b-42d7-9720-e07d3f6d152e">

These results suggest that while the top three correlated features contribute significantly to the model, other variables in the dataset also provide valuable information that enhances the model's predictive power.

### Dummy Variable Regression
<img width="289" alt="Screenshot 2024-03-12 at 18 29 22" src="https://github.com/Summeryuqing01/German_credit_risk/assets/56556388/843ddfa5-2522-4a26-9121-87be12ccf310">\
Different models were evaluated by excluding one subcategory at a time from either the savings, checking, or purpose variables. \
Best Performance: The model excluding Purpose_repairs shows the best performance with the lowest MSE and RMSE, and the highest R² (0.524).
### Ordinal Data
We were having trouble getting results better than 0.5 R^2 and MSE’s of around 4,000,000
We decided to make the categorical data ordinal for Housing, Savings, and Checking and excluded Purpose since it did not work well to make it ordinal
Job was already encoded as an ordinal variable, bu for some reason housing, savings and checking were not even though they make for very good ordinal variables
Then eliminated multicollinear factors with a VIF of greater than 5: Age and Job

### Polynomial Regression
Degree of 2\
MSE = 4,757,599\
R^2= 0.505

### Random Forest Regression
MSE = 4,821,506\
R^2 = 0.498\
Used Grid search to find best hyperparameters with 10 -fold cv\
Max_depth = 20\
Max_features = log2\
Min_samples_leaf = 4\
Min_samples_split = 10\
N_estimators = 50

### Neural Network
<img width="460" alt="Screenshot 2024-03-12 at 00 23 05" src="https://github.com/Summeryuqing01/German_credit_risk/assets/56556388/977acb1b-8df8-4b45-a399-9bd1f44f60e4">


## Model Comparison
<img width="697" alt="Screenshot 2024-03-12 at 00 09 00" src="https://github.com/Summeryuqing01/German_credit_risk/assets/56556388/d0c32a04-cff1-4e8e-817b-059845c18cfe">

## References
https://cran.r-project.org/web/packages/missForest/missForest.pdf

## Data source
https://www.kaggle.com/datasets/uciml/german-credit/code

## Contributors
Ian Rector\
Summer Xia\
Jiahao Zhang
