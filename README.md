# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import the required libraries.
2. Read the data set and find the number of null data.
3. Import KMeans from sklearn.clusters library package.
4. Find the y_pred .
5. Plot the clusters in graph.

## Program:
```
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: SOMEASVAR.R
RegisterNumber:  212221230103
```
```
import pandas as pd
import matplotlib.pyplot as plt
data=pd.read_csv("Mall_Customers.csv")
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
plt.xlabel("No of Clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")

km=KMeans(n_clusters = 5)
km.fit(data.iloc[:,3:])

y_pred = km.predict(data.iloc[:,3:])
y_pred

data["cluster"]= y_pred
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
plt.title("Customer Segments")
```

## Output:
## data.head() function:
![image](https://github.com/SOMEASVAR/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/93434149/6cf30b0c-efea-419f-9f81-94541811c5db)
## data.info():
![image](https://github.com/SOMEASVAR/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/93434149/6ffad7df-fb1b-4065-8c9f-2e7e67f3acae)
## data.isnull().sum() function:
![image](https://github.com/SOMEASVAR/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/93434149/0372e754-75b6-4598-8b59-e8baeef06403)
## Elbow method Graph:
![image](https://github.com/SOMEASVAR/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/93434149/948e73fc-0b15-4344-8f04-66704341443c)
## KMeans clusters:
![image](https://github.com/SOMEASVAR/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/93434149/fee009a3-c947-4c00-be61-ff6e5ff376c1)
![image](https://github.com/SOMEASVAR/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/93434149/e95c96c8-b6b6-4447-b2e5-f06aca4f69fb)
## Customer segments Graph:
![image](https://github.com/SOMEASVAR/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/93434149/5f318a35-d2d3-4229-a277-f2037af2a390)
## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
