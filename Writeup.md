# Churn Prediction 2020
Calvin Yu
## Abstract 
The goal of this project is to predict whether a customer will change telecommunication provdier ,also known as "churning". The dataset I used contains 5000 rows with 4250 rows as training, and 750 rows as testing. The dataset contains categorical and numeric columns. I first did a Exploratory Data Analysis to comprehend each column from the dataset. Then , I used multiple maching learning algorithms including Logistic Regression, KNeighbors Classifer,Decision Tree Classifer, Random Forest Classifer, and gradient boost/ XGB Classifer to train the dataset. I used F1 score, and accuracy to determine the performance of each algorithm, and choose the best one to predict the results for the testing set. 
## Design
A telecom company puts thousands of money on a direct marketing campaign to keep its customers loyal. However, the board members of the company want to know what factors should the company focuses on when making the marketing campaign. So , my job is to explain what factors are causing churn, and create a model to predict who will be churning. 
## Data
### Customer Churn Prediction 2020
- Training: 4250 rows with 20 columns including 1 target variable 
- Testing : 750 rows with 20 columns same as training 
- feature highlights : account length (Number of months the customer has been with the current telco provider),total day minute (Total minutes of calls per daytime),international plan, voice mail plan 
## Algorithms
1. Use pandas to read the csv files and check for missing values 
2. Do a Exploratory Data Analysis on the training set to evaluate the features
3. Use heatmap to find the correlation between each feature and eliminating the features that are similar to the others to avoid multicolinarity 
4. Turn the categorical columns into dummy variables 
5. Split the training dataset into training, validation, and testing (60,20,20)
6. Create a function called make_confusion_matrix and this function will give us the confusion matrix of the how many correct predictions are made by using the input model, and will also gives us the recall,precision,f1score, roc_auc score , and accuracy score of the model 
7. Create a function called optimal_threshold which takes the model and evaluate the best threshold for the model 
8. Fitting the training set into different algorithms, since the target variable is inbalanced, I tuned the class_weights into balanced 
9. Compare the f1 score and accuracy of each model and find out the best model is XGBoost with 0.73 average f1 score and 0.94 average accuracy score
<img width="469" alt="Screen Shot 2022-09-13 at 6 26 18 PM" src="https://user-images.githubusercontent.com/63031028/190038000-30a5d1a3-d238-4c2f-8265-8aa1c3d23456.png">
tent.com/63031028/190037869-bf0e443d-6f66-4a84-9fc5-5da9ad1f22b0.png)

10. Use optimal threshold function to find the best threshold for XGBoost
11. Use XGBoost to fit the whole training dataset, get the top 10 feature importances 


12. Use Xgboost model to predict for the testing set and the accuracy score of the model is 0.98
<img width="765" alt="Screen Shot 2022-09-13 at 6 11 24 PM" src="https://user-images.githubusercontent.com/63031028/190036477-3309e2b6-d48d-46b5-a1e6-8e8efb07b61e.png">

## Tools
- Pandas, Numpy - Exploratory Data Analysis 
- Matplotlib, Seaborn, Plotly - Data visualization
- Scikit learn , XGboost - Machine learning algorithms , and performance metrics 
## Communication 
<img width="600" alt="Screen Shot 2022-09-13 at 6 08 53 PM" src="https://user-images.githubusercontent.com/63031028/190036244-9e63b607-5442-47e3-aa5e-c61d120dcba3.png">
The feature importances diagram shows us the total minutes of calls per day including daytime, evening , and night time is really important. So the telecom company should do promotion on giving out free minutes of calls to attract new customers. Also, account length is important , so the telecom company can give out some rewards for customer who have been subscribed for a certain amount of time to keep up the customer loyalty.

## Future steps
1. Create marketing campaign with the slogan of giving out free minutes to attract new customers 
2. Reward the customers who have been subscribed for a long period
3. Coldcall the customers who have churned to understand the reasons of churning