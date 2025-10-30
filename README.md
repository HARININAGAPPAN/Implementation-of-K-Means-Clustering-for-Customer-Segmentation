# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Load and preprocess data: Import data, inspect it, and handle missing values if any.

2.Determine optimal clusters: Use the Elbow Method to identify the number of clusters by plotting WCSS against cluster numbers.

3.Fit the K-Means model: Apply K-Means with the chosen number of clusters to the selected features.

4.Assign cluster labels to each data point.

5.Plot data points in a scatter plot, color-coded by cluster assignments for interpretation.
## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: Harini N
RegisterNumber: 212223040057
import pandas as pd
import matplotlib.pyplot as plt
data = pd.read_csv("Mall_Customers.csv")
data.head()
data.info()
data.isnull().sum()
from sklearn.cluster import KMeans
wcss = []
for i in range(1,11):
    kmeans = KMeans(n_clusters = i,init = "k-means++",n_init=10)
    kmeans.fit(data.iloc[:,3:])
    wcss.append(kmeans.inertia_)
plt.plot(range(1,11),wcss)
plt.xlabel("No. of Clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")
km = KMeans(n_clusters=5, n_init=10)
km.fit(data.iloc[:, 3:])
y_pred = km.predict(data.iloc[:,3:])
y_pred
data["cluster"] = y_pred
df0 = data[data["cluster"]==0]
df1 = data[data["cluster"]==1]
df2 = data[data["cluster"]==2]
df3 = data[data["cluster"]==3]
df4 = data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster1")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="black",label="cluster2")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="blue",label="cluster3")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster4")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="magenta",label="cluster5")
plt.legend()
plt.title("Customer Segments")

*/
```

## Output:
<img width="552" height="223" alt="image" src="https://github.com/user-attachments/assets/16aec8d3-1ae2-44e9-9ccb-dff0aa4d1c05" />

<img width="552" height="262" alt="image" src="https://github.com/user-attachments/assets/b96ffc7c-8cf0-4f71-8b16-bbe1644243e1" />

<img width="264" height="159" alt="image" src="https://github.com/user-attachments/assets/86de0e42-a3c7-4956-af54-26c5845f2b19" />

<img width="530" height="403" alt="image" src="https://github.com/user-attachments/assets/ee44350f-b3d4-4409-963c-686fafa33b08" />

<img width="535" height="303" alt="image" src="https://github.com/user-attachments/assets/7f2d66ed-dd20-4164-b042-0b3a243842ce" />

<img width="866" height="777" alt="image" src="https://github.com/user-attachments/assets/980458f3-a75f-4e68-ba29-5a5a12f5391b" />






## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
