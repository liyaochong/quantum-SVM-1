# quantum-SVM
The quantum circuit version of support vector machine to recognize handwritten 6 and 9 using python's package QuTip.

Demonstation for results:

![Alt text](./demo_4.png?raw=true "Title") ![Alt text](./demo_other_4.png?raw=true "Title")

Features are chosen as the vertical ratio and the horizontal ratio, calculated from the pixels on the left (upper) half over the right (lower) half. Thus features are two-dimensional vectors. The training data are only two printed images of the standard fonts, which are represented by x1=(0.987, 0.159) for character 6 and x2 = (0.354, 0.935) for character 9. The 8 test data comes from reference 1, which is a subset of https://github.com/damiles/basicOCR. 

The task for a classical SVM is to construct a hyperplane with w·x+b=0 so that w·x_i+b≥1 for x_i in the positive class, and w· x_i+b≤−1 for x_i in the negative class. The optimization objective is to find the optimal hyperplane which could maximize the distance between two classes.

To encode the two training vectors into the qubits, we used two quantum gates, where each one of them rotates a qubit about Y-axis to a certain degree. The process of optimizing the hyperplane parameters is done by calculating the matrix inversion. At last, we read some matrix elements for the total quantum circuit to distinguish 6 and 9.

![Alt text](./circuit.png?raw=true "Title")

QuTip is a widely used python package for quantum mechanics and quantum information. After installing QuTip, the files "circuit.py and gates.py" in folder qutip/models are replaced by the corresponding files in this repository.

One possible application that I'm interested in is to further apply this QSVM to dataset MNIST. A more interesting future direction is adapting kernel function so that QSVM can be used to classify data which are not linearly separable.


Reference:
1) Li, Zhaokai, et al. "Experimental realization of a quantum support vector machine." Physical review letters 114.14 (2015): 140504. ( the main reference that I used.)

2) Rebentrost, Patrick, Masoud Mohseni, and Seth Lloyd. "Quantum support vector machine for big data classification." Physical review letters 113.13 (2014): 130503. (The original theoretical paper which doesn't contain the kernel trick.)

This repository also contains my PowerPoint for an introduction to quantum programming software, which contains 3 parts:1) elementary quantum algorithms in Quipper; 2) QSVM 3) classical simulation of boson sampling. If you're interested, don't forget to check it out. :P

Anyway, I'm very happy to answer any questions or discuss some possible further improvements. :) 

Jinlong(Darius) Huang
