---
layout:      project
title:       FFBP Neural Network
date:        2023-03-01
image:
  path:       /assets/img/projects/ffbpnn/NNarchDataflow_diagram_1920w.png
  srcset:
    1920w:   /assets/img/projects/ffbpnn/NNarchDataflow_diagram_1920w.png
    960w:    /assets/img/projects/ffbpnn/NNarchDataflow_diagram_960w.png
    480w:    /assets/img/projects/ffbpnn/NNarchDataflow_diagram_480w.png
full_width: true
caption:     Forward Feeding Back Propogation Neural Network architecture developed in Python
description: >
  This project involved constructing a Forward Feeding Back Propagating Neural Network using Sigmoid activation in Python.
featured:    false
---

## Forward Feeding Backpropagating Neural Network
This project involved implementing a forward feeding, backpropagating neural network in Python, and demonstrates core machine learning principles.  The network architecture is a basic neural network with input, hidden and output layers, intaking numerical data.  The forward feed incorporates a sigmoid activation function to introduce non-linearity and the loss is calculated using a Root Mean Squared Error (RMSE) loss metric.  The overall network is constructed manually using a doubly linked list. 

## Key Features and Highlights
- Input Handling: Data is preprocessed and split into train and test sets.
- Forward Propagation: The network computes weighted sums and applies sigmoid activation to propagate data through the hidden and output layers.
- Backpropagation: Errors are backpropagated with weight adjustments.
- Error Metric: The RMSE was used to evaluate and monitor the performance of the network during training. 

## Tools Used
- Numpy
- JSON
- PyQt5
- Matplotlib

## Experimentation & Results
The network was tested using the well known Iris dataset and the Sine dataset.  

### Iris Dataset
The network was trained twice using the Iris dataset; for 10001 epochs at a learning rate of 0.7 and for 20001 epochs at a learning rate of 0.3.