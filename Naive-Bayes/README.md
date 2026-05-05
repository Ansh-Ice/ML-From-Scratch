# Naive Bayes From Scratch

This folder contains a from-scratch implementation of Gaussian Naive Bayes using Python and NumPy. Naive Bayes is a probabilistic classifier that predicts classes by combining prior probabilities with feature likelihoods under a conditional independence assumption. It is widely used for fast baseline classification, document filtering, medical screening, and structured multi-class problems.

## What I Implemented
- Class prior calculation from the training labels.
- Per-class feature statistics: mean and variance.
- Gaussian likelihood computation for continuous features.
- Posterior score calculation using log probabilities for numerical stability.
- Single-sample and batch prediction.
- Manual accuracy calculation and confusion matrix generation.

## Experiments & Observations
- Used the Iris dataset after removing the `Id` column and encoding species labels numerically.
- Split the data into training and test sets.
- Computed per-class means and variances for each feature.
- Evaluated the model on the test set and visualized feature distributions by class.
- Compared train and test accuracy and plotted the confusion matrix.

Key observations:
- The notebook achieved `100%` test accuracy on the selected Iris split.
- The confusion matrix showed perfect separation on that run, which suggests the class distributions were well separated in the chosen feature space.
- Per-class histograms and mean plots made it easier to see why Gaussian Naive Bayes works well on this dataset.

## Key Learnings
- Naive Bayes can perform surprisingly well when class-conditional feature distributions are reasonably distinct.
- Using log probabilities is important because multiplying many small likelihood values quickly becomes numerically unstable.
- The independence assumption is strong, but the model can still work very well in practice.
- Inspecting class-wise statistics gives a much better intuition for what the classifier is actually using.

## Challenges Faced
- Implementing Gaussian likelihoods carefully so variance handling stayed stable.
- Making sure posterior computation remained numerically safe.
- Keeping label encoding, class statistics, and confusion matrix indexing consistent.
- Understanding model behavior beyond accuracy by checking per-class feature distributions.

## How to Run
1. Open `code.ipynb` in Jupyter Notebook or VS Code.
2. Run the cells from top to bottom.
3. The notebook will train the Gaussian Naive Bayes classifier and generate evaluation plots and a confusion matrix.
