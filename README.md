# Implementation-of-Linear-Regression-Using-Gradient-Descent

## AIM:
To write a program to predict the profit of a city using the linear regression model with gradient descent.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
step 1.Import the required library and read the dataframe.

step 2.Write a function computeCost to generate the cost function.

step 3.Perform iterations og gradient steps with learning rate.

step 4.Plot the Cost function using Gradient Descent and generate the required graph.

## Program:

/*
Program to implement the linear regression using gradient descent.

Developed by: PREM R

RegisterNumber: 212223240124
*/
```
import pandas as pd
import numpy as np
from sklearn.preprocessing import StandardScaler
def linear_regression(X1,y,learning_rate=0.1,num_iters=1000):
    X=np.c_[np.ones(len(X1)),X1]
    theta= np.zeros(X.shape[1]).reshape(-1,1)
    for _ in range(num_iters):
        predicitions= (X).dot(theta).reshape(-1,1)
        errors=(predicitions-y).reshape(-1,1)
        theta-= learning_rate*(1/len(X1))*X.T.dot(errors)
    return theta
data = pd.read_csv("C:/Users/admin/OneDrive/Desktop/50_Startups.csv")
print (data.head())
X=(data.iloc[1:,:-2].values)
X1= X.astype(float)
s= StandardScaler()
y=(data.iloc[1:,-1].values).reshape(-1,1)
X1_scaled= s.fit_transform(X1)
y1_scaled= s.fit_transform(y)
print(X)
print(X1_scaled)
print(y1_scaled)
theta=linear_regression(X1_scaled,y1_scaled)
new_Data= np.array([165349.2,136897.8,471784.1]).reshape(-1,1)
new_scaled= s.fit_transform(new_Data)
predicition= np.dot(np.append(1,new_scaled),theta)
predicition= predicition.reshape(-1,1)
pre= s.inverse_transform(predicition)
print(predicition)
print(f"Predicited value: {pre}")
```

## Output:
![image](https://github.com/user-attachments/assets/81f36e27-259a-4917-ad10-b14d5170bcdb)



## Result:
Thus the program to implement the linear regression using gradient descent is written and verified using python programming.
