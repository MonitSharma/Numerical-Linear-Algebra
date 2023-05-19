# Linear Algebra for Quantum Computing


![](https://tikz.net/files/vectors.gif)


This repository is aimed at providing an introduction to the basics of linear algebra and advanced computational numerical linear algebra with a focus on applications in quantum computing.


Quantum computing is a rapidly growing field that has the potential to revolutionize the way we process and analyze information. Linear algebra forms an essential part of the mathematical framework used in quantum computing. In this article, we will explore the role of linear algebra in quantum computing, including its importance in representing quantum states, quantum gates, and quantum algorithms.




## Quantum States
Quantum states are represented as vectors in a complex vector space. The state of a single qubit can be represented as a vector in a two-dimensional complex vector space, commonly denoted as $\mathbb{C}^2$. For example, the state $\ket{\psi}=\alpha\ket{0}+\beta\ket{1}$, where $\alpha,\beta\in\mathbb{C}$ and $|\alpha|^2+|\beta|^2=1$, can be represented as the vector 

$$\begin{pmatrix} \alpha \\\ \beta \end{pmatrix}$$


In quantum computing, the state of a qubit (a quantum bit) can be represented as a vector in a two-dimensional complex vector space, commonly denoted as $\mathbb{C}^2$. A qubit can exist in a superposition of two classical states, represented as $\ket{0}$ and $\ket{1}$, with probability amplitudes $\alpha$ and $\beta$, respectively. The state of the qubit can be represented as a linear combination of the basis states:

$$\ket{\psi}=\alpha\ket{0}+\beta\ket{1}$$


where $\alpha$,$\beta$ $\in\mathbb{C}$ and $|\alpha|^2+|\beta|^2=1$. The complex numbers $\alpha$ and $\beta$ are referred to as probability amplitudes, and the probability of measuring the qubit in state $\ket{0}$ or $\ket{1}$ is given by $|\alpha|^2$ and $|\beta|^2$, respectively. The state $\ket{\psi}$ is normalized such that the sum of the probabilities is equal to 1:

$$\braket{\psi|\psi}=\left(\alpha^\bra{0}+\beta^\bra{1}\right)\left(\alpha\ket{0}+\beta\ket{1}\right)=|\alpha|^2+|\beta|^2=1$$

where $\braket{\cdot|\cdot}$ denotes the inner product.

The state of $n$ qubits can be represented as a vector in a $2^n$-dimensional complex vector space, commonly denoted as $\mathbb{C}^{2^n}$. For example, the state of two qubits can be represented as a linear combination of the basis states $\ket{00}$, $\ket{01}$, $\ket{10}$, and $\ket{11}$:

$$\ket{\psi}=\alpha_{00}\ket{00}+\alpha_{01}\ket{01}+\alpha_{10}\ket{10}+\alpha_{11}\ket{11}$$

where $\alpha_{00}$, $\alpha_{01}$, $\alpha_{10}$, and $\alpha_{11}$ are complex probability amplitudes such that $|\alpha_{00}|^2+|\alpha_{01}|^2+|\alpha_{10}|^2+|\alpha_{11}|^2=1$. This state can be represented as a vector in $\mathbb{C}^4$:

$$\begin{pmatrix}\alpha_{00} \\ \alpha_{01} \\ \alpha_{10} \\ \alpha_{11}\end{pmatrix}$$

Similarly, the state of $n$ qubits can be represented as a vector in $\mathbb{C}^{2^n}$, where each element corresponds to a particular combination of classical states of the $n$ qubits.

The ability to represent quantum states as vectors in a complex vector space is one of the fundamental differences between classical and quantum computing. This representation allows for the use of linear algebraic techniques in the manipulation of quantum states, which is a powerful tool for quantum computing.


The state of $n$ qubits can be represented as a vector in a $2^n$-dimensional complex vector space, commonly denoted as $\mathbb{C}^{2^n}$. For example, the state $\ket{\psi}=\frac{1}{\sqrt{2}}\ket{00}+\frac{1}{\sqrt{2}}\ket{11}$ can be represented as the vector 

$$\begin{pmatrix}\frac{1}{\sqrt{2}} \\\ 0 \\\ 0 \\\ \frac{1}{\sqrt{2}} \end{pmatrix}$$


## Quantum Gates
Quantum gates are represented as unitary matrices. A unitary matrix $U$ is a complex square matrix such that $UU^\dagger=U^\dagger U=I$, where $U^\dagger$ denotes the conjugate transpose of $U$, and $I$ denotes the identity matrix. Unitary matrices preserve the norm of vectors, which is important for preserving the probabilities of quantum states.

A single-qubit gate can be represented as a $2\times2$ unitary matrix. For example, the Pauli-X gate, which flips the state of a qubit, is represented as the matrix 

$$\begin{pmatrix}0 & 1 \\\ 1 & 0 \end{pmatrix}$$ 

The Hadamard gate, which puts a qubit into a superposition state, is represented as the matrix 

$$\frac{1}{\sqrt{2}}\begin{pmatrix}1 & 1 \\\ 1 & -1\end{pmatrix}$$

A multi-qubit gate can be represented as a tensor product of single-qubit gates. For example, the Controlled-NOT (CNOT) gate, which flips the state of the second qubit if the first qubit is in the state $\ket{1}$, is represented as the matrix 

$$\begin{pmatrix}1 & 0 & 0 & 0 \\\ 0 & 1 & 0 & 0 \\\ 0 & 0 & 0 & 1 \\\ 0 & 0 & 1 & 0\end{pmatrix}$$

which is a tensor product of the identity matrix and the Pauli-X gate.



### Single-qubit Gates
Single-qubit gates operate on the state of a single qubit. The most commonly used single-qubit gates are the Pauli gates:

$$X = \begin{pmatrix}0 & 1 \\\ 1 & 0\end{pmatrix},\quad Y = \begin{pmatrix}0 & -i \\\ i & 0\end{pmatrix},\quad Z = \begin{pmatrix}1 & 0 \\\ 0 & -1\end{pmatrix}$$

The Pauli-X gate, also known as the NOT gate, flips the state of a qubit from $\ket{0}$ to $\ket{1}$ and vice versa. The Pauli-Y gate and Pauli-Z gate perform rotations around the Y and Z axes of the Bloch sphere, respectively.

Other commonly used single-qubit gates include the Hadamard gate:

$$H = \frac{1}{\sqrt{2}}\begin{pmatrix}1 & 1 \\\ 1 & -1\end{pmatrix}$$

which creates a superposition of the $\ket{0}$ and $\ket{1}$ states, and the phase gate:

$$S = \begin{pmatrix}1 & 0 \\\ 0 & i\end{pmatrix}$$

which introduces a phase shift of $\pi/2$ to the $\ket{1}$ state.


### Multi-qubit Gates
Multi-qubit gates operate on the state of two or more qubits. The most commonly used multi-qubit gate is the controlled-NOT (CNOT) gate:

$$\text{CNOT} = \begin{pmatrix}1 & 0 & 0 & 0 \\\ 0 & 1 & 0 & 0 \\\ 0 & 0 & 0 & 1 \\\ 0 & 0 & 1 & 0\end{pmatrix}$$

The CNOT gate flips the state of the target qubit if and only if the control qubit is in the $\ket{1}$ state. The CNOT gate is often used as a building block for more complex multi-qubit gates and quantum algorithms.

Another important multi-qubit gate is the SWAP gate:

$$\text{SWAP} = \begin{pmatrix}1 & 0 & 0 & 0 \\\ 0 & 0 & 1 & 0 \\\ 0 & 1 & 0 & 0 \\\ 0 & 0 & 0 & 1\end{pmatrix}$$

The SWAP gate exchanges the state of two qubits. The SWAP gate is a crucial component of many quantum algorithms, particularly those related to quantum error correction.


### Matrix Multiplication and Composition of Gates
Quantum gates are represented by unitary matrices, which are matrices that preserve the norm and inner product of quantum states. The composition of two quantum gates is equivalent to matrix multiplication of their corresponding unitary matrices. For example, the composition of two single-qubit gates $U$ and $V$ is given by the matrix multiplication $UV$, which represents a new single-qubit gate. Similarly, the composition of two multi-qubit gates is given by the matrix multiplication of their corresponding unitary matrices. The order of matrix multiplication is important, as quantum gates do not necessarily commute.

The ability to represent quantum gates as matrices and to compose them through matrix multiplication is one of the key advantages of using linear algebra in quantum computing. This allows for the efficient simulation and optimization of quantum circuits using linear algebraic techniques.


### Example: Quantum Teleportation Circuit
As an example of the use of quantum gates in quantum circuits, consider the quantum teleportation circuit. This circuit allows the transfer of an arbitrary qubit state from one qubit to another, without physically moving the qubit. The circuit consists of three qubits: the input qubit to be teleported, and two auxiliary qubits used to transfer the state.

The quantum teleportation circuit can be implemented using a combination of single-qubit gates and the CNOT gate. The circuit is shown below:

![](https://media.geeksforgeeks.org/wp-content/uploads/20210827125006/Screenshot20210827124930.jpg)

The first two qubits are entangled using a Hadamard gate and a CNOT gate, creating the Bell state $\frac{1}{\sqrt{2}}(\ket{00}+\ket{11})$. The input qubit is then combined with the first qubit using a CNOT gate, followed by a Hadamard gate on the input qubit. This prepares the input qubit in a state that is entangled with the second qubit. Finally, a measurement is performed on the first two qubits, and the results are used to perform a Pauli correction operation on the third qubit, which now contains the teleported state.

The quantum teleportation circuit is an example of the power of quantum gates and quantum circuits. By using a combination of simple gates, it is possible to perform complex quantum operations that would be impossible using classical computing techniques. The use of linear algebra in representing and manipulating quantum gates and circuits allows for the efficient simulation and optimization of these quantum systems, and is a key tool in the development of practical quantum algorithms and technologies.



## Quantum Algorithms

Quantum algorithms are represented as sequences of quantum gates applied to quantum states. The most famous quantum algorithm is Shor's algorithm, which can factor large numbers exponentially faster than classical algorithms. Shor's algorithm consists of three steps: preparing the input state, applying the quantum Fourier transform, and measuring the output state. The quantum Fourier transform is represented as a sequence of Hadamard gates and controlled-phase gates.

Another famous quantum algorithm is Grover's algorithm, which can search an unsorted database with $N$ items in $\mathcal{O}(\sqrt{N})$ time. Grover's algorithm consists of two steps: preparing the input state and applying the Grover iteration. The Grover iteration is represented as a sequence of single-qubit rotations and a multi-qubit oracle.


Quantum algorithms are a key application of quantum computing. These algorithms take advantage of the unique properties of quantum mechanics to perform certain calculations faster than is possible with classical computing techniques.

One of the most famous quantum algorithms is Shor's algorithm, which allows for the efficient factorization of large integers. This has significant implications for cryptography, as many modern encryption schemes rely on the difficulty of factoring large numbers.

Another important quantum algorithm is Grover's algorithm, which provides a quadratic speedup for unstructured search problems. This algorithm has applications in data mining, optimization, and other areas of computer science.

The implementation of quantum algorithms involves designing quantum circuits that perform the necessary operations. These circuits can be represented and manipulated using linear algebraic techniques, such as matrix multiplication and tensor products.

For example, the quantum Fourier transform (QFT) is a key component of Shor's algorithm, and can be represented as a matrix multiplication operation. The QFT is defined by the following equation:

$$ \text{QFT}N\ket{j}=\frac{1}{\sqrt{N}}\sum{k=0}^{N-1}e^{2\pi ijk/N}\ket{k} $$

where $\ket{j}$ is a quantum state with $N$ basis states, and $\text{QFT}_N$ is the quantum Fourier transform. The QFT can be implemented using a circuit composed of Hadamard gates and phase shift gates, and can be efficiently computed using linear algebraic techniques.

In addition to designing quantum algorithms, it is also important to understand their limitations. Quantum computers are not a panacea for all computational problems, and certain problems may not benefit from quantum algorithms. Additionally, the implementation of quantum algorithms requires the ability to control and manipulate individual qubits, which can be challenging due to noise and other sources of error.

Despite these challenges, quantum algorithms have the potential to revolutionize fields such as cryptography, optimization, and machine learning, and are a key area of research in the development of practical quantum technologies.

-----

## [Introduction to Linear Algebra](https://github.com/MonitSharma/Numerical-Linear-Algebra/tree/main/Basic%20Numerical%20Linear%20Algebra)
This section of the repository will cover the basics of linear algebra. It will include topics such as vectors, matrices, linear transformations, and eigenvalues/eigenvectors. The content will be presented in a way that is accessible to beginners, with examples and exercises to solidify understanding.


![](https://tikz.net/files/reference_frame_rotational.gif)

| Serial Number | Title                                     | Description                                         | Links     | Medium                                                                                |
| ------------- | ----------------------------------------- | --------------------------------------------------- | ----------------------------------------------------------------------------------------- |------------------------------------|
| 1             | Scalars, vectors, matrices and tensors    | Introduction to basic concepts in linear algebra    | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://github.com/MonitSharma/Numerical-Linear-Algebra/blob/main/Basic%20Numerical%20Linear%20Algebra/1-Scalars%2C_Vectors%2C_Matrices_and_Tensors.ipynb) |  [![Medium](https://img.shields.io/badge/Medium-12100E?style=for-the-badge&logo=medium&logoColor=white)](https://medium.com/@_monitsharma/computational-linear-algebra-scalars-vectors-matrices-and-tensors-50e392df9ccc) |
| 2             | Multiplying matrices and vectors          | Understanding how matrix multiplication works       | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://github.com/MonitSharma/Numerical-Linear-Algebra/blob/main/Basic%20Numerical%20Linear%20Algebra/2-Multiplying_Matrices_and_Vectors.ipynb) | [![Medium](https://img.shields.io/badge/Medium-12100E?style=for-the-badge&logo=medium&logoColor=white)](https://medium.com/@_monitsharma/computational-linear-algebra-multiplication-and-identity-a2391370d713) |
| 3             | Identity and inverse matrices             | Explanation of identity and inverse matrices        | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://github.com/MonitSharma/Numerical-Linear-Algebra/blob/main/Basic%20Numerical%20Linear%20Algebra/3-Identity_and_Inverse_Matrices.ipynb) |[![Medium](https://img.shields.io/badge/Medium-12100E?style=for-the-badge&logo=medium&logoColor=white)](https://medium.com/@_monitsharma/computational-linear-algebra-multiplication-and-identity-a2391370d713) |
| 4             | Linear dependence and span                 | Understanding linear dependence and span of vectors | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://github.com/MonitSharma/Numerical-Linear-Algebra/blob/main/Basic%20Numerical%20Linear%20Algebra/4-Linear_Dependence_and_Span.ipynb) | [![Medium](https://img.shields.io/badge/Medium-12100E?style=for-the-badge&logo=medium&logoColor=white)](https://medium.com/@_monitsharma/computational-linear-algebra-linear-dependence-and-span-62fc0393d247) |
| 5             | Norms                                     | Definition and examples of vector norms             | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://github.com/MonitSharma/Numerical-Linear-Algebra/blob/main/Basic%20Numerical%20Linear%20Algebra/5-Norms.ipynb) |
| 6             | Special kind of matrices                   | Introduction to special types of matrices           | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://github.com/MonitSharma/Numerical-Linear-Algebra/blob/main/Basic%20Numerical%20Linear%20Algebra/6-Special_Kind_of_Matrices_and_Vectors.ipynb) |
| 7             | Eigendecomposition                         | Understanding eigenvectors and eigenvalues          | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://github.com/MonitSharma/Numerical-Linear-Algebra/blob/main/Basic%20Numerical%20Linear%20Algebra/7-Eigendecomposition.ipynb) |
| 8             | Singular value decomposition               | Introduction to singular value decomposition        | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://github.com/MonitSharma/Numerical-Linear-Algebra/blob/main/Basic%20Numerical%20Linear%20Algebra/8-Singular_Value_Decomposition.ipynb) |
| 9             | The Moore-Penrose pseudoinverse            | Definition and applications of the pseudoinverse    | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://github.com/MonitSharma/Numerical-Linear-Algebra/blob/main/Basic%20Numerical%20Linear%20Algebra/9-The_Moore_Penrose_Pseudoinverse.ipynb) |
| 10            | The trace operator                        | Definition and properties of the trace operator    | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://github.com/MonitSharma/Numerical-Linear-Algebra/blob/main/Basic%20Numerical%20Linear%20Algebra/10-The_Trace_Operator.ipynb) |
| 11            | The determinant                           | Explanation of the determinant of a matrix         | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://github.com/MonitSharma/Numerical-Linear-Algebra/blob/main/Basic%20Numerical%20Linear%20Algebra/11-The_Determinant.ipynb) |




----

## [Advanced Computational Numerical Linear Algebra](https://github.com/MonitSharma/Numerical-Linear-Algebra/tree/main/Advanced%20Numerical%20Linear%20Algebra)
This section of the repository will cover advanced topics in computational numerical linear algebra. It will include topics such as singular value decomposition (SVD), QR decomposition, and LU decomposition. The content will be presented with a focus on their applications in quantum computing, and will include exercises and projects to solidify understanding.


![](https://tikz.net/janosh/tori.png)



| Serial Number | Title                                | Description                                                           | Links                                                                                     |
| ------------- | ------------------------------------ | --------------------------------------------------------------------- | ----------------------------------------------------------------------------------------- |
| 1             | Introduction to matrices             | Overview of matrices and their properties, operations, and applications | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://github.com/MonitSharma/Numerical-Linear-Algebra/blob/main/Advanced%20Numerical%20Linear%20Algebra/week_1_introduction_to_matrices.ipynb) |
| 2             | Singular Value Decomposition         | Introduction to singular value decomposition and its applications     | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://github.com/MonitSharma/Numerical-Linear-Algebra/blob/main/Advanced%20Numerical%20Linear%20Algebra/week_2_singular_value_decomposition.ipynb) |
| 3             | Topic Modelling with NMF              | Explanation of Non-negative Matrix Factorization for topic modeling  | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://github.com/MonitSharma/Numerical-Linear-Algebra/blob/main/Advanced%20Numerical%20Linear%20Algebra/week_3_topic_modeling_with_NMF_and_SVD.ipynb) |
| 4             | Background Removal                   | Techniques for removing the background from images using linear algebra | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://github.com/MonitSharma/Numerical-Linear-Algebra/blob/main/Advanced%20Numerical%20Linear%20Algebra/week_4_background_removal_with_robust_PCA.ipynb) |
| 5             | Compressed Sensing CT scans           | Using compressed sensing for faster and more efficient CT scans      | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://github.com/MonitSharma/Numerical-Linear-Algebra/blob/main/Advanced%20Numerical%20Linear%20Algebra/week_5_compressed_sensing_CT_scans_robust_regression.ipynb) |
| 6             | Health outcomes with linear algebra  | Applications of linear algebra in healthcare and medical research   | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://github.com/MonitSharma/Numerical-Linear-Algebra/blob/main/Advanced%20Numerical%20Linear%20Algebra/week_6_health_outcomes_with_linear_regression.ipynb) |
| 7             | Linear regression                    | Introduction to linear regression and its applications               | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://github.com/MonitSharma/Numerical-Linear-Algebra/blob/main/Advanced%20Numerical%20Linear%20Algebra/week_7_how_to_implement_linear_regression.ipynb) |
| 8             | Page rank with eigen decomposition   | Explanation of PageRank algorithm using eigendecomposition            | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://github.com/MonitSharma/Numerical-Linear-Algebra/blob/main/Advanced%20Numerical%20Linear%20Algebra/week_8_page_rank_with_eigen_decomposition.ipynb) |




-----


## [Applications in Quantum Computing](https://github.com/MonitSharma/Qiskit-Hindi-Tutorials/blob/main/qiskit_hindi_basic_gates_part2.ipynb)

![](https://tikz.net/files/complex.gif)


This section of the repository will cover the applications of linear algebra and computational numerical linear algebra in quantum computing. It will include topics such as quantum gates, quantum circuits, and quantum algorithms. The content will be presented in a way that is accessible to beginners, with examples and exercises to solidify understanding. This will be covered in detail in another repository.


----


## Getting Started
These instructions will get you a copy of the project up and running on your local machine for development and testing purposes.

----


## Prerequisites
This project requires Python 3.x and Jupyter Notebook. You can install Python from the official Python website and Jupyter Notebook can be installed using the following command:


```python
pip install jupyter
```

----


## Installation
To get started, simply clone the repository:

```python
git clone https://github.com/MonitSharma/Numerical-Linear-Algebra.git
```

-----


## Usage
You will find the content organized into directories according to the topics covered in this repository. The examples and exercises are provided in Jupyter notebooks that can be run on your local machine. To run the Jupyter notebooks, navigate to the directory containing the notebooks and type the following command in the terminal:

```python
jupyter notebook
```

This will start the Jupyter Notebook server and open a web page in your browser. Click on the notebook you want to open and start exploring the content.


-----


## Contributing
Contributions are welcome! Please feel free to open an issue if you find a bug or have a suggestion for improvement. Pull requests are also welcome.

-----


## License
This repository is licensed under the MIT License.

------


## Acknowledgements
We would like to thank the following resources for their contribution to this repository:

1. Linear Algebra - Khan Academy
2. Numerical Linear Algebra for Coders - Fast.ai
3. Quantum Computing for the Very Curious - IBM
