# Manual Learning of AND Gate Using a Perceptron

## Assignment Description

This assignment requires **manual** implementation of learning an AND logic gate using a single perceptron, using the iteration method (perceptron algorithm / gradient descent), **not** through analytical solution of a system of equations.

## Perceptron Architecture

The perceptron consists of:
- **One neuron**
- **Three inputs:**
  - X₀ = 1 (bias)
  - X₁ (first input)
  - X₂ (second input)
- **Three weights:**
  - W₀ (bias weight)
  - W₁
  - W₂
- **Activation function:** sign
  - Negative output → 0 (False)
  - Positive output → 1 (True)

## Dataset - AND Gate

| X₀ | X₁ | X₂ | Y (target) |
|:--:|:--:|:--:|:----------:|
| 1  | 0  | 0  |     0      |
| 1  | 0  | 1  |     0      |
| 1  | 1  | 0  |     0      |
| 1  | 1  | 1  |     1      |

## Workflow

### 1. Initialize Weights
Start with random weights (any legitimate starting set is valid).  
For example: W₀ = 0.5, W₁ = -0.3, W₂ = 0.2

### 2. Training Loop
Iterate through the examples **one by one** (batch size = 1):

For each example, perform:

1. **Calculate the dot product:**
   ```
   z = W₀·X₀ + W₁·X₁ + W₂·X₂ = Wᵀ·X
   ```

2. **Apply the sign function:**
   ```
   ŷ = sign(z) = { 1  if z ≥ 0
                 { 0  if z < 0
   ```

3. **Calculate the error:**
   ```
   error = Y - ŷ
   ```

4. **Update weights** (perceptron algorithm):
   ```
   W₀ ← W₀ + η · error · X₀
   W₁ ← W₁ + η · error · X₁
   W₂ ← W₂ + η · error · X₂
   ```
   Where η (learning rate) is typically = 1 in the classical perceptron algorithm

### 3. Stopping Criterion
Continue until all four examples are correctly classified (100% accuracy).

**Note:** One epoch = one complete pass through all four examples.

## Submission Requirements

### Allowed Tools
**Only** one of the following:
- ✏️ **Manual:** Pen and paper
- 📊 **Digital:** Microsoft Excel

### Submission Format
- **PDF file only**
  - Manual work → Scan/photograph clearly and convert to PDF
  - Excel work → Export the spreadsheet to PDF
- Upload to the course repository

## What to Include in the Document

### 1. Network Architecture Diagram ✅
A manual drawing/diagram including:
- One neuron
- Three inputs: X₀=1, X₁, X₂
- Weights: W₀, W₁, W₂
- One output after the sign function

### 2. Data Table ✅
Clear presentation of the four AND gate examples

### 3. Iteration Table ✅
For each update step, document:
- Iteration number
- Current weights (W₀, W₁, W₂)
- Current input vector (X₀, X₁, X₂)
- Dot product (z)
- Output after sign (ŷ)
- Target (Y)
- Error
- Updated weights

### 4. Process Documentation ✅
- Document all iterations until convergence
- Specify how many epochs were required
- Show that you achieved 100% correct classification

## Example Table Structure

| Iteration | W₀ | W₁ | W₂ | X₀ | X₁ | X₂ | z | ŷ | Y | Error | W₀' | W₁' | W₂' |
|:---------:|:--:|:--:|:--:|:--:|:--:|:--:|:-:|:-:|:-:|:-----:|:---:|:---:|:---:|
| 1 | 0.5 | -0.3 | 0.2 | 1 | 0 | 0 | 0.5 | 1 | 0 | -1 | ... | ... | ... |
| 2 | ... | ... | ... | 1 | 0 | 1 | ... | ... | 0 | ... | ... | ... | ... |

## Tips for Success

1. 🎯 **Choose simple initial weights** - prefer small numbers (-1 to 1)
2. 📝 **Work in order** - start from the first example in each epoch
3. ✔️ **Check each calculation** - calculation errors will lead to non-convergence
4. 🔁 **Patience** - may require 2-3 epochs or more
5. 📋 **Legibility** - ensure handwriting/spreadsheet is clear and readable

## Frequently Asked Questions

**Q: What learning rate should I use?**  
A: In the classical perceptron algorithm, use η=1

**Q: What if it doesn't converge?**  
A: The AND gate is linearly separable - if you followed the method correctly, it must converge

**Q: Can I use Python?**  
A: No! Only manual or Excel

**Q: How many iterations are expected?**  
A: Depends on initial weights - typically 4-20 iterations

---

**Good luck! 🚀**