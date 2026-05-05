# PCA From Scratch

This folder contains a from-scratch implementation of Principal Component Analysis (PCA) using Python and NumPy. PCA is a dimensionality reduction technique that transforms data into a smaller set of orthogonal components that preserve as much variance as possible. It is commonly used for visualization, compression, denoising, and preprocessing before other machine learning models.

## What I Implemented
- Mean-centering of the dataset.
- Covariance matrix computation.
- Eigenvalue and eigenvector decomposition.
- Sorting principal components by descending variance.
- Projection of the original data onto the first principal component.
- Visualizations for the original data, centered data, principal direction, and 1D projection.

## Experiments & Observations
- Generated a 2D synthetic dataset with strongly correlated features.
- Centered the data and verified the centered mean was effectively zero.
- Computed the covariance matrix and extracted eigenvalues/eigenvectors.
- Projected the 2D data onto the first principal component.
- Visualized both the principal axis in 2D space and the resulting 1D representation.

Key observations:
- One eigenvalue was much larger than the other (`~4.07` vs `~0.045`), showing that most of the variance lay in a single direction.
- Because the two features were correlated, projecting to one component preserved the dominant structure well.
- Centering the data was an essential step; without it, the principal direction would not represent variance correctly.

## Key Learnings
- PCA is much easier to understand when you implement it geometrically instead of treating it as a black-box transform.
- Eigenvectors define directions, but eigenvalues tell you why those directions matter.
- Strongly correlated features are a natural setting where PCA becomes very intuitive.
- The projection step makes dimensionality reduction concrete: the data keeps its main pattern while losing redundant variation.

## Challenges Faced
- Keeping track of matrix shapes when moving from 2D data to a 1D projection.
- Sorting eigenvalues and eigenvectors together in the correct order.
- Interpreting the principal component direction visually rather than only numerically.
- Verifying that the centered data and covariance computation were aligned correctly.

## How to Run
1. Open `code.ipynb` in Jupyter Notebook or VS Code.
2. Run the cells in sequence.
3. The notebook will generate synthetic data, compute PCA step by step, and visualize the projection process.
