# Face-Recognition

This is a face recognition model implemented using various dimensionality reduction and classification techniques, including PCA, LDA, Kernel PCA, QDA, and rLDA, followed by the KNN algorithm for face identification.
---

### Table of Contents

- [Introduction](#introduction)
- [Contributers](#Contributers)
- [Dataset](#dataset)
- [Implementation Details](#implementation-details)
- [Conclusion](#conclusion)

## Introduction

We intend to perform face recognition. Face recognition means that for a given image 
you can tell the subject id. Our database of subject is very simple. It has 40 subjects. 
Below we will show the needed steps to achieve the goal of the assignment.

## Contributers
* [Patrick Georges](https://github.com/Patrick-Geo7)
* [Adel Mahmoud](https://github.com/Adel-Mahmoud-Mohamed)
* [Mahmoud Attia](https://github.com/mahmoudattia12)

## Dataset

The ORL dataset is used for this project, which contains 10 images per subject. Each image is a grayscale image of size 92x112 pixels. You can access the dataset from [here](https://www.kaggle.com/kasikrit/att-database-of-faces/).

## Implementation Details

### 1. Data Preprocessing

- Conversion of images into a vector format of size 10304.
- Creation of the Data Matrix (D) and Label Vector (y).

### 2. Dimensionality Reduction

- Principle Component Analysis (PCA), Linear Discriminant Analysis (LDA), Kernel PCA, Quadratic Discriminant Analysis (QDA), and Regularized Linear Discriminant Analysis (rLDA) are employed for dimensionality reduction.
- PCA is explored with different values of alpha to find the optimal reduction.
- Kernel PCA is implemented with varying degrees to evaluate its effectiveness.
- Comparison between PCA, Kernel PCA, LDA, QDA, and rLDA for dimensionality reduction.

### 3. Classification

- K-Nearest Neighbors (KNN) classification is utilized.
- Various values of k are tested to determine optimal classification accuracy.
- Comparison of PCA and LDA for classification accuracy.

### 4. Handling Non-Faces

- Experimentation with non-face images to evaluate model robustness.
- Comparison of different techniques for face vs. non-face classification.

### 5. Bonus Part: Other variations to PCA and LDA

#### Introduction
In this bonus part, we explore additional variations of PCA and LDA beyond the original algorithms. Specifically, we implement Kernel PCA as an extension of PCA and compare it to the original PCA algorithm. Furthermore, we utilize Quadratic Discriminant Analysis (QDA) and Regularized Linear Discriminant Analysis (rLDA) as variations of LDA and compare them to the traditional LDA approach.

#### Kernel PCA vs. PCA
- **Kernel PCA**: Kernel PCA is an extension of PCA that allows for non-linear dimensionality reduction. It can capture non-linear relationships by implicitly mapping the data into a higher-dimensional space using a kernel function.
- **PCA**: Principal Component Analysis is a linear dimensionality reduction technique that aims to find the orthogonal directions (principal components) along which the data varies the most.

###### Time Complexity Comparison:
- **PCA**: \( O(nd^2 + d^3) \)
- **Kernel PCA**: \( O(n^2d + n^3) \)

###### Accuracy Comparison:
- PCA:
  - Suitable for linear relationships.
  - Limited capability to capture non-linear structures.
- Kernel PCA:
  - Suitable for non-linear relationships.
  - Captures non-linear structures effectively.

#### Quadratic Discriminant Analysis (QDA) vs. Linear Discriminant Analysis (LDA)
- **QDA**: Assumes that the class-conditional densities of the features follow multivariate Gaussian distributions, with each class potentially having its own covariance matrix.
- **LDA**: Assumes a shared covariance matrix for all classes.

###### Time Complexity Comparison:
- Both algorithms have a time complexity of approximately \( O(nd^2 + d^3) \), but QDA may involve additional computations due to the estimation of separate covariance matrices for each class.

###### Accuracy Comparison:
- QDA:
  - Allows for more flexibility in capturing complex relationships within each class.
  - Requires sufficient data to estimate class-specific covariance matrices accurately.
- LDA:
  - Assumes a shared covariance matrix across classes, which may not capture class-specific variations as effectively as QDA.

#### Regularized Linear Discriminant Analysis (rLDA) vs. Linear Discriminant Analysis (LDA)
- **rLDA**: An extension of LDA that incorporates regularization techniques to improve stability and generalization, especially in high-dimensional or noisy datasets.
- **LDA**: Traditional Linear Discriminant Analysis without regularization.

###### Time Complexity Comparison:
- Both rLDA and LDA have a time complexity of approximately \( O(nd^2 + d^3) \), but rLDA may involve additional computations due to the regularization step.

###### Accuracy Comparison:
- rLDA:
  - Offers improved stability and generalization, particularly in high-dimensional or noisy datasets.
  - Balances between fitting the data well and maintaining stability through regularization.
- LDA:
  - May suffer from overfitting or instability in certain scenarios, especially when dealing with collinear features or limited sample sizes.

#### Results
- Kernel PCA is effective for capturing non-linear relationships, while PCA is suitable for linear relationships.
- QDA provides more flexibility in modeling complex relationships within each class compared to LDA.
- rLDA offers improved stability and generalization over LDA, especially in challenging datasets.


## Conclusion

This project demonstrates the application of various dimensionality reduction and classification techniques for face recognition tasks. By exploring methods like PCA, LDA, Kernel PCA, and QDA, we gain insights into their effectiveness and computational efficiency. The implementation details and results are provided in the colab notebook for further analysis and experimentation.
