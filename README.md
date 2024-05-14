# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1..Import the necessary packages using import statement.

2.Read the given csv file using read_csv() method and print the number of contents to be displayed using df.head().

3.Import KMeans and use for loop to cluster the data.

4.Predict the cluster and plot data graphs.

5.Print the outputs and end the program 
 

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: gajalakshmi V
RegisterNumber: 212223040047 
*/
import pandas as pd
import matplotlib.pyplot as plt
data=pd.read_csv("Mall_Customers.csv")
data.head()
data.info()
data.isnull().sum()
from sklearn.cluster import KMeans
wcss = []
for i in range(1,11):
  kmeans = KMeans (n_clusters = i, init ="k-means++")
  kmeans.fit(data.iloc[:,3:])
  wcss.append(kmeans.inertia_)
plt.plot(range(1,11),wcss)
plt.xlabel("no of cluster")
plt.ylabel("wcss")
plt.title("Elbow Metthod")
km=KMeans(n_clusters=5)
km.fit(data.iloc[:,3:])
y_pred = km.predict(data.iloc[:,3:])
y_pred
data["cluster"]=y_pred
df0=data[data["cluster"]==0]
df1=data[data["cluster"]==1]
df2=data[data["cluster"]==2]
df3=data[data["cluster"]==3]
df4=data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="pink",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="green",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="blue",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="black",label="cluster4")
plt.legend()
plt.title("Customer Segments")

```

## Output:

![329870706-c1163120-5ce3-4359-b888-87d58a7000b2](https://github.com/Gajalakshmivelmurugan/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/144871940/92905b2a-53da-4bfc-9897-bb62822840f5)

Dataset information:

![329870721-6e62973a-3e8b-42cc-90e8-eb3f77d8ec79](https://github.com/Gajalakshmivelmurugan/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/144871940/d4cbaf2d-0854-4a17-a2d2-352eacfb6856)

![329870735-ecee6adb-a2b4-49e8-86ba-15db557d3093](https://github.com/Gajalakshmivelmurugan/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/144871940/96f0a52c-9168-4d49-8daa-b3631edec921)


Elbow method graph (wcss vs each iteration):

![329870780-d94b79f7-aa3f-40e6-8b2b-c3c73c9ee82d](https://github.com/Gajalakshmivelmurugan/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/144871940/d4e4e2f7-7ed3-4987-8948-c05702a56da4)

Cluster represnting customer segments-graph:

![329870810-c5ffd0ee-f1d1-4fb1-8793-203fe2a6ffb1](https://github.com/Gajalakshmivelmurugan/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/144871940/596b409d-1033-42a5-b608-b225cde15c96)

## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
