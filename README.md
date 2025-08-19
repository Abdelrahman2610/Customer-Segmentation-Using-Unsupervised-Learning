# Customer Segmentation Using Unsupervised Learning

## Overview

This project implements **Customer Segmentation** using unsupervised learning techniques on the Mall Customers dataset. The goal is to identify distinct customer groups based on features such as **Annual Income** and **Spending Score**, enabling targeted marketing strategies. The notebook utilizes **K-Means** and **DBSCAN** clustering algorithms, along with optimization techniques as the **Elbow Method** and **Silhouette Score** to determine the optimal number of clusters.

## Features

- **Exploratory Data Analysis (EDA)**: Visualizations including correlation heatmaps, pairplots by gender, and scatter plots to understand customer data distributions and relationships.
- **Data Preprocessing**: Handling missing values, encoding categorical variables (e.g., Gender), and scaling features for robust clustering.
- **Clustering Algorithms**:
  - **K-Means**: Segments customers into 5 clusters based on income and spending behavior.
  - **DBSCAN**: Identifies noise points and 7 clusters based on density, providing an alternative segmentation approach.
- **Cluster Optimization**: Uses the Elbow Method (elbow at K=5) and Silhouette Score (peak at K=5 with score \~0.55) to determine the optimal number of clusters.
- **Visualizations**: High-resolution plots (saved in the `plots` folder) including cluster scatter plots with centroids, Elbow curves, Silhouette score visualizations, raw data scatter, DBSCAN clusters, and pairplots.
- **Cluster Analysis**: Computes average Annual Income and Spending Score per cluster to derive actionable marketing insights, such as targeting high-income low-spenders with premium offers.

## Table of Contents

- Installation
- Usage
- Project Structure
- Results
- Contributing
- License
- Contact

## Installation

### Prerequisites

- Python 3.8+

- Jupyter Notebook or Kaggle account

- Required libraries:

  ```plaintext
  pandas
  numpy
  scikit-learn
  seaborn
  matplotlib
  ```

### Steps

1. **Clone the repository**:

   ```bash
   git clone https://github.com/Abdelrahman2610/Customer-Segmentation-Using-Unsupervised-learning.git
   cd Customer-Segmentation-Using-Unsupervised-learning
   ```

2. **Install dependencies**:

   ```bash
   pip install -r requirements.txt
   ```

3. **Download the dataset**:

   - Obtain the Mall Customers dataset from Kaggle.
   - Place the `Mall_Customers.csv` file in the project directory.

4. **Run the notebook**:

   ```bash
   Jupyter Notebook Customer-Segmentation-Using-Unsupervised-learning.ipynb
   ```

   Alternatively, upload the notebook to Kaggle and run it in a Kaggle environment.

## Usage

1. **Open the notebook** in Jupyter or Kaggle.

2. **Run the cells** sequentially to:

   - Load and preprocess the dataset.
   - Perform EDA with visualizations saved to the `plots` folder.
   - Apply K-Means and DBSCAN clustering.
   - Evaluate clusters using the Elbow Method and Silhouette Score.
   - Analyze cluster averages for marketing insights.

3. **View results**:

   - Visualizations are saved as PNG files in the `plots` folder (e.g., `plots/kmeans_clusters.png`, `plots/elbow_method.png`, `plots/silhouette_scores.png`, `plots/dbscan_clustering.png`, `plots/raw_data_scatter.png`, `plots/pairplot_gender.png`).
   - Cluster analysis results are displayed in the notebook output.

Example command to start Jupyter Notebook:

```bash
jupyter notebook
```

## Project Structure

```
customer-segmentation/
│
├── customer-segmentation.ipynb  # Main Jupyter notebook
├── Mall_Customers.csv           # Dataset 
├── plots/                       # Folder for saved visualizations
│   ├── kmeans_clusters.png
│   ├── kmeans_centroids.png
│   ├── elbow_method.png
│   ├── silhouette_scores.png
│   ├── dbscan_clustering.png
│   ├── raw_data_scatter.png
│   ├── pairplot_gender.png
│   └── ...
├── requirements.txt             # Python dependencies
└── README.md                    # This file
```

## Results

- **K-Means Clustering**:
  - Optimal number of clusters: 5 (based on Elbow Method and Silhouette Score \~0.55 at K=5).
  - Clusters reveal distinct customer groups with the following approximate averages (note: cluster labels are arbitrary):

| Cluster | Average Annual Income (k$) | Average Spending Score (1-100) | Description |
| --- | --- | --- | --- |
| 0 | 55 | 49 | Medium income, medium spending – Balanced customers, target with general promotions. |
| 1 | 86 | 18 | High income, low spending – Affluent savers, attract with luxury discounts. |
| 2 | 26 | 20 | Low income, low spending – Budget-conscious, offer value deals. |
| 3 | 26 | 79 | Low income, high spending – Impulse buyers, promote affordable luxuries. |
| 4 | 88 | 82 | High income, high spending – Premium customers, focus on loyalty programs. |

- **DBSCAN Clustering**:
  - Identifies 7 clusters plus noise points, with the following averages:

| Cluster | Average Annual Income (k$) | Average Spending Score (1-100) |
| --- | --- | --- |
| \-1 (Noise) | Varies | Varies |
| 0 | 23.17 | 74.58 |
| 1 | 19.60 | 6.60 |
| 2 | 22.43 | 34.43 |
| 3 | 55.23 | 48.58 |
| 4 | 79.53 | 83.13 |
| 5 | 75.93 | 10.07 |
| 6 | 88.78 | 17.00 |

- **Visualizations**:
  - Scatter plots show clear separation of clusters based on Annual Income and Spending Score.
  - Pairplots and histograms highlight relationships and distributions by features like Age, Gender, Income, and Spending Score.
- **Insights**:
  - The segments can inform marketing: e.g., promotions for low-spenders or loyalty programs for high-value customers.
  - Limitations: Analysis focuses on two features; adding Age or Gender could improve granularity.
  - Future Work: Explore hierarchical clustering or integrate segments into a recommendation system.

![K-Means Clusters](plots/kmeans_clusters.png)\## Contributing

Contributions are welcome! To contribute:

1. **Fork the repository**.

2. **Create a new branch**:

   ```bash
   git checkout -b feature/your-feature-name
   ```

3. **Make changes** and commit:

   ```bash
   git commit -m "Add your feature description"
   ```

4. **Push to your branch**:

   ```bash
   git push origin feature/your-feature-name
   ```

5. **Open a Pull Request** on GitHub.

Please adhere to the Code of Conduct and ensure code quality with clear comments and documentation.

---

*Built with ❤️ by Abdelrahman Salah*
