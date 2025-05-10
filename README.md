# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Import dataset and print head,info of the dataset  
2.check for null values   
3.Import kmeans and fit it to the dataset    
4.Plot the graph using elbow method    
5.Print the predicted array    
6.Plot the customer segments    

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by:Srikaran M
RegisterNumber:  212223040206
*/
```
```python

import pandas as pd

import matplotlib.pyplot as plt

data=pd.read_csv("/content/Mall_Customers (1).csv")

data.head()

data.info()

data.isnull().sum()

from sklearn.cluster import KMeans

wcss=[]

for i in range(1,11):

kmeans=KMeans(n_clusters=i,init="k-means++")

kmeans.fit(data.iloc[:,3:])

wcss.append(kmeans.inertia_)

plt.plot(range(1,11),wcss)

plt.xlabel("No_of_Clusters")

plt.ylabel("wcss")

plt.title("Elbow Method")

km=KMeans(n_clusters=5)

km.fit(data.iloc[:,3:])

y_pred=km.predict(data.iloc[:,3:])

y_pred

data["cluster"]=y_pred

df0=data[data["cluster"]==0]

df1=data[data["cluster"]==1]

df2=data[data["cluster"]==2]

df3=data[data["cluster"]==3]

df4=data[data["cluster"]==4]

plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")

plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="black",label="cluster1")

plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="blue",label="cluster2")

plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster3")

plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="magenta",label="cluster4")

plt.legend()

plt.title("Customer Segment")
```
## Output:
### 1.DATA.HEAD():
![image](https://github.com/user-attachments/assets/12ec6b6a-8a0f-4426-88b3-136cb6a45c9c)


### 2.DATA.INF0():
![image](https://github.com/user-attachments/assets/58ac8003-aad7-4f6f-a86a-16b9a7dedea0)


### 3.DATA.ISNULL().SUM():

![image](https://github.com/user-attachments/assets/54987a16-1683-444b-9de6-50994bcdadb3)


### 4.PLOT USING ELBOW METHOD:
![image](https://github.com/user-attachments/assets/9104e251-6620-40bf-9345-a6b8f166ff0f)


### 5.K-MEANS CLUSTERING:
![image](https://github.com/user-attachments/assets/ea694b28-4ad9-4e3b-bf80-e18d7d3f8cc7)

### 6.Y_PRED ARRAY:
![image](https://github.com/user-attachments/assets/e073cd89-51e8-4ba6-8d3b-65875c7e02bc)






### 7.CUSTOMER SEGMENT:

![image](https://github.com/user-attachments/assets/7bacf9f0-5228-4336-b7da-b75e3465639a)




## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
