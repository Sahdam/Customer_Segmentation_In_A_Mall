# Customer Segmentation using K-Means Clustering

This project aims to segment mall customers into distinct groups based on their 'Annual Income (k$)' and 'Spending Score (1-100)' using the K-Means clustering algorithm. Customer segmentation allows businesses to understand their customer base better, enabling more targeted marketing strategies and personalized services.

By identifying different customer profiles, we can tailor offerings to meet specific needs and preferences, ultimately improving customer satisfaction and business profitability.

This project aims to segment mall customers into distinct groups based on their 'Annual Income (k$)' and 'Spending Score (1-100)' using the K-Means clustering algorithm. Customer segmentation allows businesses to understand their customer base better, enabling more targeted marketing strategies and personalized services.

By identifying different customer profiles, we can tailor offerings to meet specific needs and preferences, ultimately improving customer satisfaction and business profitability.

## Introduction

Customer segmentation is a powerful marketing technique that involves dividing a customer base into distinct groups based on shared characteristics. This project applies K-Means clustering, an unsupervised machine learning algorithm, to a mall customer dataset to identify naturally occurring customer segments. The primary goal is to provide actionable insights that can inform marketing strategies and customer relationship management.

## Dataset

The dataset used in this project is `Mall_Customers.csv`, containing information about mall customers. The key features used for clustering are:

-   **CustomerID**: Unique identifier for each customer.
-   **Gender**: Gender of the customer.
-   **Age**: Age of the customer.
-   **Annual Income (k$)**: Annual income of the customer in thousands of dollars.
-   **Spending Score (1-100)**: A score assigned by the mall based on customer behavior and spending habits.


## Exploratory Data Analysis (EDA)

Exploratory Data Analysis was performed to understand the distribution and characteristics of the dataset. Key steps included:

-   **Loading Data**: Reading the `Mall_Customers.csv` file into a pandas DataFrame.
-   **Data Cleaning**: Checking for missing values (none found) and data types. `CustomerID` was set as the index.
-   **Summary Statistics**: Generating descriptive statistics using `.describe()`.
-   **Visualizations**:
    -   Histograms for 'Age', 'Annual Income (k$)', and 'Spending Score (1-100)' to observe their distributions.
    -   Box plot to visualize 'Gender' vs. 'Spending Score (1-100)' to see gender-based spending patterns.
    -   A scatter plot of 'Annual Income (k$)' vs. 'Spending Score (1-100)' revealed initial visual groupings, suggesting the suitability of clustering.

## Optimal Number of Clusters

To determine the optimal number of clusters (`k`) for the K-Means algorithm, two common methods were employed:

1.  **Elbow Method**: This method plots the inertia (sum of squared distances of samples to their closest cluster center) against the number of clusters. The 'elbow point' in the plot suggests the optimal `k`.
2.  **Silhouette Score**: This metric measures how similar an object is to its own cluster compared to other clusters. A higher silhouette score indicates better-defined clusters.

Both methods suggested that **5** is the optimal number of clusters for this dataset.


## K-Means Clustering

After determining the optimal number of clusters, a K-Means model was built with `k=5`.

-   **Model Initialization**: `KMeans(n_clusters=5, random_state=42, n_init=10, max_iter=1000)`.
-   **Fitting**: The model was fitted to the selected features: 'Annual Income (k$)' and 'Spending Score (1-100)'.
-   **Prediction**: Cluster labels were assigned to each customer.
-   **Cluster Analysis**: The mean 'Annual Income (k$)' and 'Spending Score (1-100)' for each cluster were calculated to understand the characteristics of each segment.

## Results and Insights

Based on the clustering results, five distinct customer segments were identified:

-   **Cluster 0 (Moderate Group)**: Moderate Income Earner, Moderate Spenders
-   **Cluster 1 (High-Value Group)**: High Income Earner, High Spenders
-   **Cluster 2 (Target Group - Enthusiasts)**: Low Income Earner, High Spenders
-   **Cluster 3 (Careful Spenders)**: High Income Earner, Low Spenders
-   **Cluster 4 (Budget-Conscious Group)**: Low Income Earner, Low Spenders

These insights are visualized through a scatter plot showing 'Annual Income (k$)' versus 'Spending Score (1-100)', with each customer colored by their predicted cluster and cluster centroids marked.

This segmentation provides valuable information for tailoring marketing efforts:
-   **High-Value Group (Cluster 1)**: These are ideal customers. Loyalty programs and exclusive offers could further enhance their engagement.
-   **Target Group - Enthusiasts (Cluster 2)**: Despite lower income, they are high spenders. Understanding their motivation can help attract more similar customers.
-   **Careful Spenders (Cluster 3)**: High income but low spending. Campaigns focusing on value, luxury, or new product launches might incentivize them to spend more.
-   **Budget-Conscious Group (Cluster 4)**: Low income and low spending. Promotions on essential items or entry-level products could be effective.
-   **Moderate Group (Cluster 0)**: A balanced group that could be influenced by a variety of marketing strategies.


## How to Run

1.  **Clone the repository (if applicable)**: `git clone <repository_url>`
2.  **Navigate to the project directory**.
3.  **Ensure you have all the requirements installed** (see [Requirements](#requirements)).
4.  **Open the Jupyter/Colab notebook** (e.g., `customer_segmentation.ipynb`).
5.  **Run all cells** sequentially to reproduce the analysis and results.


## Conclusion

This project successfully segmented mall customers into five distinct groups based on their spending and income patterns. The insights gained from this segmentation can be leveraged by the mall's marketing team to develop more personalized and effective strategies, ultimately leading to improved customer engagement and increased revenue.

## Author

[Olayinka Yusuf]
