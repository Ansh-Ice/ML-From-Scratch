# K-Means From Scratch

This folder contains a from-scratch implementation of K-Means clustering using Python and NumPy. K-Means is an unsupervised learning algorithm used to group similar data points into clusters based on distance to cluster centroids. It is commonly applied in customer segmentation, document grouping, image compression, and exploratory data analysis.

## What I Implemented
- Euclidean distance computation between points and centroids.
- Random centroid initialization from existing samples.
- Cluster assignment based on nearest centroid.
- Centroid updates using the mean of assigned points.
- A full K-Means training loop with iterative refinement.
- Empty-cluster handling by randomly reinitializing a centroid.
- Inertia calculation to measure within-cluster compactness.

## Experiments & Observations
- Generated synthetic 2D blobs data and visualized it before clustering.
- Ran K-Means with different values of `K` including `2`, `3`, `4`, and `5`.
- Visualized final cluster assignments and centroid positions.

Key observations:
- The clustering looked most natural when `K=3`, which matches the structure of the generated dataset.
- Different initial centroids can lead to different early assignments, which is why the algorithm may converge differently across runs.
- Adding empty-cluster handling made the implementation more stable when a centroid received no points.

## Key Learnings
- K-Means is simple to implement, but initialization has a strong effect on the result.
- The update step is straightforward mathematically, yet the quality of clustering depends heavily on the current assignments.
- Visualizing the clusters is one of the fastest ways to debug whether the algorithm is behaving correctly.
- Inertia is useful for comparing cluster compactness, but it should be interpreted together with the data distribution and visual structure.

## Challenges Faced
- Making sure labels were reassigned correctly at every iteration.
- Handling cases where a cluster became empty during centroid updates.
- Dealing with randomness in initialization, which can change the final clustering outcome.
- Verifying convergence behavior without relying on a library implementation.

## How to Run
1. Open `code.ipynb` in Jupyter Notebook or VS Code.
2. Run the notebook cells in sequence.
3. The notebook will generate sample data, cluster it with K-Means, and show plots for different values of `K`.
