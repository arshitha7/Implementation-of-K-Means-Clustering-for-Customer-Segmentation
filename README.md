# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import the necessary packages using import statement.

2.Read the given csv file using read_csv() method and print the number of contents to be displayed using df.head().

3.Import KMeans and use for loop to cluster the data.

4.Predict the cluster and plot data graphs.

5.Print the outputs and end the program


## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: ARSHITHA MS
RegisterNumber: 212223240015 
*/
import pandas as pd
import matplotlib.pyplot as plt
data=pd.read_csv(r'Mall_Customers.csv')

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
y_pred

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
### Head():
![image](https://github.com/23008344/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/145742655/a3c39d82-2b6b-4987-85c2-c0eb0ce7d889)

### Info():
![image](https://github.com/23008344/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/145742655/a2a12e8e-6199-4449-a4ad-fee572d4a9df)

### isnull.sum():
![image](https://github.com/23008344/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/145742655/a95cd78f-ca0e-4c0c-88cd-a04999582215)

### Elbow Method:
![image](https://github.com/23008344/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/145742655/95db45d4-7719-4339-924c-db8c00ba7de5)

### Fitting the no. of clusters:
![image](https://github.com/23008344/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/145742655/f4cbdac9-e169-4a11-a191-1e62477e9678)

### Prediction of Y:
![image](https://github.com/23008344/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/145742655/90211d46-6bc0-4aa8-a917-38e68d95857c)

### Customer Segments:
![image](https://github.com/23008344/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/145742655/ab87b4bb-efe4-4bba-9aa7-0353444b7b84)


## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
