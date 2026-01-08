# Perceptron AND Gate – Manual Training Exercise

This project implements and **documents** a manual training process of a single-layer perceptron that learns the logical AND function, based on a homework assignment given in class.[file:1]

## Project Description

The goal is to find weights \(W_0, W_1, W_2\) for a single neuron (perceptron) with bias so that it correctly classifies all inputs of the AND gate.[file:1]  
The training is done manually (or via Excel), by iteratively updating the weights according to the algorithm demonstrated in the lecture, until 100% classification accuracy is reached on the AND truth table.[file:1]

## Model Architecture

- Single perceptron (one neuron).[file:1]  
- Inputs:
  - \(X_0 = 1\) (bias term)
  - \(X_1\), \(X_2\).[file:1]
- Weights:
  - \(W_0\) (bias weight)
  - \(W_1\), \(W_2\).[file:1]
- Output:
  - Scalar output after applying a sign activation function (negative → class 0, positive → class 1).[file:1]

Mathematically, the neuron computes the scalar product \(z = W^T X\), and then applies a sign activation to obtain the final binary output.[file:1]

## Dataset (AND Gate)

The dataset consists of all input combinations for a 2-input AND gate, augmented with the bias input \(X_0 = 1\).[file:1]

| Sample | X0 | X1 | X2 | Target (Y) |
|--------|----|----|----|------------|
| 1      | 1  | 0  | 0  | 0          |
| 2      | 1  | 0  | 1  | 0          |
| 3      | 1  | 1  | 0  | 0          |
| 4      | 1  | 1  | 1  | 1          |[file:1]

The perceptron must learn a separating line in the \((X_1, X_2)\) plane such that the three points corresponding to output 0 are on one side (negative) and the point \((1,1)\) is on the other side (positive).[file:1]

## Training Procedure

The assignment requires **manual** training (no automatic coding of the algorithm), either:

- By hand, using pen and paper, or  
- Using Excel, while still writing out and showing all intermediate calculations.[file:1]

Main guidelines:

1. **Weight initialization**  
   - Start from randomly chosen initial weights \(W_0, W_1, W_2\).[file:1]  
   - Different students may use different initial weights; there are infinitely many separating hyperplanes.[file:1]

2. **Batch size and epochs**  
   - Batch size: 1 (one sample per update step).[file:1]  
   - One epoch = passing through all 4 samples once.[file:1]  
   - It is allowed and expected to have more than one epoch until convergence (100% correct classification).[file:1]

3. **Per-step computation** (for each sample):
   - Compute the scalar product \(z = W^T X\).[file:1]  
   - Apply the sign activation:
     - Negative \(z\) → output 0 (class 0).
     - Positive \(z\) → output 1 (class 1).[file:1]
   - Compare the predicted output to the target \(Y\) and compute the error.[file:1]  
   - Update the weights using the perceptron update rule / gradient-style rule as shown in the lecture, which involves subtracting a term proportional to the feature vector \(X\) in case of misclassification.[file:1]

4. **Stopping condition**  
   - Repeat the process over the dataset (multiple epochs if needed) until all four samples are classified correctly (100% accuracy).[file:1]

## Deliverables

The submission for this project is:

- A **PDF file** that clearly shows:
  - The architecture drawing of the perceptron (inputs, weights, neuron, activation).[file:1]
  - The full dataset table with inputs and targets.[file:1]
  - A detailed iteration table showing, for each step:
    - Current weights \((W_0, W_1, W_2)\)
    - Input vector \((X_0, X_1, X_2)\)
    - Scalar product \(z = W^T X\)
    - Output after the sign function
    - Error
    - Updated weights.[file:1]

Accepted formats for producing the PDF:

- Handwritten calculations and diagrams (scanned or photographed, then converted to PDF), or  
- Excel sheet exported to PDF.[file:1]

The PDF should be uploaded to the course repository as the final submission, following the course’s standard submission process.[file:1]

## Repository Structure (Suggested)

```text
.
├── README.md              # This file
├── docs/
│   └── perceptron_and_explanation.pdf   # Optional extra explanation for yourself
├── submission/
│   └── perceptron_and_homework.pdf      # The PDF submitted to the lecturer
├── excel/
│   └── perceptron_and_calculations.xlsx # If you choose to work in Excel
└── sketches/
    └── architecture_draft.png           # Optional diagram drafts
