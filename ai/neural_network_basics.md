
# 🧠 Neural Network Basics (NN, Activation Functions, Backpropagation)

- Artificial Neural Networks (ANN)
- Activation Functions
- Backpropagation (learning algorithm)

---

# 1️⃣ What Is a Neural Network?

A neural network is a computational model inspired by the human brain.  
It consists of layers of interconnected units called **neurons**.

Each neuron performs three steps:

1. **Takes inputs**  
2. **Multiplies each input by a weight**  
3. **Sums them and applies an activation function**

The goal of a neural network is to **learn patterns** in data such as:
- images  
- text  
- speech  
- predictions  

A basic neuron computes:

\[
net = \sum (x_i \cdot w_i)
\]

Then applies an activation function to produce the final output.

---

# 2️⃣ Activation Functions (Why They Matter)

Activation Functions (AFs) decide whether a neuron should activate or not.  
They give the network its **non-linear ability**, allowing it to learn complex patterns.

Without activation functions, the network becomes **only linear** and cannot learn real-world data.

---

## 🔹 Common Activation Functions

### **1. Step Function**
Used in early perceptrons.  
Outputs:
- 1 if input ≥ 0  
- 0 otherwise  

Good for yes/no decisions but not used in deep learning.

---

### **2. Sigmoid**
Smooth function that outputs values between **0 and 1**.

\[
\sigma(x)=\frac{1}{1+e^{-x}}
\]

Useful for **binary classification**.

---

### **3. Tanh**
Outputs values from **-1 to +1**.

Better than sigmoid because it is zero-centered.

---

### **4. ReLU (Rectified Linear Unit)**
Most widely used today.

\[
ReLU(x)=\max(0,x)
\]

Simple, fast, and effective in deep learning.

---

### **5. Softmax**
Used for **multi-class classification**.  
Converts outputs into probabilities that sum to 1.

---

# 3️⃣ Backpropagation (How Neural Networks Learn)

Backpropagation is the learning algorithm that adjusts the weights in a neural network.

It has two main phases:

---

## 🔹 1. Forward Pass
- Inputs are multiplied by weights  
- Activation functions are applied  
- The network produces an output  

---

## 🔹 2. Backward Pass
If the output is incorrect, the network computes an **error**:

\[
Error = Target - Output
\]

Then it works backward through the layers to update the weights.

Key steps:
- Compute gradients (sensitivity of error to each weight)  
- Adjust weights in the direction that reduces error  
- Repeat for many training samples  

This process is what allows the network to “learn.”

---

# 4️⃣ Summary

| Concept | Meaning |
|--------|---------|
| Neural Network | System of connected neurons that learn patterns |
| Activation Function | Decides neuron output and adds non-linearity |
| Backpropagation | Algorithm that updates weights to reduce error |

Neural networks become powerful because of the combination of:
- **Weighted inputs**
- **Activation functions**
- **Backpropagation learning**

---

# 5️⃣ Tiny Example (Python)

python
import numpy as np

def relu(x):
    return np.maximum(0, x)

inputs = np.array([1, -2, 3])
weights = np.array([0.4, -0.3, 0.8])

net = np.dot(inputs, weights)
output = relu(net)

print("Net:", net)
print("Output:", output)
