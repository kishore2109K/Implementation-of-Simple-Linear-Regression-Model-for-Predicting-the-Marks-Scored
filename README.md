# Implementation-of-Simple-Linear-Regression-Model-for-Predicting-the-Marks-Scored

## AIM:
To write a program to predict the marks scored by a student using the simple linear regression model.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Import the standard Libraries.
2.Set variables for assigning dataset values.
3.Import linear regression from sklearn.
4.Assign the points for representing in the graph.
5.Predict the regression for marks by using the representation of the graph.
6.Compare the graphs and hence we obtained the linear regression for the given datas. 

## Program:
```
Program to implement the simple linear regression model for predicting the marks scored.
Developed by: KISHORE K
RegisterNumber: 212223040101  
```
## obtaining x and y value from csv file
```
df=pd.read_csv(r"student_scores.csv")
print(df.head())
print(df.tail())
x=df.iloc[:,:-1].values
y=df.iloc[:,1].values
print("x values:",x)
print("y values:",y)
```
## spliting dataset for testing and training
```
from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test=train_test_split(x,y,test_size=1/3,random_state=0)
```
## training the model by linear regression
```
from sklearn.linear_model import LinearRegression
regressor=LinearRegression()
regressor.fit(x_train,y_train)

y_pred=regressor.predict(x_test)

print("Y Prediction:",y_pred)
print("Actual Value:",y_test)
plt.scatter(x_train,y_train,color="black")
plt.plot(x_train,regressor.predict(x_train),color="brown")
plt.title("Hours vs Score (Training Set)")
plt.xlabel("Hours")
plt.ylabel("Scores")
plt.show()

plt.scatter(x_test,y_test,color="red")
plt.plot(x_test,regressor.predict(x_test),color="blue")
plt.title("House vs Score (Test Set)")
plt.xlabel("Hours")
plt.ylabel("Scores")
plt.show()
```
#measuring the error percentage for the model
```
mse=mean_squared_error(y_test,y_pred)
print("MSE =",mse)
mae=mean_absolute_error(y_test,y_pred)
print("MAE =",mae)
rmse=np.sqrt(mse)
print("RMSE =",rmse)
```
## Output:
## head and tail values
![image](https://github.com/user-attachments/assets/4efc40c6-ce92-44e1-b3ed-3403d35f1b20)
## x and y values
![image](https://github.com/user-attachments/assets/05496c12-ceb7-4826-b439-6897a0ecd308)
## prediction values
![image](https://github.com/user-attachments/assets/b20b88d1-5026-472f-88b0-36e50e70a47f)
## mse,mae,mrse
![image](https://github.com/user-attachments/assets/e0adc750-d262-4b09-948e-3a6e30e9a2ad)
## training set
![image](https://github.com/user-attachments/assets/f8e6fdc9-ca1d-4b74-aeb2-162e131ec757)
![image](https://github.com/user-attachments/assets/271e2f8b-5662-4c8a-9d24-64f5c1454314)



## Result:
Thus the program to implement the simple linear regression model for predicting the marks scored is written and verified using python programming.
