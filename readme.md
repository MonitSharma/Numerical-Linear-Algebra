# Computational Linear Algebra for Coders

This course is focused on the question: How do we do matrix computations with acceptable speed and accurancy?

The course is taught in python with jupyter notebooks, using libraries like Scikit-learn and Numpy as well as Numba ( a library that compiles Python to C for faster performance) and PyTorch ( an alternative to Numpy for the GPU)


## Table of Contents

### 1. [Why are we here?](https://github.com/MonitSharma/Numerical-Linear-Algebra/blob/main/week_1_introduction_to_matrices.ipynb)

We start with a high level overview of some foundational concepts in numerical linear algebra.
<li> Matrix and tensor products
<li> Matrix Decompositions
<li> Accuracy        
<li> Memory Use
<li> Speed 
<li> Parallelization & vectorization

### 2. Topic Modeling with NMF and SVD 

We will use the newsgroups datasets to try to identify the topics of different posts. We use a term-document matrix that represents the frequency of the vocabulary.
<li> Topic Frequency - Inverse Document Frequency (TF-IDF)
<li> Singular Value Decomposition (SVD)
<li> Non-Negative Matrix Factorization (NMF)
<li> Stochastic Gradient Descent (SGD)
<li> Intro to PyTorch
<li> Truncated SVD

### 3. Background Removal with Robust PCA

Another application og SVD is to identify the people and remove the background of a surveillance video. We will cover robust PCA, which uses randomized SVD which in turn uses the LU factorization

<li> Load and View Video Data  
<li> SVD 
<li> Principal Component Analysis
<li> L1 Norm induces Sparsity
<li> Robust PCA
<li> LU Factorization
<li> Stability of LU
<li> LU factorization with Pivoting
<li> History of Gaussian Elimination
<li> Block Matrix Multiplication 


### 4. Compressed Sensing with Robust Regression

Compressed sensing is critical to allowing CT scans with lower radiation-- the image can be reconstructed with less data. Here we will learn the technique and apply it to CT images.

<li> Broadcasting
<li> Sparse Matrices
<li> CT Scans and Compressed Sensing
<li> L1 and L2 regression


### 5. Predicting Health Outcomes with Linear Regressions

<li> Linear Regression in sklearn
<li> Polynomial Features
<li> Speeding up with Numba
<li> Regularization and Noise


### 6. How to Implement Linear Regression?

<li> How did Scikit learn to do it?
<li> Naive Solution
<li> Normal equation and Cholesky factorization
<li> QR Factorization
<li> SVD
<li> Timing Comparison
<li> Conditioning and Stability
<li> Full vs Reduced Factorization
<li> Matrix Inversion is Unstable



### 7. Page Rank with Eigen Decompositon

We have applied SVD to topic modeling, background removal, and linear regression. SVD is intimately connected to the eigen decomposition, so we will now learn how to calculate eigenvalues for a large matrix. We will use DBpedia data, a large dataset of Wikipedia links, because here the principal eigenvector gives the relative importance of different Wikipedia pages (this is the basic idea of Google's PageRank algorithm). We will look at 3 different methods for calculating eigenvectors, of increasing complexity (and increasing usefulness!)

<li> SVD
<li> DBpedia Dataset
<li> Power Method
<li> QR algorithm
<li> Two-Phase Approach to find eigen values
<li> Arnoldi Iteration



### 8. Implementing QR Factorization

<li> Gram-Schmidt
<li> House Holder
<li> Stability Examples



    
