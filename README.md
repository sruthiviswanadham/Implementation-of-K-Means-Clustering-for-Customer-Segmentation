# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Data Preparation: Load data, handle missing values, and extract relevant features for clustering.

2. Determine Clusters: Use the Elbow Method to find optimal number of clusters based on WCSS.

3. K-Means Clustering: Fit the K-Means model with optimal clusters, predict cluster labels for data.

4. Visualization: Plot data points with distinct colors for each cluster to visualize clustering results.


## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: viswanadham venkata sai sruthi
RegisterNumber:212223100061
*/
```
```
import pandas as pd 
import matplotlib.pyplot as plt 
```
```
data=pd.read_csv("Mall_Customers.csv")
data.head()
```
## Output:
![image](https://github.com/user-attachments/assets/d970e94b-50cc-4bd1-8013-ed7bdd559552)
```
data.info()
```
## Output:
![image](https://github.com/user-attachments/assets/dd443d39-2c35-4939-a8bb-5a74ab0ff9e5)
```
data.isnull().sum()
```
## Output:
![image](https://github.com/user-attachments/assets/1a255d89-8395-4874-ac9a-3eb833156ce4)
```
from sklearn.cluster import KMeans
wcss = []
for i in range(1,11):
    kmeans = KMeans(n_clusters = i,init = "k-means++")
    kmeans.fit(data.iloc[:,3:])
    wcss.append(kmeans.inertia_)
plt.plot(range(1,11),wcss)
plt.xlabel("No.of Clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")
```
## Output:
![image](https://github.com/user-attachments/assets/7e01b052-e7a3-4d10-9fa7-6aece0f9a1e4)
```
km=KMeans(n_clusters=5)
km.fit(data.iloc[:,3:])
KMeans(n_clusters=5)
y_pred=km.predict(data.iloc[:,3:])
y_pred
```
## Output:
![image](https://github.com/user-attachments/assets/2e8a7873-a2f1-4885-9823-dad6916f882b)
```
data["cluster"]=y_pred
df0 = data[data["cluster"]==0]
df1 = data[data["cluster"]==1]
df2 = data[data["cluster"]==2]
df3 = data[data["cluster"]==3]
df4 = data[data["cluster"]==4]
```
```
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"], color = "gold")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"], color = "pink")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"], color = "green")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"], color = "blue")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"], color = "red")
plt.show()
```
## Output:
![image](https://github.com/user-attachments/assets/88d97371-fc53-403c-9b9d-50c6deebf3fc)




## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.

