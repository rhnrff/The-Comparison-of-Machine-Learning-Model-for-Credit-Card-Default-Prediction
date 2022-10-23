# The-Comparison-of-Machine-Learning-Model-for-Credit-Card-Default-Prediction
## Introduction
The use of credit cards today is increasingly prevalent. The convenience provided in transacting using a credit card makes more and more people use it. Credit cards basically allow users to transact using credit from banks within a certain period and limit. The limit is determined by the bank based on the bank's estimate of the user's ability to pay credit bills within that period. Generally, the credit card term used is at the end of each month. However, if the user does not make a payment by the specified deadline, the bank will apply a penalty in the form of additional fees or fines. Based on economic data from the Federal Reserve, credit card arrears have increased sharply since 2016. However, in 2020, they experienced a sharp decline. This was also due to a charge-off policy by banks due to the COVID-19 pandemic situation that has recently hit the world. Of course, this causes huge losses for the bank that has provided credit card services for its users who have arrears in repayment. This risk can actually be minimized if the bank can predict the level of possibility of failing to pay. If this can be done, the bank certainly has more options to cope with large losses that occur due to payment failures or arrears due to credit cards by providing other options for credit card users.

The existence of machine learning has greatly helped many needs in various fields. Especially in policy determinations that leverage predictions made by machine learning models generated from pre-owned data sets. There are many machine learning models that can be utilized, such as logistic regression, support vector machine (SVM), k-nearest neighbors, and Naive Bayes. In addition, there are also tree-based models and ensemble learning such as decision trees, random forests, and extreme gradient boosting (xg-boost). These models can be used to predict which credit card users are likely to default and which credit card users are not. Then the performance of these models can also be compared by evaluating the model and then determining which hyperparameter has a value to produce the best model.

## Objective
1. Create a machine learning logistic regression model, support vector machine (svm), decision trees model, random forests model, k-nearest neighbors (knn) model, naive bayes model, and gradient boosting model to predict default users on credit cards.
2. Compare machine learning models built to predict user defaults on credit cards and determine the best model.
3. Perform hyperparameter tuning for the best prediction model.

## Exploratory Analysis
1. Default Payment

![My Image](../The-Comparison-of-Machine-Learning-Model-for-Credit-Card-Default-Prediction/image/1.png)

2330 of the total 2965 or 78.58% of the data population were identified as non-default credit card users, while 635 or 21.42% were identified as default credit card users. The data is very unbalanced between the default note users and the default data. Actually, this is very reasonable when viewed from the real world where most people will always pay their credit cards on time. Meanwhile, for people who have credit card payment arrears the number of defaults will not be much. Of course, this is a general assumption that the world is not in a state of economic crisis.

2. Gender Data Distribution

![My Image](../The-Comparison-of-Machine-Learning-Model-for-Credit-Card-Default-Prediction/image/2.png)

![My Image](../The-Comparison-of-Machine-Learning-Model-for-Credit-Card-Default-Prediction/image/3.png)

It can be seen that the distribution of data by gender is also not balanced. However, the difference is not as far as the data class difference in the default status column. When viewed in each default class, 58.7% of the total population of credit card users who defaulted were women, while the remaining 41.3% were men. While in the non-default class, 61.3% are female credit card users, while the remaining 38.7% are male. This makes the default assessment of users on this credit card data cannot directly related to the gender of the user. Although the default class is dominated by female users, the not default class is also dominated by female users. The conclusion that can be drawn from the simple visualization above is that regardless of the user's default status, credit cards are mostly used by women because basically, it is generally known that women do more shopping activities than men.

3. Education Level

![My Image](../The-Comparison-of-Machine-Learning-Model-for-Credit-Card-Default-Prediction/image/4.png)

