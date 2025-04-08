# Enhanced-Loss-Function

dataset download link: https://www.kaggle.com/datasets/atulanandjha/lfwpeople


# Enhanced AM-Softmax Loss for Improved Feature Separation

This repository contains the project developed as part of the CSO 211 course by Group 20. The project focuses on improving the conventional AM-Softmax loss function by introducing modifications that enhance both intra-class compactness and inter-class separability.

## Overview

In tasks such as face recognition, where the differentiation between classes is critical, the standard AM-Softmax loss can be further optimized. This project presents two key enhancements:

- **Additional Margin:**  
  An additive margin is integrated into the loss function to enforce a larger angular separation between classes. This modification leads to more robust and distinctive feature representations, ensuring that samples from the same class are tightly clustered while those from different classes are well-separated.

- **Exponential Scaling Factor:**  
  An exponential scaling factor is applied to manage the loss function more effectively. This factor contributes to:
  - **Loss Reduction:** Minimizing the overall loss during training.
  - **Enhanced Feature Compactness:** Promoting tight clustering of intra-class features, which ultimately improves accuracy in classification tasks.

## Loss Function Overview

The modified loss function introduces a new factor \( M \), where:

\[
M = e^m
\]

The updated prediction function is:

\[
y_{\text{pred}} = y_{\text{true}} \times \frac{(y_{\text{pred}} - \text{margin})}{M} + (1 - y_{\text{true}}) \times y_{\text{pred}}
\]

And the final loss is defined as:

\[
L_a = - \frac{1}{n} \sum_{i=1}^{n} \frac{e^{s \cdot (\cos \theta_{y_i} - m)}}{e^{s \cdot (\cos \theta_{y_i} - m)} + \sum_{j=1, j \neq y_i}^{n} e^{s \cdot (\cos \theta_{j} + m)}}
\]

This formulation more effectively balances the need for both intra-class similarity and inter-class dissimilarity.

## Contributors

- **Yash Vashist** 

