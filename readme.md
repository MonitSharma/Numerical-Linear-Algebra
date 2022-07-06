## Computational Linear Algebra for Coders

This course is focused on the question: How do we do matrix computations with acceptable speed and accurancy?

The course is taught in python with jupyter notebooks, using libraries like Scikit-learn and Numpy as well as Numba ( a library that compiles Python to C for faster performance) and PyTorch ( an alternative to Numpy for the GPU)


### Table of Contents

1. Why are we here?
    We start with a high level overview of some foundational concepts in numerical linear algebra.
    <li> Matrix and tensor products
    <li> Matrix Decompositions
    <li> Accuracy        
    <li> Memory Use
    <li> Speed 
    <li> Parallelization & vectorization

2. Topic Modeling with NMF and SVD 
   We will use the newsgroups datasets to try to identify the topics of different posts. We use a term-document matrix that represents the frequency of the vocabulary.
    <li> Topic Frequency - Inverse Document Frequency (TF-IDF)
    <li> Singular Value Decomposition (SVD)
    <li> Non-Negative Matrix Factorization (NMF)
    <li> Stochastic Gradient Descent (SGD)
    <li> Intro to PyTorch
    <li> Truncated SVD

3. Background Removal with Robust PCA
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

    
