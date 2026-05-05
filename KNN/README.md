# K-Nearest Neighbors From Scratch

This folder contains a from-scratch implementation of the K-Nearest Neighbors (KNN) classifier using Python and NumPy. KNN is a simple instance-based algorithm that predicts a label by looking at the closest training samples in feature space. It is commonly used for pattern recognition, baseline classification, recommendation-style similarity tasks, and small to medium tabular datasets.

## What I Implemented
- Euclidean distance calculation between samples.
- Distance computation from a test point to all training samples.
- Selection of the `k` nearest neighbors using sorted distances.
- Majority voting to assign the predicted class.
- Batch prediction for a test set.
- Accuracy calculation for evaluation.

## Experiments & Observations
- Used the Iris dataset after dropping the `Id` column and mapping species names to integer labels.
- Split the data into training and test sets.
- Evaluated the model with `k=3`.
- Ran an experiment across odd `K` values from `1` to `49`.
- Compared train and test accuracy across different `K` values.

Key observations:
- The notebook achieved `100%` test accuracy with `k=3` on the chosen split.
- Small values of `K` fit the local structure more aggressively, while larger values smooth the decision boundary.
- Comparing train and test accuracy across `K` values is a practical way to see where underfitting or overfitting starts to appear.

## Key Learnings
- KNN has almost no training phase, but prediction becomes expensive because every test sample compares against the full training set.
- Choosing `K` is a real modeling decision, not just a hyperparameter to plug in blindly.
- Feature-space distance is the core of the algorithm, so understanding what "closeness" means matters a lot.
- Even a simple algorithm can perform very well on clean, well-separated datasets like Iris.

## Challenges Faced
- Implementing the distance pipeline efficiently without using library classifiers.
- Making sure the neighbor indices and majority vote logic stayed aligned with the correct labels.
- Interpreting performance changes as `K` grows, especially when train and test accuracy move in different directions.
- Managing notebook versions in this folder and keeping the final workflow clear.

## How to Run
1. Open `finalcode.ipynb` in Jupyter Notebook or VS Code.
2. Run the cells from top to bottom.
3. The notebook will train the KNN classifier, test different `K` values, and plot accuracy trends.
