# Linear Regression From Scratch

This folder contains a from-scratch implementation of Linear Regression using Python and NumPy. Linear Regression models the relationship between input features and a continuous target value. It is widely used for forecasting, trend analysis, price prediction, and as a foundation for understanding optimization in machine learning.

## What I Implemented
- Prediction using `y = Xw + b`.
- Mean squared error (MSE) cost function.
- Gradient descent updates for weights and bias.
- Single-feature and multi-feature regression training loops.
- Feature scaling for multi-feature training.
- Train/test splitting and evaluation with MSE and R2 score.
- Stochastic Gradient Descent (SGD) and Mini-batch Gradient Descent.
- L2 and L1 regularization experiments.

## Experiments & Observations
- Started with a single-feature model using `TotalBsmtSF` to predict house prices.
- Compared feature correlations with `SalePrice` and expanded to multiple features: `TotalBsmtSF`, `YearBuilt`, and `YearRemodAdd`.
- Trained models with batch gradient descent, SGD, and mini-batch gradient descent.
- Plotted cost curves to observe convergence behavior.
- Evaluated a train/test split and computed an `R2` score.
- Explored L2 regularization and then added a synthetic noisy feature before testing L1 regularization.

Key observations:
- The single-feature model learned, but multi-feature training gave a noticeably better fit after scaling.
- Feature normalization made gradient descent much more stable for the multi-feature setup.
- The final train/test experiment reported an `R2` score of about `0.566`, showing the model captured part of the price variation but not all of it.
- SGD and mini-batch updates converged differently from batch gradient descent and showed noisier cost trajectories.
- The L1 regularization experiment was useful for checking how the model behaves when an irrelevant feature is introduced.

## Key Learnings
- Learning rate choice is tightly connected to feature scaling; without scaling, training can become unstable or extremely slow.
- Comparing batch, stochastic, and mini-batch updates makes optimization behavior much easier to understand than reading about it in theory.
- Correlation is a helpful starting point for feature selection, but it does not guarantee a complete model.
- Regularization becomes much more intuitive when you test it against noisy or weak features instead of only clean inputs.
- A decent-looking training curve does not automatically mean strong generalization, which is why a held-out test set matters.

## Challenges Faced
- Using a very small learning rate for the unscaled single-feature setup to avoid unstable updates.
- Re-initializing parameters correctly between optimization experiments.
- Scaling features using only training statistics before evaluating on test data.
- Keeping the regularization experiments consistent after adding an extra synthetic feature.

## How to Run
1. Open `code.ipynb` in Jupyter Notebook or VS Code.
2. Run the notebook cells in order.
3. The notebook will load the dataset, train multiple regression variants, and plot optimization and regularization behavior.
