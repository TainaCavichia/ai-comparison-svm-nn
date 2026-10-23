# ai-comparison-svm-nn

This repository contains a practical, math-first implementation of two of the most iconic algorithms in Artificial Intelligence: Support Vector Machines (SVM) and Artificial Neural Networks (ANN). 

The main objective of this project is to apply both models to the MNIST dataset (handwritten digit classification from 0 to 9) to analyze and compare their performance, building everything from scratch using only NumPy and Pandas.

---

## Project Highlights

Unlike projects that rely on out-of-the-box libraries like scikit-learn, TensorFlow, or PyTorch, this code was built by translating mathematical equations directly into linear and matrix programming logic:
- **No ML Frameworks:** All optimization and linear algebra are solved natively using NumPy array operations.
- **Conceptual Focus:** Clean, well-commented code designed to demonstrate the inner workings of optimization algorithms and cost functions.

---

## Implemented Models

### 1. Linear Support Vector Machine (SVM)
- **Multi-Class Approach:** One-vs-One (OvO) strategy, training an ensemble of 45 independent binary classifiers to cover the 10 classes of MNIST.
- **Optimization:** Stochastic Gradient Descent (SGD) with refined update mechanisms.
- **Cost Function:** Hinge Loss with L2 Regularization for geometric margin maximization.

### 2. Neural Network (Single-Layer Perceptron)
- **Architecture:** A single-layer Perceptron network connecting the 784 input features (pixels) directly to the 10 output neurons (one for each digit).
- **Core Algorithm:** Weight adjustment via Gradient Descent applied to the output layer.
- **Activation and Cost:** Output processed via the Softmax function to generate probabilities and optimized using Cross-Entropy Loss.

---

## Optimization Techniques (Training Enhancements)

To accelerate convergence and ensure high accuracy on MNIST, both models were enhanced with:
- **Mini-batch Gradient Descent:** Training is performed neither sample-by-sample nor on the full dataset at once. Data is processed in mini-batches, balancing mathematical stability and computational speed.
- **Learning Rate Decay:** Gradual and scheduled reduction of the learning rate across epochs. This allows the models to take large steps early in training and refined steps later, preventing weights from oscillating indefinitely away from the optimal convergence point.

---

## Execution Pipeline

1. **Data Loading and Manipulation:** Reading and structuring pixel matrices with Pandas.
2. **Preprocessing:** Z-score normalization to ensure numerical stability and rapid gradient convergence.
3. **Optimized Training:** Executing the epoch training loop using mini-batches and learning rate decay.
4. **Evaluation:** Generating accuracy metrics and confusion matrices to identify major prediction failure modes (e.g., confusing the digit 4 with 9).

---

## Technologies Used

- Python (Base language)
- NumPy (Numerical computing, matrices, and linear algebra)
- Pandas (Dataset structuring and loading)
