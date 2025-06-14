# Enhanced Image Classification Through Evolutionary Optimization of Residual Networks

## Project Overview

This project evaluates multiple optimization techniques—GD, PSO, CMA-ES, and NSGA-II—to improve image classification accuracy using a lightweight ResNet-18 model on the CIFAR-10 dataset, focusing on optimizing its final layer and addressing challenges like vanishing gradients and overfitting.

## Problem Statement

Image classification using Convolutional Neural Networks (CNNs) often suffers from issues such as:
- **Overfitting** on small datasets  
- **Vanishing gradients** in deep architectures  
- High **computational cost** of optimization techniques  
- Difficulty in **hyperparameter tuning**

This project addresses these challenges by optimizing the final layer of **ResNet-18** using multiple strategies, including gradient-based and evolutionary approaches. The goal is to assess performance and generalization across different optimizers on a benchmark image classification task.

##  Methodology

###  Dataset

- **CIFAR-10**: 60,000 color images (32×32) across 10 classes
  - Training: 50,000 images
  - Testing: 10,000 images

### Model: ResNet-18

- 18-layer deep CNN
- Incorporates **residual (skip) connections** to tackle vanishing gradients
- Final layer has 5,130 parameters (5120 weights + 10 biases)

### ⚙ Optimization Algorithms

| Algorithm        | Accuracy (%) | Notes |
|------------------|--------------|-------|
| Gradient Descent | 80.09        | Best performance, fast convergence |
| PSO              | 60.71        | Faster than CMA-ES, but less accurate |
| CMA-ES           | 24.06        | Computationally expensive, stable improvement |
| NSGA-II          | 19.3         | Poor performance due to short run-time and trade-offs |

> **Loss Function**: Cross-Entropy  
> **Batch Size**: 128  
> **Epochs/Generations**: 50  

## Bi-Objective Optimization (NSGA-II)

- **Goals**: Maximize accuracy + Minimize Gaussian Regularization (prevent overfitting)
- Selected Pareto-optimal solutions
- Accuracy was lower due to limited computational resources and trade-offs not being necessary in this context

## Results

- **Gradient Descent** showed steep loss minimization early on
- **CMA-ES** had steady but slow improvement, suggesting potential for vanishing gradient reduction
- **NSGA-II** underperformed due to its multi-objective trade-offs not aligning with dataset needs

## Conclusion

- **Gradient Descent** is the most effective technique for optimizing ResNet-18 on CIFAR-10 in this study.
- While **CMA-ES** and **PSO** offer advantages in avoiding local minima or boosting stability, they are not as efficient or accurate under tight constraints.
- **NSGA-II** can be considered for scenarios where trade-offs are critical (e.g., fairness vs. accuracy).

## Repository Structure

├── notebooks/

│ ├── GradientDescent.ipynb # Training ResNet-18 with Gradient Descent

│ ├── PSO.ipynb # Optimization using Particle Swarm Optimization

│ ├── CMA_ES.ipynb # CMA-ES-based final layer optimization

│ ├── BiObj.ipynb # Multi-objective optimization using NSGA-II

│ └── Graph.ipynb # Visual analysis: accuracy/loss plots

├── README.md # Project overview and details
└── requirements.txt # Dependencies and libraries


## Author
**Shivasmi Sharma**  
Bioinformatics Analyst | MSc Data Science  
📧 Email: [shivasmisharma646@gmail.com](mailto:shivasmisharma646@gmail.com)  
🔗 LinkedIn: [linkedin.com/in/shivasmi-sharma](https://www.linkedin.com/in/shivasmi-sharma)  
🐙 GitHub: [github.com/shivasmi07](https://github.com/shivasmi07)

