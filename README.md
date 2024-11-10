# Implementation-of-SVM-For-Spam-Mail-Detection

## AIM:
To write a program to implement the SVM For Spam Mail Detection.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Import the necessary python packages using import statements.

2.Read the given csv file using read_csv() method and print the number of contents to be displayed using df.head().

3.Split the dataset using train_test_split.

4.Calculate Y_Pred and accuracy.

5.Print all the outputs.

6.End the Program.


## Program:
```
/*
Program to implement the SVM For Spam Mail Detection..
Developed by: Mohamed Anas O.I
RegisterNumber:  212223110028
*/
import chardet
file='spam.csv'
with open (file,'rb') as rawdata:
    result = chardet.detect(rawdata.read(100000))
result

import pandas as pd
data=pd.read_csv("spam.csv",encoding='windows-1252')

data.head()
```

### Output:
![Screenshot 2024-11-10 204636](https://github.com/user-attachments/assets/6d6885a2-b800-462a-a2d6-0bea7d41181e)



```
data.info()
```

### Output:
![Screenshot 2024-11-10 204641](https://github.com/user-attachments/assets/4d03a33f-2e74-478c-8b20-f989c5c3fed8)


```
data.isnull().sum()
```

### Output:
![Screenshot 2024-11-10 204647](https://github.com/user-attachments/assets/2cdd6808-c502-47bc-a75c-88ea7226a892)

```
x=data["v1"].values
y=data["v2"].values

from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test=train_test_split(x,y,test_size=0.2,random_state=0)

from sklearn.feature_extraction.text import CountVectorizer
cv=CountVectorizer()
x_train=cv.fit_transform(x_train)
x_test=cv.transform(x_test)

from sklearn.svm import SVC
svc=SVC()
svc.fit(x_train,y_train)
y_pred=svc.predict(x_test)
y_pred

from sklearn import metrics
accuracy=metrics.accuracy_score(y_test,y_pred)
accuracy
```

### Output:
![Screenshot 2024-11-10 204652](https://github.com/user-attachments/assets/a0151f6b-1af2-448f-bb37-15b8480d1871)


## Result:
Thus the program to implement the SVM For Spam Mail Detection is written and verified using python programming.
