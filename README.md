# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Import pandas and mataplotlib.pyplot
2.Read the dataset and transform it 
3.Import KMeans and fit the data in the model 
4. Plot the cluster graph

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by:Ramya G 
RegisterNumber: 24003270 
*/
```
```
import pandas as pd
import matplotlib.pyplot as plt
data = pd.read_csv("Mall_Customers.csv")
data.head()
data.info()
data.isnull().sum()
from sklearn.cluster import KMeans
wcss = []
for i in range(1,11):
    kmeans = KMeans(n_clusters = i,init = "k-means++")
    kmeans.fit(data.iloc[:,3:])
    wcss.append(kmeans.inertia_)

plt.plot(range(1,11),wcss)
plt.xlabel("No. of Clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")
km = KMeans(n_clusters = 5)
km.fit(data.iloc[:,3:])

y_pred = km.predict(data.iloc[:,3:])
print(y_pred)
data["cluster"] = y_pred
df0 = data[data["cluster"]==0]
df1 = data[data["cluster"]==1]
df2 = data[data["cluster"]==2]
df3 = data[data["cluster"]==3]
df4 = data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="black",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="blue",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="magenta",label="cluster4")
plt.legend()
plt.title("Customer Segments")
```

## Output:
![K Means Clustering for Customer Segmentation](sam.png)
![Screenshot 2024-12-15 211811](https://github.com/user-attachments/assets/5973b264-e426-4d15-8d4e-5e6e8c043e1c)
![Screenshot 2024-12-15 212045](https://github.com/user-attachments/assets/cbd1c1fd-1d7f-4cd9-bea2-bce5228c08ca)
![Screenshot 2024-12-15 211855](https://github.com/user-attachments/assets/0b399c69-e7ab-4215-a5d2-f7377291b670)
![Screenshot 2024-12-15 211905](https://github.com/user-attachments/assets/db5fb384-b7b0-4845-a0f3-0efddf75ec95)


## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