The credit card users contained in the data are divided into four classes based on the level of education, namely graduate school, university, high school, and others. In general, if you look at the distribution of data on the graph, credit card users with university education status have the highest default status compared to users with other educational statuses. In addition, it can also be seen that there is no correlation between the education level of credit card user and their probability of default. However, when viewed more closely, the population of credit card users with university education status is the largest number of users. The assumption that can be taken here is that the tendency of someone to use a credit card is directly proportional to their level of education. But not so with the default state that can happen to them. This is because, in the available data, the population of users with university education status is the largest. So it cannot be concluded that the level of education is correlated with the possibility of users experiencing default.

4. Marital Status

![My Image](../The-Comparison-of-Machine-Learning-Model-for-Credit-Card-Default-Prediction/image/5.png)

In general, the number of credit card users with married and single statuses is quite balanced. Even when viewed from the default status or not, the two classes are also quite balanced.

5. Age Distribution

![My Image](../The-Comparison-of-Machine-Learning-Model-for-Credit-Card-Default-Prediction/image/6.png)

Most credit card users are in the age group of 24 years to 32 years. In general, the number of credit card users decreases as users age. When viewed from the default status, it can be seen that users who default and do not default based on age have a fairly similar pattern.

6. Age Vs. Marriage

![My Image](../The-Comparison-of-Machine-Learning-Model-for-Credit-Card-Default-Prediction/image/7.png)

If you look at the marital status with the user's age and gender, it can be seen that the average married credit card users are between the ages of 30 and 50 years. Meanwhile, users who are not married or still single are an average age of 20 years to 35 years. There is another class on marital status. When viewed from the age distribution, it can be assumed that this other class contains users with the status of having been married but already widowed or widowed because the age distribution is in the average range of 30 years to 55 years.

7. Limit Balance

![My Image](../The-Comparison-of-Machine-Learning-Model-for-Credit-Card-Default-Prediction/image/8.png)

The distribution pattern of credit limit data is also almost the same as age, where users with a higher number of limits have a smaller population. When viewed from the default status or not, it can be concluded that the smaller the credit limit owned by the user, the higher the possibility for them to experience default. In general, banks will apply a credit card usage limit for each user based on the bank's estimate of each user's ability to make payments. Therefore, users with high credit limits can be assumed to be users who have high monthly income, so their chances of experiencing default should be smaller.

8. Repayment Status

![My Image](../The-Comparison-of-Machine-Learning-Model-for-Credit-Card-Default-Prediction/image/9.png)

Repayment status is the user's monthly credit card payment status. It can be seen that in April 2005 (pay_6), users with 4 months arrears were the most users. Meanwhile, in May 2005 (pay_5), users with 5 and 6 months arrears status both increased. Then in June 2005 (pay_4) and July 2005 (pay_3), users with 5, 6, and 7 months arrears status experienced an increase. The number of users with 8 months arrears status began to appear in September 2005 (pay_1). In addition, it can be seen that the number of users with no arrears status each month did not experience significant changes and tended to stagnate. Users with a 1-month arrears status in September 2005 (pay_1) experienced a considerable increase and users with no arrears status slightly decreased. This can be interpreted that in September users with no arrears status began to decrease and make payments in arrears. This can be seen clearly because previously in August 2005 (pay_2), the number of users with 1-month arrears was very small or almost non-existent.

9. Amount of Bill Statement

![My Image](../The-Comparison-of-Machine-Learning-Model-for-Credit-Card-Default-Prediction/image/10.png)

The billing statement is the amount of the bill that must be paid by the credit card used by the bank. In general, it can be seen that the number of bills each month does not change significantly and tends to be the same. However, in July a bill appeared between 450,000 and s.d. 615,000 USD means that in the middle of 2005 the use of credit cards increased in intensity so that the number of bills from users' shopping activities also increases.

10. Amount of Previous Payment

![My Image](../The-Comparison-of-Machine-Learning-Model-for-Credit-Card-Default-Prediction/image/11.png)

