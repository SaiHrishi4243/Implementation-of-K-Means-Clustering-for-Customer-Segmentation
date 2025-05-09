# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:

To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:

1. Hardware – PCs

2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm

1.Import pandas

2.Import KMeans Cluster Package

3.Fit the data in the model

4.Find the Customer Segmentation


## Program:
```

Program to implement the K Means Clustering for Customer Segmentation.
Developed by: Sai Hrishi M
RegisterNumber:  212224240140


import pandas as pd
import matplotlib.pyplot as plt
data = pd.read_csv("/content/Mall_Customers.csv")
data.head()
data.info()
data.isnull().sum()
from sklearn.cluster import KMeans
wcss=[]
for i in range(1,11):
  kmeans = KMeans(n_clusters = i, init = "k-means++")
  kmeans.fit(data.iloc[:, 3:])
  wcss.append(kmeans.inertia_)
plt.plot(range(1, 11), wcss)
plt.xlabel("No. of Clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")
km = KMeans(n_clusters = 5)
km.fit(data.iloc[:, 3:])
y_pred = km.predict(data.iloc[:, 3:])
y_pred
data["cluster"]=y_pred
df0 = data[data["cluster"] == 0]
df1 = data[data["cluster"] == 1]
df2 = data[data["cluster"] == 2]
df3 = data[data["cluster"] == 3]
df4 = data[data["cluster"] == 4]
plt.scatter(df0["Annual Income (k$)"], df0["Spending Score (1-100)"], c = "red", label = "cluster0")
plt.scatter(df1["Annual Income (k$)"], df1["Spending Score (1-100)"], c = "black", label = "cluster1")
plt.scatter(df2["Annual Income (k$)"], df2["Spending Score (1-100)"], c = "blue", label = "cluster2")
plt.scatter(df3["Annual Income (k$)"], df3["Spending Score (1-100)"], c = "green", label = "cluster3")
plt.scatter(df4["Annual Income (k$)"], df4["Spending Score (1-100)"], c = "magenta", label = "cluster4")
plt.legend()
plt.title("Customer Segments")


```

## Output:

![Screenshot 2025-05-09 091452](https://github.com/user-attachments/assets/b8754892-9287-4db5-a5b0-2b3726952cd7)

![Screenshot 2025-05-09 091512](https://github.com/user-attachments/assets/9406a4ea-cebb-4d59-a6bf-d5b9ff991788)

![Screenshot 2025-05-09 091635](https://github.com/user-attachments/assets/5d049eef-1c45-4184-a9f0-0152b56fe5f8)

## Result:

Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
