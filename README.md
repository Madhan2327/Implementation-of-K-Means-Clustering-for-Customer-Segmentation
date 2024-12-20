# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1..Import pandas and matplotlib.pyplot
2.Read the dataset and transform it
3.Import KMeans and fit the data in the model
4.Plot the Cluster graph
## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: Madhan C
RegisterNumber: 24004329  
*/
import pandas as pd
import matplotlib.pyplot as plt
data = pd.read_csv("C:/Users/LENOVO/Downloads/Mall_Customers.csv")
data.head()
data.info()
data.isnull().sum()
from sklearn.cluster import KMeans
wcss = [] #Within-Cluster Sum of Square
#It is the sum of squared distance between each point & the centroid in a cluster.
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
plt.scatter(df0["Annual Income (k$)"], df0["Spending Score (1-100)"], c="red", label="cluster 0")
plt.scatter(df1["Annual Income (k$)"], df1["Spending Score (1-100)"], c="black", label="cluster 1")
plt.scatter(df2["Annual Income (k$)"], df2["Spending Score (1-100)"], c="blue", label="cluster 2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster 3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="magenta",label="cluster 4")
plt.legend()
plt.title("Customer Segments")
```

## Output:
![K Means Clustering for Customer Segmentation](sam.png)
![Screenshot 2024-12-20 084000](https://github.com/user-attachments/assets/61d91596-f135-4ee7-a03e-d50a1b237664)
![Screenshot 2024-12-20 084005](https://github.com/user-attachments/assets/aeba4d23-45cd-417a-8355-06765c128748)
![Screenshot 2024-12-20 084010](https://github.com/user-attachments/assets/ef0172c1-be77-4260-a923-acd05baa11be)
![Screenshot 2024-12-20 084016](https://github.com/user-attachments/assets/6c6d7fe2-54c0-4c44-9287-f3382d0c394e)
![Screenshot 2024-12-20 084021](https://github.com/user-attachments/assets/6bb29dc2-060c-4831-9ad7-d42a9999f43c)
![Screenshot 2024-12-20 084026](https://github.com/user-attachments/assets/d2867af3-d123-4c27-ba44-5a7a944ff2c4)
![Screenshot 2024-12-20 084034](https://github.com/user-attachments/assets/8525ec99-f741-4e00-bad9-a24d71cd904c)
## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
