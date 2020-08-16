## Introduction
This is my **first** Kaggle challenge! The legendary Titanic ML competition is perfect for those who are getting started in the ML field. The challenge is to use machine learning to create a model that predicts which passengers survived the Titanic shipwreck from the given data set.
## The challenge
> The sinking of the Titanic is one of the most infamous shipwrecks in history.
>
> On April 15, 1912, during her maiden voyage, the widely considered “unsinkable” RMS Titanic sank after colliding with an iceberg. Unfortunately, there weren’t enough lifeboats for everyone onboard, resulting in the death of 1502 out of 2224 passengers and crew.
>
> While there was some element of luck involved in surviving, it seems some groups of people were more likely to survive than others.
>
> In this challenge, we ask you to build a predictive model that answers the question: “what sorts of people were more likely to survive?” using passenger data (ie name, age, gender, socio-economic class, etc).



## Data Set
The data set consists of two .csv files: train.csv and test.csv. The training set has 891 passengers and the testing set has 418 passengers. The attributes are:
* PassengerId
* Pclass
* Name
* Sex
* Age
* SibSp
* Parch
* Ticket
* Fare

The target value is to predict whether the passenger survived that shipwreck. Since this is a binary classification problem, **0** means the passenger did **not survived** and **1** means the passenger did **survived**. 

The data set can be found [here](https://www.kaggle.com/c/titanic/data). 

## Content
### 1. Data exploration
- Identify the missing values 
- Use distribution plots to visualize the correlation between certain attributes (age, sex, Pclass, alone/not alone) and the outcome of survival
### 2. Data cleaning and feature engineering
- Drop "PassengerId" since it does not help in the prediction
- Drop "Ticket" since there are too many unique values
- Combine "SibSp" and "Parch" - identify whether the passenger boarded the ship alone
- Transform "Cabin" into "Deck" - classify using the Cabin letters (e.g. Cabin "C123" corresponds to Deck "C")
- Map each deck into a numeric value
- Fill in the missing values in "Age" using the mean and standard deviation calculated from the known population
- Create age groups and fare groups map them into numeric values
- Fill in the 2 missing values in "Embarked" using the highest occurrence value and map the field into numeric values
- Map the "Sex" field into numeric values
### 3. Evaluation of different models
- Stochastic gradient descent
- Random forest
- Logistic regression
- K-nearest neighbours
- Gaussian Naive Bayes
- Linear SVM
- Decision tree
- Perceptron  

Random forest performed the best. 
### 4. Hyperparameter tuning
- Plot the importance of each feature contributing the to model training
- Drop the non-important features (not_alone and Parch)
- Identify the available parameters for tuning 
- Tune the hyperparameters of Random Forest using RandomizedSearchCV for an approximate region of search. Then use GridSearchCV for a finer degree of search. 
### 5. Confusion matrix, precision, recall, ROC-AUC score
- The confusion matrix shows the number of True Positives (TP), True Negatives (TN), False Positives (FP) and False Negatives (FN)
- FP is aka Type 1 error, FN is aka Type 2 error
- Precision = TP/(TP+FP)
- Recall = TP/(TP+FN)
- The ROC-AUC curve should be as far as possible away from the purely random classifier line

## Libraries
1. Numpy
2. Pandas
3. Seaborn
4. Matplotlib
5. sklearn
6. re
