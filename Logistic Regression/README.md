# Logistic Regression From Scratch

This folder contains a from-scratch implementation of Logistic Regression using Python and NumPy. Logistic Regression is a binary classification algorithm that models class probability using the sigmoid function. It is commonly used in churn prediction, medical risk screening, fraud detection, and other problems where the output is a yes/no decision.

## What I Implemented
- Sigmoid activation for converting linear scores into probabilities.
- Probability prediction and class prediction with a configurable threshold.
- Binary cross-entropy loss with clipping for numerical stability.
- Gradient descent updates for weights and bias.
- Manual evaluation using accuracy, precision, recall, and confusion matrix counts.
- Threshold-based comparison to study precision-recall tradeoffs.

## Experiments & Observations
- Started with a small 2D toy dataset to visualize the decision boundary.
- Trained the model on an employee turnover dataset.
- Standardized the input features before optimization.
- Monitored loss reduction over epochs during training.
- Evaluated the test set using accuracy, precision, recall, and a confusion matrix.
- Compared predictions at thresholds `0.3`, `0.5`, and `0.7`.

Key observations:
- The training loss decreased steadily, which showed that the gradient updates were working as intended.
- On the employee turnover dataset, the notebook reported about `85.9%` accuracy.
- At threshold `0.3`, recall increased strongly but precision dropped.
- At threshold `0.7`, precision increased but recall decreased, which clearly showed the tradeoff introduced by the decision threshold.

## Key Learnings
- Logistic Regression is linear in feature space, but threshold choice changes the model's practical behavior a lot.
- Probability outputs are more informative than hard labels when you want to reason about false positives and false negatives.
- Feature scaling helps gradient descent converge more smoothly on real tabular data.
- Looking only at accuracy can hide useful information that precision, recall, and the confusion matrix make visible.
- Building the loss and gradient updates manually makes the connection between optimization and classification much clearer.

## Challenges Faced
- Preventing numerical issues in the log-loss calculation by clipping predicted probabilities.
- Verifying that the gradient formulas for `dw` and `db` were implemented correctly.
- Interpreting threshold effects beyond a single accuracy number.
- Separating the simple visualization example from the full employee-turnover training workflow.

## How to Run
1. Open `code.ipynb` in Jupyter Notebook or VS Code.
2. Run the cells sequentially.
3. The notebook will first show a small visual example, then train and evaluate Logistic Regression on the employee turnover dataset.
