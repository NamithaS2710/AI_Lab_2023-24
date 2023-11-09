# Ex.No: 13 Learning – Use Supervised Learning  
### DATE: 28.10.2023                                                                           
### REGISTER NUMBER : 212221040110
### AIM: 
To write a program to train the classifier for Predicting the Placement Status of Students.
### Program:
```
import pandas as pd
data=pd.read_csv('/content/Placement_Data (1).csv')
print("Placement data")
data.head()
data1=data.copy()
data1=data1.drop(["sl_no","salary"],axis=1)
print("Salary data")
data1.head()
print("Checking the null() function")
data1.isnull().sum()
print("Data Duplicate")
data1.duplicated().sum()
from sklearn.preprocessing import LabelEncoder
le=LabelEncoder()
data1["gender"]=le.fit_transform(data1["gender"])
data1["ssc_b"]=le.fit_transform(data1["ssc_b"])
data1["hsc_b"]=le.fit_transform(data1["hsc_b"])
data1["hsc_s"]=le.fit_transform(data1["hsc_s"])
data1["degree_t"]=le.fit_transform(data1["degree_t"])
data1["workex"]=le.fit_transform(data1["workex"])
data1["specialisation"]=le.fit_transform(data1["specialisation"])
data1["status"]=le.fit_transform(data1["status"])
print("Print data")
data1
x=data1.iloc[:,:-1]
print("Data-status")
x
y=data1["status"]
print("data-status")
y
from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test=train_test_split(x,y,test_size=0.2,random_state=0)
from sklearn.linear_model import LogisticRegression
lr=LogisticRegression(solver="liblinear")
lr.fit(x_train,y_train)
y_pred=lr.predict(x_test)
print("y_prediction array")
y_pred
from sklearn.metrics import accuracy_score
accuracy=accuracy_score(y_test,y_pred)
print("Accuracy value")
accuracy
from sklearn.metrics import confusion_matrix
confusion = confusion_matrix(y_test,y_pred)
print("Confusion array")
confusion
from sklearn.metrics import classification_report
classification_report1 = classification_report(y_test,y_pred)
print("Classification report")
print(classification_report1)
print("Prediction of LR")
lr.predict([[1,80,1,90,1,1,90,1,0,85,1,85]])
```

### Output:
1. Placement data
2. Salary data
![image](https://github.com/NamithaS2710/AI_Lab_2023-24/assets/133190822/aee596bc-82c6-40c5-b746-3828d3e44665)
![image](https://github.com/NamithaS2710/AI_Lab_2023-24/assets/133190822/37899f2a-18d9-41ef-97b7-206bbf5481ee)
3. Checking the null function()
![image](https://github.com/NamithaS2710/AI_Lab_2023-24/assets/133190822/b9eb5722-8aa4-4f3c-b486-905ce266fe7f)
4. Data duplicate
5. Print data
![image](https://github.com/NamithaS2710/AI_Lab_2023-24/assets/133190822/ec6dce26-4a0a-417f-a542-a37e3fc84555)
6. Data status
![image](https://github.com/NamithaS2710/AI_Lab_2023-24/assets/133190822/666d1431-2461-4cde-b9f3-ff88c35d30ad)
![image](https://github.com/NamithaS2710/AI_Lab_2023-24/assets/133190822/5e7250aa-99d7-4f6b-922c-dd43413662c9)
7. y_prediction array
![image](https://github.com/NamithaS2710/AI_Lab_2023-24/assets/133190822/d25badcd-490f-40cf-bce2-eedc29e9554e)
8. Accuracy value
![image](https://github.com/NamithaS2710/AI_Lab_2023-24/assets/133190822/9fbf6340-06eb-4927-bf99-5b37ff825495)
9. Confusion matrix
![image](https://github.com/NamithaS2710/AI_Lab_2023-24/assets/133190822/fa0e4dbc-c565-49e8-9ff0-55e187803542)
10. Classification report
11. Prediction of LR
![image](https://github.com/NamithaS2710/AI_Lab_2023-24/assets/133190822/a8415478-5fe3-4b73-a985-bb4bdaaa5f3b)

### Result:
Thus the system was trained successfully and the prediction was carried out.
