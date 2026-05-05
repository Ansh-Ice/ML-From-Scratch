# Decision Tree From Scratch

This folder contains a from-scratch implementation of a Decision Tree classifier using Python and NumPy. Decision Trees are widely used for classification because they are easy to interpret, handle non-linear decision boundaries, and work well on tabular data. They are commonly applied in medical diagnosis, risk assessment, customer segmentation, and other structured prediction tasks.

## What I Implemented
- Entropy calculation to measure node impurity.
- Information gain to evaluate candidate splits.
- Feature-threshold based binary splitting.
- A recursive tree builder with a `max_depth` stopping condition.
- A simple `Node` structure to store split rules or leaf predictions.
- Recursive prediction for single samples and batch prediction for datasets.

## Experiments & Observations
- Tested the implementation on the breast cancer dataset.
- Trained and evaluated trees across multiple depths from `1` to `10`.
- Compared train and test accuracy as depth increased.
- Printed the learned tree structure to inspect how the model was splitting the data.

Key observations:
- A shallow tree underfit the dataset because it could not model enough decision boundaries.
- Increasing depth improved performance at first, but the train accuracy rose faster than test accuracy, which is a typical sign that deeper trees can start overfitting.
- With `max_depth=5`, the notebook achieved about `95.6%` test accuracy.

## Key Learnings
- Information gain is very sensitive to how cleanly a split separates classes.
- Tree depth is one of the most important controls for the bias-variance tradeoff in Decision Trees.
- A recursive implementation is conceptually simple, but debugging split logic and stopping conditions requires care.
- Printing the final tree is useful for checking whether the learned rules are reasonable instead of treating the model like a black box.

## Challenges Faced
- Making sure the split masks correctly separated left and right subsets.
- Handling stopping conditions so recursion ends at pure nodes or the depth limit.
- Searching all unique thresholds can become expensive, even for a relatively small implementation.
- Preventing the tree from growing deeper than needed without losing too much predictive power.

## How to Run
1. Open `code.ipynb` in Jupyter Notebook or VS Code.
2. Run the cells in order.
3. The notebook will train the tree, plot depth vs accuracy, and print the learned tree structure.
