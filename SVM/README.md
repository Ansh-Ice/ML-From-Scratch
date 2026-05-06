# 📈 Support Vector Machine (SVM) from Scratch using NumPy

This project implements a **Linear Support Vector Machine (SVM)** from scratch using only **NumPy**, without relying on libraries like scikit-learn.

The goal is to deeply understand:
- Maximum Margin Principle
- Hinge Loss
- Gradient Descent Optimization
- Support Vectors

---

## 🧠 What is SVM?

Support Vector Machine (SVM) is a supervised learning algorithm used for classification.

Instead of just separating data, SVM finds a boundary that:
> **Maximizes the margin between two classes**

---

## 📊 Dataset

We generate a simple synthetic dataset:

- Class +1 → centered around `(2, 2)`
- Class -1 → centered around `(-2, -2)`

This creates a linearly separable dataset ideal for understanding SVM.

---

## ⚙️ Implementation Steps

### 1. Initialize Parameters

- Weights `w`
- Bias `b`
- Learning rate
- Regularization parameter `λ`

---

### 2. Hinge Loss

SVM uses hinge loss defined as:
Loss = max(0, 1 - y(w·x + b))

This ensures:
- Correct classification
- Large margin

---

### 3. Gradient Descent

We optimize:

0.5 * ||w||² + λ * hinge_loss

Using **Batch Gradient Descent**:

- Compute gradients over all samples
- Update `w` and `b` once per epoch

---

### 4. Decision Boundary

The hyperplane is defined as:
w·x + b = 0

Margins:
w·x + b = +1
w·x + b = -1

---

### 5. Support Vectors

Support vectors are the points:
