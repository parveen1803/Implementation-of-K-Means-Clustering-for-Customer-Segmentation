# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. Import the necessary packages using import statement.
2. Read the given csv file using read_csv() method and print the number of contents to be displayed using df.head().
3. Import KMeans and use for loop to cluster the data.
4. Predict the cluster and plot data graphs.
5. Print the outputs and end the program

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: Parveen Fathima M
RegisterNumber: 212219040103
*/
#import packages
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
## Dataset:
![dataset](https://user-images.githubusercontent.com/87666371/174471402-57235033-7b02-4deb-8b15-2a76e4ec8653.png)

## Dataset information:
![datainfo](https://user-images.githubusercontent.com/87666371/174471419-3a06cae3-bc26-49bc-b04c-70230b775676.png)

![datainfo2](https://user-images.githubusercontent.com/87666371/174471439-bc726e18-1650-4745-a42b-425a74be68ff.png)

## Elbow method graph (wcss vs each iteration):
![elbowgraph](https://user-images.githubusercontent.com/87666371/174471460-79df8d94-5aa3-4bb6-ac32-77782be1ea54.png)

## Cluster represnting customer segments-graph:
![cluster](https://user-images.githubusercontent.com/87666371/174471477-808d622f-f5ca-4f57-a417-2104f201b57f.png)


## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
