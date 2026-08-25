# Exp 4 Elbow Method using K-Means Clustering

**Date:**

## AIM:
To implement the Elbow Method using K-Means Clustering in Python to determine the optimal number of clusters for customers based on their Annual Income and Spending Score by plotting WCSS against different values of K.

## DESIGN STEPS:

### Step 1:
Clone the repository from GitHub.

### Step 2:
Create a Python project in the preferred IDE (VS Code/PyCharm/Jupyter Notebook).

### Step 3:
Create the Python program for implementing the Elbow Method using the Scikit-learn library.

### Step 4:
Load the customer dataset and select the features **Annual Income** and **Spending Score**.

### Step 5:
Run the K-Means algorithm for different values of **K** (number of clusters).

### Step 6:
Calculate the **Within-Cluster Sum of Squares (WCSS)** for each value of **K**.

### Step 7:
Plot the WCSS values against the corresponding values of **K** to identify the optimal number of clusters using the Elbow Method.

### Step 8:
Execute the program and analyze the elbow point in the graph.

## PROGRAM:
# Step 1: Import libraries
import pandas as pd
import matplotlib.pyplot as plt
from sklearn.cluster import KMeans

# Step 2: Load dataset
data = pd.read_csv("customers_large_dataset.csv")

# Step 3: Select numeric columns
X = data[["Annual Income", "Spending Score"]]

# Step 4: Calculate WCSS for different K values
wcss = []

for k in range(1, 11):
    kmeans = KMeans(n_clusters=k, random_state=42, n_init=10)
    kmeans.fit(X)
    wcss.append(kmeans.inertia_)

# Step 5: Plot the Elbow Graph
plt.figure(figsize=(8, 5))
plt.plot(range(1, 11), wcss, marker="o")
plt.xlabel("Number of Clusters (K)")
plt.ylabel("WCSS")
plt.title("Elbow Method")
plt.xticks(range(1, 11))
plt.grid(True)
plt.show()


## OUTPUT:

<img width="1917" height="1033" alt="Screenshot 2026-08-25 091709" src="https://github.com/user-attachments/assets/161ded4b-3771-4a17-9c11-51fe34adc024" />

## RESULT:

The Elbow Method using K-Means Clustering was implemented successfully. The optimal number of clusters was determined by analyzing the WCSS plot and identifying the elbow point, which can be used for effective customer segmentation based on Annual Income and Spending Score.
