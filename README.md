# Term Deposit Marketing

# Summary

## Context 

The objective of this project was to predict whether a customer would subscribe to a term deposit (variable y), and to identify customers who are more likely to purchase the investment product. The goal was to determine which segment(s) of customers our client should prioritize.

The dataset consisted of 40,000 rows and 14 features, including categorical (binary and non-binary) and numerical features (discrete and continuous). The dataset had no duplicate or missing values. Clients who did not subscribe to a term deposit represented 93% of the dataset, while clients who subscribed represented only 7%, making the dataset highly imbalanced. Among the entire dataset, 60% were married, 52% had reached secondary education, and 62% had cellular service.

The most common job types among customers who subscribed to term deposits were Blue_collar (1.3%), management (1.7%), and technician (1.2%). Subscribers to term deposits tended to be married (3.7%) and have cellular service (5.6%). Their education status was either secondary (3.5%) or tertiary (2.6%). Subscribers to term deposits tended to have no loan and no default credit, and the distribution of housing ownership was balanced between the two groups. Subscribers also tended to have experienced long-duration calls.

## Data preprocessing:

The first step in data preprocessing was to transform binary categorical columns with binary values (1, 0) and apply label encoding to non-binary categorical columns. The target variable and predictors were then obtained, and the dataset was divided into train and test sets.

## Modeling:

Modeling was divided into three parts. 

Modeling part one:

- Construct a baseline model with no feature engineering and no data augmentation. (model 0)
- Construct a baseline model with no feature engineering and data augmentation (smot)
- Get the features of importance

Modeling part two:

- Construct a baseline model where some columns were dropped (model 3)
- Construct a baseline model where some columns were dropped and apply data augmentation (smot 2)
- PCA in the pipeline of the random forest (has new features and data augmentation) (pipe)
- Construct a baseline model with feature engineering and no data augmentation (model 4)
- Construct a baseline model with feature engineering and data augmentation (smot 3)

Modeling part three:

- Random forest model tunning (has new features and applied smot ) using randomized grisearchCV one, two, three, and four
- Tuning hyperparameters by gradually increasing or decreasing hyperparams values (n_estimators max_features , max_depth , min_samples_split , min_samples_leaf , bootstrap) 

## Tracking Model evaluation and selection:

The best model among all the models was the random forest model tune 4, which had an accuracy of 95%. The features of importance were obtained, and the SHAP value of features of the 3 best models (random forest and XGBoost) was analyzed. The analysis showed that duration was the most important feature in all models, followed by month. Other important features included age, day, contact, housing, and balance. From the SHAP value plot, it was observed that the main features that had a great impact on model prediction were almost the same as the features of importance. Additionally, it was noted that default, loan, job, and marital status had less impact on model prediction.
