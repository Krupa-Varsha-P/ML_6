# Implementation-of-Decision-Tree-Classifier-Model-for-Predicting-Employee-Churn

## AIM:
To write a program to implement the Decision Tree Classifier Model for Predicting Employee Churn.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import dataset and print the dataset info
2. check for null value
3. Map numerical for salary feature
4. Asiign x and y values
5. Split as train data and test data
6. Import decision tree classifier and fit it in the dataset
7. Find accuracy and predict the values

## Program:
```txt
Program to implement the Decision Tree Classifier Model for Predicting Employee Churn.
Developed by: Krupa Varsha P
RegisterNumber:  212220220022
```
```python3
import pandas as pd
data=pd.read_csv('/content/Employee.csv')
data.head()
```
```python3
data.info
```
```python3
data.isnull().sum()
```
```python3
data["left"].value_counts()
```
```python3
from sklearn.preprocessing import LabelEncoder 
le=LabelEncoder() 
data["salary"]=le.fit_transform(data["salary"]) 
data.head()
```
```python3
x=data[["satisfaction_level","last_evaluation","number_project","average_montly_hours","time_sp
x.head()
```
```python3
y=data["left"] 
from sklearn.model_selection import train_test_split 
x_train,x_test,y_train,y_test=train_test_split(x,y,test_size=0.2,random_state=10) 
from sklearn.tree import DecisionTreeClassifier 
dt=DecisionTreeClassifier(criterion="entropy") 
dt.fit(x_train,y_train) 
y_pred=dt.predict(x_test)
```
```python3
from sklearn import metrics 
accuracy=metrics.accuracy_score(y_test,y_pred) 
accuracy
```
```python3
dt.predict([[0.5,0.8,9,260,6,0,1,2]])
```

## Output:
![b3a2b798-0050-48b8-85cf-9fdc1538ac0c](https://github.com/Krupa-Varsha-P/ML_6/assets/100466625/a13b715d-f4a3-4911-b79d-7e680948d29f)
![f9ff2af3-2b0a-4de9-bf9f-991ddf0f321b](https://github.com/Krupa-Varsha-P/ML_6/assets/100466625/07592527-3b1e-4f1b-bc62-f5cc7b7f98fa)
![06021659-b53b-44a9-99fc-24fbf15c866e](https://github.com/Krupa-Varsha-P/ML_6/assets/100466625/018e140e-aad4-4329-bd61-1b6757432f97)
![64c12100-11e4-4eac-949f-39238a9f6ee7](https://github.com/Krupa-Varsha-P/ML_6/assets/100466625/0a70c0fe-341b-4fee-b1cb-ce29870b2d02)
![97d1041a-9298-4de8-a7f2-fd7918b5fa04](https://github.com/Krupa-Varsha-P/ML_6/assets/100466625/8efe6661-5813-4136-b621-574eb1cce62c)
![663df356-2d19-4aca-b368-6c302e009625](https://github.com/Krupa-Varsha-P/ML_6/assets/100466625/5e42f359-d771-41dd-b985-78b8b6c9af74)


## Result:
Thus the program to implement the  Decision Tree Classifier Model for Predicting Employee Churn is written and verified using python programming.
