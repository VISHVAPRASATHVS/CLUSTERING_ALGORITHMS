# Mall Customer Segmentation using Hierarchical Clustering

Project Overview:
This project aims to segment customers of a mall based on their Annual Income and Spending Score. By identifying distinct customer groups, the mall can tailor marketing strategies and improve customer satisfaction. We utilize Hierarchical Clustering for this segmentation task.

Dataset:
The dataset used is Mall_Customers.csv, which contains information about mall customers. Key features include:

CustomerID: Unique ID for each customer.
Genre: Gender of the customer.
Age: Age of the customer.
Annual_Income_(k$): Annual income of the customer in thousands of dollars.
Spending_Score: A score (1-99) assigned by the mall based on customer behavior and spending habits.
Data Preprocessing
The following steps were performed to prepare the data for clustering:

Load Data: The Mall_Customers.csv file was loaded into a pandas DataFrame.
Missing Values Check: No missing values were found in the dataset.
Categorical Encoding: The Genre column (Male/Female) was converted into numerical format using LabelEncoder.
Feature Selection: For clustering, we focused on Annual_Income_(k$) and Spending_Score, as these are the most relevant features for segmenting customers based on their purchasing power and habits. Age, CustomerID, and Genre were dropped from the feature set for clustering.
Feature Scaling: The selected features (Annual_Income_(k$) and Spending_Score) were scaled using StandardScaler to ensure that no single feature dominates the clustering process due to its scale.
Clustering Model - Agglomerative Clustering
Hierarchical Clustering, specifically AgglomerativeClustering, was used to group the customers.

Model: AgglomerativeClustering
Number of Clusters (n_clusters): 5 (determined by visualizing the dendrogram and silhouette score).
Linkage: average (calculates the average distance between all observations in the two sets).
Evaluation
The clustering performance was evaluated using the Silhouette Score.

Silhouette Score: 0.479

A silhouette score close to 1 indicates that the objects are well matched to their own cluster and poorly matched to neighboring clusters, while a score close to -1 indicates the opposite.

Visualizations:
Dendrogram
A dendrogram was generated to visualize the hierarchical relationship between clusters, aiding in the selection of the optimal number of clusters.

Dendrogram:

Cluster Visualization:
A scatter plot shows the customers distributed across Annual_Income_(k$) and Spending_Score, colored by their assigned cluster.

Conclusion and Insights:
Based on the clustering results, we have identified 5 distinct customer segments. These segments can be analyzed further to understand their characteristics based on Annual_Income_(k$) and Spending_Score. For example, one cluster might represent high-income, high-spending customers, while another might be low-income, low-spending individuals. This segmentation can help the mall develop targeted marketing campaigns, personalized offers, and optimize store layouts to cater to the specific needs of each customer group.


# Customer Segmentation using K-Means Clustering

Project Overview:
This project focuses on performing customer segmentation using the K-Means clustering algorithm. The goal is to identify distinct groups of customers based on their demographic and spending habits, which can help businesses tailor marketing strategies and improve customer relationship management.

Dataset:
The dataset used for this analysis is Mall_Customers.csv, which contains information about mall customers, including:

CustomerID: Unique identifier for each customer.
Genre: Gender of the customer.
Age: Age of the customer.
Annual_Income_(k$): Annual income of the customer in thousands of dollars.
Spending_Score: A score (1-100) assigned by the mall based on customer behavior and spending nature.
Objective
To segment customers into homogeneous groups to gain insights into different customer profiles and behaviors.

Methodology:
The following steps were performed:

Data Loading and Initial Exploration: Loaded the dataset and checked for missing values and data types.
Data Preprocessing:
Encoded the 'Genre' categorical feature into numerical format using LabelEncoder.
Selected relevant features ('Age', 'Annual_Income_(k$)', 'Spending_Score') for clustering.
Scaled the selected features using StandardScaler to ensure all features contribute equally to the distance calculation.
Determining Optimal Number of Clusters (K): Used the Elbow Method (WCSS - Within-Cluster Sum of Squares) to find an appropriate number of clusters.
K-Means Clustering: Applied the K-Means algorithm with the identified optimal number of clusters (k=5).
Cluster Assignment: Assigned each customer to a cluster.
Evaluation: Calculated the Silhouette Score to evaluate the quality of the clustering.
Visualization and Interpretation: Visualized the clusters across different feature pairs (Age vs Spending Score, Annual Income vs Spending Score, Age vs Annual Income) and profiled each cluster by examining the mean values of 'Age', 'Annual Income', and 'Spending Score'.
Results and Insights
The Elbow Method suggested 5 as an optimal number of clusters.
The Silhouette Score for the clustering was approximately 0.408, indicating a reasonable separation of clusters.
Five distinct customer segments were identified, each with unique characteristics:
Cluster 0 (Older, Mid-Income, Mid-Spending): Customers typically older, with moderate income and spending.
Cluster 1 (Young/Mid-Age, High Income, High Spending): Customers with high income and high spending scores, often considered 'target customers'.
Cluster 2 (Young, Low Income, High Spending): Younger customers with lower income but high spending scores, potentially impulse buyers or trend-followers.
Cluster 3 (Young/Mid-Age, Mid-Income, Low Spending): Customers with moderate income but low spending scores.
Cluster 4 (Mid/Older Age, High Income, Low Spending): Older customers with high income but low spending scores, often cautious spenders.

# Customer Segmentation using DBSCAN

Project Overview:
This project aims to segment mall customers based on their Annual Income and Spending Score using the DBSCAN clustering algorithm. The goal is to identify distinct groups of customers to enable targeted marketing strategies.

Dataset:
The dataset used is Mall_Customers.csv, which contains customer information including:

CustomerID: Unique ID for each customer
Genre: Gender of the customer
Age: Age of the customer
Annual_Income_(k$): Annual income of the customer in thousands of dollars
Spending_Score: Spending score (1-100) assigned by the mall based on customer behavior
Project Steps
1. Data Loading and Initial Exploration
The dataset Mall_Customers.csv is loaded into a pandas DataFrame.
Initial checks for missing values and data types are performed.
2. Data Preprocessing
The Genre (Gender) column is converted into numerical format using LabelEncoder (Female: 0, Male: 1).
Irrelevant columns like Age, CustomerID, and Genre are dropped for the clustering analysis, focusing on Annual_Income_(k$) and Spending_Score.
The selected features are scaled using StandardScaler to ensure that no single feature dominates the clustering due to its scale.
3. DBSCAN Clustering
The DBSCAN (Density-Based Spatial Clustering of Applications with Noise) algorithm is applied to the scaled data.
Parameters used:
eps = 0.4: The maximum distance between two samples for one to be considered as in the neighborhood of the other.
min_samples = 4: The number of samples (or total weight) in a neighborhood for a point to be considered as a core point.
metric = 'euclidean': The distance metric used to calculate distances between points.
The cluster labels generated by DBSCAN are added as a new column cluster to the original DataFrame.
4. Results and Evaluation
The unique cluster labels and their respective counts are displayed. DBSCAN can identify noise points, labeled as -1.
The Silhouette Score is calculated to evaluate the quality of the clustering. A score of 0.3983 indicates moderately defined clusters.
5. Visualization
A scatter plot is generated to visualize the customer segments based on their Annual Income and Spending Score, with each cluster represented by a different color. This helps in understanding the distinct groups identified by DBSCAN.
