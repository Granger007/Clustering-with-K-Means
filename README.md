# K-Means Clustering Project

## Objective

Perform unsupervised learning using **K-Means** clustering to group data into meaningful clusters.

## Tools Used

* **Python**
* **Pandas**
* **Matplotlib**
* **Scikit-learn**

## Steps

### 1. Load and Explore the Dataset

* Load data from CSV or a built-in dataset (e.g., Iris).
* Inspect data using `.head()` and `.describe()`.
* Optionally scale features for better clustering results.

### 2. Visualize the Dataset

* Use **PCA** to reduce data to 2 dimensions for easy plotting.
* Scatter plot for a quick visual check.

### 3. Determine Optimal K (Elbow Method)

* Loop over a range of K values (e.g., 2–10).
* Fit K-Means and record **inertia**.
* Plot K vs. inertia to find the "elbow" point.

### 4. Train K-Means Model

```python
from sklearn.cluster import KMeans
kmeans = KMeans(n_clusters=K_optimal, random_state=42)
labels = kmeans.fit_predict(X)
```

* `labels` contains the cluster index for each sample.

### 5. Visualize Clusters

* Color-code points based on cluster labels.
* Plot PCA components for a 2D view.

### 6. Evaluate Clustering

* Use **Silhouette Score** to measure how well samples are clustered.

```python
from sklearn.metrics import silhouette_score
score = silhouette_score(X, labels)
print(f"Silhouette Score: {score:.3f}")
```

* Higher scores (closer to 1) indicate better-defined clusters.

## Example Output

* **Elbow Method plot** to choose K.
* **Cluster visualization** in PCA space.
* **Silhouette Score** to evaluate quality.

## Notes

* Scaling data before clustering often improves results.
* PCA is used here only for visualization; clustering is done on full feature space.
* Random seed is fixed for reproducibility.