Previous payment is the amount of payment made by the user based on the bill that the brand has. It can be seen that the nominal payment has increased from April to April. June 2005 (prepr_6, prepr_5, and prepr_4). Meanwhile, in July, August, and September 2005 (prepr_3, prepr_2, and prepr_1) there was no significant pattern depicted.

## Model Summary and Overall Analysis
![My Image](../The-Comparison-of-Machine-Learning-Model-for-Credit-Card-Default-Prediction/image/12.png)

Based on the results of the correlation carried out on numerical data, credit limit and age have a higher correlation value than other numerical features. So it was decided to eliminate the billing statement and previous payment features from the training data and only use credit limit and age data. Based on the results of hypothesis testing using chi-square on the training data for the above categories, all category features have a relationship with the target data so that they will be used in the modeling process. The two numerical data that will be used to build the classification model have a moderate right skew with a skew value for the credit limit feature of 0.956 and a skew value of 0.774 for the age feature. It was decided that outliers handling would be carried out by censoring the data using windsorizer method. The selection of censoring is done because the amount of data used is very small so if the treatment given is the removal of outliers, it is feared that the data will decrease and affect the performance of the classification model later. There are no missing values for bank credit card users data.

The use of cross-validation is done to see the consistency of the model made. The input data used to create the model is unbalanced data so the value used in the cross-validation is the recall value. The model will have better performance if the recall value is closer to 1.0. This of course cannot be separated from the influence of the imbalance of the target data used. In general, the accuracy value obtained is quite good. However, considering that the input data used is unbalanced data, the accuracy value is considered biased. So it cannot be used as a consideration for the performance of the model made. There was overfitting in the model decision tree and random forests. The accuracy value indicates that the model created is overfitting the training model, but cannot generalize the testing data being tested so the testing model gets a low score and is very unequal to the training model. There was also a misclassification that occurs in the default data. The misclassification is very high in number so the accuracy of the testing model is low. The overfitting that occurs in the random forests model is not as bad as the decision tree model because the random forest model which is a tree-based model has a better decision-making method because the number of branches formed is much more than the decision tree.  As discussed earlier, the performance of the machine learning classification model, in general, can be seen from the results of the accuracy scores of the training model and the testing model. However, there is a condition where the two values ​​are biased. This condition is a condition where the target data used is data that is not balanced between data labels. Cross-validation has been carried out using the recall scores of each model to see its consistency. This recall value will be considered to represent the model's performance in identifying labels that match ground truth or positive true. The recall value is considered to be getting better as it approaches 1.0. Determination of the best model carried out in this modeling using imbalanced data is done by comparing the best recall values ​​between models. The Naive Bayes model has the best recall score among all models with a recall value of 0.45 on the training model and 0.52 on the testing model. Then after determining the model with the best performance, the modeling will be carried out again, but by using hyperparameter tuning to improve the performance of the model. The hyperparameter tuning method used this time is grid search hyperparameter tuning. The selection of this method is based on the number of features used. If the number of features used is quite large, then grid search is a more reliable method to use. The tuning hyperparameter in the Naive Bayes model can be applied to the var_smoothing parameter. var_smoothing is a portion of the largest variance of all features that are added to variances for stability calculation. After tuning the accuracy value based on cross-validation, it gets a value of 0.84. In general, the performance of the model is slightly improved. When viewed in the confusion matrix, there are 442 data that do not default credit card user data identified according to their original condition. Then there are 68 non-default credit card user data identified as default users. Then there are 45 default credit card user data that were identified according to their original condition, while the other 28 default data were misclassified and identified as not default data. In general, misclassification of models that have been hyperparameter tuned has decreased. Prediction of the inference data is done using the results of the best hyperparameter tuning model, namely naive bayes grid search cross-validation. The results of the accuracy of the Naive Bayes searchCV grid resulted in a test model accuracy of 0.84, an increase of 0.02 from the model before hyperparameter tuning. Then from the prediction results on the inference data, in general, the results are quite good although there are still some misclassifications.