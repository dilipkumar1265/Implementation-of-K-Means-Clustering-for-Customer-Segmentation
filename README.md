# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import standard libraries in python for finding Implementation-of-K-Means-Clustering-for-Customer-Segmentation.
2. Initialize and print the Data.head(),data.info(),data.isnull().sum()
3. Import sklearn.cluster import KMeans
4. calculate the value of KMeans Clusters.
5. plot the graph from Elbow method and find y_pred values .
6. plot the graph from Customer Segments Graph. 

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: DILIP KUMAR R
RegisterNumber: 212222040037
*/
import pandas as pd
import matplotlib.pyplot as plt
data = pd.read_csv("/content/Mall_Customers (1).csv")
print("data.head():")
data.head()
print("data.info():")
data.info()
print("data.isnull().sum():")
data.isnull().sum()
from sklearn.cluster import KMeans
wcss = []
for i in range (1,11):
    kmeans = KMeans(n_clusters = i,init = "k-means++")
    kmeans.fit(data.iloc[:,3:])
    wcss.append(kmeans.inertia_)
print("Elbow Method Graph:")
plt.plot(range(1,11),wcss)
plt.xlabel("No. of Clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")

print("KMeans cluster value:")
km = KMeans(n_clusters = 5)
km.fit(data.iloc[:,3:])

print("y_pred:")
y_pred = km.predict(data.iloc[:,3:])
y_pred

print("Customer Segments Graph:")
data["cluster"] = y_pred
df0=data[data["cluster"]==0]
df1=data[data["cluster"]==1]
df2=data[data["cluster"]==2]
df3=data[data["cluster"]==3]
df4=data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="black",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="blue",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="yellow",label="cluster4")
plt.legend()
plt.title("Customer Segments")
```

## Output:
## data.head()
![Screenshot 2023-11-11 164112](https://github.com/dilipkumar1265/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119065291/9e4d77bc-f769-456a-8c67-a7c7118ac595)
## data.info()
![Screenshot 2023-11-11 164141](https://github.com/dilipkumar1265/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119065291/0668e4aa-6211-43b0-a351-61e1966b5d88)
## data.isnull().sum()
![Screenshot 2023-11-11 165013](https://github.com/dilipkumar1265/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119065291/94cd76e2-681c-4f66-9b59-be743d3fe80d)
## elbow method
![Screenshot 2023-11-11 164157](https://github.com/dilipkumar1265/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119065291/9c0886b4-f5fe-49b4-9563-8930b61abc71)
## K Means cluster
![Screenshot 2023-11-11 164205](https://github.com/dilipkumar1265/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119065291/92e9fef6-62c5-4a38-a635-7d2f1eb82b10)
## customer segments
![Screenshot 2023-11-11 164217](https://github.com/dilipkumar1265/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119065291/dc94977e-f1c8-4afc-8603-94183d94f753)



## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
