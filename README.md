# pca-svd-image-compression
Image compression and denoising using Singular Value Decomposition (SVD) and Principal Component Analysis (PCA)

This project explores image compression, reconstruction, and denoising using **Singular Value Decomposition (SVD)** and **Principal Component Analysis (PCA)**.

A grayscale image is represented as a numerical matrix, allowing linear algebra techniques to be applied directly to image processing.

## Project Overview

The project consists of two main experiments:

1. **SVD Image Compression**

   * Convert an image to grayscale.
   * Apply Singular Value Decomposition.
   * Reconstruct the image using rank-\(k\) approximations.
   * Compare reconstruction quality for different ranks.
   * Measure reconstruction error using the Frobenius norm.

2. **PCA Reconstruction and Denoising**

   * Add Gaussian random noise to the original image.
   * Center the noisy image.
   * Apply SVD to the centered data as part of PCA.
   * Reconstruct the image using different numbers of principal components.
   * Compare image quality and relative reconstruction error.

## Methods

The Singular Value Decomposition of an image matrix \(A\) is

$$
A = U\Sigma V^T.
$$

A rank-\(k\) approximation is obtained by retaining only the first \(k\) singular values and corresponding singular vectors:

$$
A_k = \sum_{i=1}^{k} \sigma_i u_i v_i^T.
$$

The project compares the following ranks:

* 5
* 10
* 20
* 50
* 100

Reconstruction quality is measured using relative Frobenius error:

$$
\frac{\|A-A_k\|_F}{\|A\|_F}.
$$

## Results

For SVD compression, increasing the rank produces clearer reconstructions and lower relative error.

For PCA reconstruction, lower-rank approximations remove more noise but also lose image detail. In the experiment:

* **Rank 50** provided a strong visual balance between smoothness and detail.
* **Rank 100** achieved the lowest numerical reconstruction error among the tested PCA ranks.

These results demonstrate the trade-off between dimensionality reduction, reconstruction accuracy, and noise removal.

## Technologies

* Python
* NumPy
* Pandas
* Matplotlib
* Pillow
* Google Colab

## Files

* `PCA_and_SVD_Image_Compression.ipynb` — complete analysis and implementation
* `MathClass.png` — input image used in the experiment

## Key Concepts

* Singular Value Decomposition (SVD)
* Principal Component Analysis (PCA)
* Low-rank matrix approximation
* Dimensionality reduction
* Image compression
* Image denoising
* Frobenius norm
