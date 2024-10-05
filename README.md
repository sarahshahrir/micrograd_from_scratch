# Micrograd: Autograd Engine from Scratch
This repository contains my implementation of Andrej Karpathy's Micrograd tutorial. Micrograd is a minimalistic engine for backpropagation and automatic differentiation, which is used to implement and train neural networks from scratch. Through this project, I learned strengthened my foundations -- backrpopagation is essentially just an application of the chain rule in calculus.

## Overview
Micrograd is designed to provide an intuitive understanding of how backpropagation and automatic differentiation work behind the scenes in neural networks. This project breaks down complex concepts into simpler building blocks, all written in pure Python without any external dependencies like TensorFlow or PyTorch.

### Key Features
- Backpropagation: Implementation of the backward pass, allowing for automatic differentiation of scalar-valued functions.
- Neural Networks: A basic neural network model built using manually defined layers and activation functions.
- Minimalist Code: The entire project is implemented in under 100 lines of Python code, focusing on simplicity and clarity.

## Learnings
This project helped solidify my understanding of:
- How automatic differentiation enables training neural networks.
- The inner workings of backpropagation algorithms.
- How neural networks can be constructed manually with simple building blocks.

# Key Concepts Covered
### 1. Simple Function Example
- Implemented a basic function and plotted using `matplotlib`.
- The derivative (slope) was approximated with finite differences: $f'(x) = \frac{f(x+h) - f(x)}{h}$
### 2. Derivatives and Sensitiviity Analysis
- Through simple operations like `a * b + c`, calculated how sensitive the output was to small changes in variables, which is thed derivative with respect to that variable.
- Observes how a small bump in a variable affects the others.
### 3. Building a Value Object
- Created the `Value` class, which was central to building a computational graph and automatic differentiation.
- Key features included:
  - Tracking data and previous operations (_children).
  - Gradient accumulation through backpropagation.
  - Overloading mathematical operations (`+`, `-`, `*`, `/`, `**`) to propagate gradients. 
### 4. Activation Functions
- Implemented the hyperbolic tangent (tanh) activation function: $f'(x) = \frac{f(x+h) - f(x)}{h}$
- Backpropagation for `tanh`:
  The gradient was calculated as $1 - \tanh^2(x)$
### 5. Backpropagation in Computational Graphs
- Performed topological sorting of the nodes in the graph to ensure correct gradient computation when backpropagating.
- Learned that backpropagation is just applying the chain rule repeatedly across a graph of variables and operations.
- Gradient accumulation occurred in reverse order using a depth-first search to visit all dependent nodes.
### 6. Visualizing the Computational Graph
- Used `graphviz` to visualize the computational graph, showing how values and operations interacted during forward and backward passes.
### 7. Manual Gradient Calculation
- Manually verified gradients by applying the chain rule to small examples of neural network computations (i.e., linear combination of inputs, weights, and bias).
### 8. Neurons and Networks
- Built a `Neuron` class, representing a simple neural network neuron with learnable weights and bias.
- Performed forward and backward passes for a single neuron and plotted the resulting computations and gradients.
### 9. Comparison with PyTorch
- Re-implemented the same neural network neuron in PyTorch to observe the similarity in how gradients were calculated using automatic differentiation.
### 10. Towards a Neural Network Library
- This example laid the foundation for building a larger neural network library by stacking multiple neurons into layers and introducing an optimizer to update weights based on gradients.

# Acknowledgements
A big thank you to Andrej Karpathy for the amazing Micrograd tutorial and his contributions to making deep learning more accessible!
