# Implementation-of-Decision-Tree-Classifier-Model-for-Predicting-Employee-Churn

## AIM:
To write a program to implement the Decision Tree Classifier Model for Predicting Employee Churn.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Import pandas module and import the required data set.

2.Find the null values and count them.

3.Count number of left values.

4.From sklearn import LabelEncoder to convert string values to numerical values.

5.From sklearn.model_selection import train_test_split.

6.Assign the train dataset and test dataset.
 
7.From sklearn.tree import DecisionTreeClassifier.

8.Use criteria as entropy.

9.From sklearn import metrics. 10.Find the accuracy of our model and predict the require values. 

## Program:
```
/*
Program to implement the Decision Tree Classifier Model for Predicting Employee Churn.
Developed by: Roop Sagar S L
RegisterNumber: 212223040175
*/
import pandas as pd
data=pd.read_csv("/content/Employee.csv")

data.head()

data.info()

data.isnull().sum()

data["left"].value_counts()

from sklearn.preprocessing import LabelEncoder
le=LabelEncoder()

data["salary"]=le.fit_transform(data["salary"])
data.head()

x=data[["satisfaction_level","last_evaluation","number_project","average_montly_hours","time_spend_company","Work_accident","promotion_last_5years","salary"]]
x.head()

y=data["left"]

from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test=train_test_split(x,y,test_size=0.2,random_state=100)

from sklearn.tree import DecisionTreeClassifier
dt=DecisionTreeClassifier(criterion="entropy")
dt.fit(x_train,y_train)
y_pred=dt.predict(x_test)

from sklearn import metrics
accuracy=metrics.accuracy_score(y_test,y_pred)
accuracy

dt.predict([[0.5,0.8,9,260,6,0,1,2]])

*/
```

## Output:
## data.head()

![data-head](https://github.com/user-attachments/assets/d00ec1c9-770d-4ff6-a72e-2b5734f8dd47)

## data.info()

![data-info](https://github.com/user-attachments/assets/1b4bb5c9-fb6b-4ba6-90d8-d7c1433522df)

## isnull() and sum ()

![isnull-and-sum](https://github.com/user-attachments/assets/a5cb9078-7bab-4c6c-8857-18a4705e70ea)

## data value counts()

![data-value-counts](https://github.com/user-attachments/assets/a5ee2380-b88d-40e6-829e-58c9d44f406e)

## data.head() for salary

![data-head-for-salary](https://github.com/user-attachments/assets/d3e49bf0-9a37-4552-be45-f3f1428f8d85)

## x.head()

![x-head](https://github.com/user-attachments/assets/9c47a7c5-5744-4c49-9f1d-bfb7d4270ebe)

## accuracy value

![accuracy-value](https://github.com/user-attachments/assets/1ba49a65-72a6-437a-9bfa-3e2b1cea6d83)

## data prediction

![data-prediction](https://github.com/user-attachments/assets/579ca4e7-3b2c-4c9b-9a1f-810a62b55e7d)

## Result:
Thus the program to implement the  Decision Tree Classifier Model for Predicting Employee Churn is written and verified using python programming.
