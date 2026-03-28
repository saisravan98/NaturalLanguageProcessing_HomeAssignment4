# CS5760 Natural Language Processing

## Homework 4 – Spring 2026

**University of Central Missouri**
**Department of Computer Science & Cybersecurity**

---

## 👨‍💻 Student Information

**Name:** CHINTALA SAI SRAVAN

---

## 📌 Overview

This assignment covers both **theoretical concepts** and **practical implementations** in deep learning and Natural Language Processing (NLP).

It includes:

* RNN-based sequence modeling
* Transformer Encoder architecture
* Scaled Dot-Product Attention
* Neural network computations and decision boundaries
* Concepts like vanishing gradients, LSTM gates, and self-attention

All programming tasks are implemented in a **single Python file (`Homework 4_Solution.py`)**.

---

## 📂 Repository Structure

```bash id="struct"
.
├── Homework 4_Solution.py   # Contains Q1, Q2, Q3 implementations
├── sample.txt              # Text dataset for RNN model
├── Homework 4_Solution.pdf # Written solutions (Q3–Q8 + theory)
├── README.md               # Documentation
```

---

## ⚙️ Requirements

Install dependencies before running:

```bash id="install2"
pip install torch numpy matplotlib
```

---

## ▶️ How to Run

1. Ensure `sample.txt` is present (50–200 KB text file)
2. Run the program:

```bash id="run2"
python "Homework 4_Solution.py"
```

---

# 🧩 PART I: THEORY QUESTIONS

---

## 🔹 Q3: Neural Networks

* Non-linear activations enable learning complex relationships
* Deep networks learn hierarchical features better than shallow models

---

## 🔹 RNN Concepts

* **Next-word prediction:** One-to-many
* **Sentiment analysis:** Many-to-one
* **NER:** Many-to-many (aligned)
* **Machine Translation:** Many-to-many (unaligned)

---

## 🔹 Vanishing Gradient Problem

* Gradients shrink over time → poor long-term learning
* Solutions:

  * LSTM
  * GRU
  * Gradient Clipping

---

## 🔹 LSTM Gates

* Forget Gate → removes irrelevant info
* Input Gate → adds new info
* Output Gate → controls exposure

---

## 🔹 Self-Attention

* Query → what to look for
* Key → what is available
* Value → actual content

Formula:

```
Attention(Q,K,V) = softmax(QKᵀ / √dₖ) V
```

---

## 🔹 Multi-Head Attention

* Captures multiple relationships in parallel
* Improves representation power

---

## 🔹 Encoder–Decoder

* Masked attention prevents future leakage
* Cross-attention connects encoder and decoder

---

# 🧩 PART II: PROGRAMMING

---

## 🔹 Q1: Character-Level RNN Language Model

### ✅ Objective

Predict next character from previous sequence.

---

### 🏗️ Model Architecture

* Embedding Layer
* LSTM
* Fully Connected Layer
* Softmax

---

### ⚙️ Training Details

* Sequence Length: 50
* Hidden Size: 256
* Batch Size: 64
* Epochs: 10
* Optimizer: Adam
* Loss: Cross-Entropy

---

### 📊 Output Results

**Loss Values:**

* Train Loss decreased from **0.0286 → 0.0167**
* Validation Loss stabilized around **0.022**

---

### 📝 Generated Text Samples

**Temperature = 0.7 (More coherent):**

* Structured and readable text
* More repetitive

**Temperature = 1.0 (Balanced):**

* Moderate creativity and coherence

**Temperature = 1.2 (Creative):**

* More randomness
* Less grammatical accuracy

---

### 🧠 Reflection

* Larger sequence length improves context
* Higher hidden size increases learning capacity
* Temperature controls randomness vs coherence

---

## 🔹 Q2: Mini Transformer Encoder

### ✅ Objective

Process sentences using Transformer Encoder.

---

### 🏗️ Components

* Tokenization & Padding
* Embedding Layer
* Positional Encoding
* Multi-Head Attention (2 heads)
* Feed-Forward Network
* Add & LayerNorm

---

### 📊 Outputs

* Input token tensor shape: **(10, 5)**
* Final embeddings shape: **(10, 5, 32)**
* Attention heatmap visualization

---

### 🧠 Observations

* Self-attention captures word relationships
* Multi-head attention learns diverse patterns
* Positional encoding preserves order

---

## 🔹 Q3: Scaled Dot-Product Attention

### ✅ Objective

Implement attention mechanism.

---

### 📊 Results

* Raw max score: **4.319**
* Scaled max score: **1.527**

---

### 🔍 Key Insight

* Without scaling → very sharp softmax
* With scaling → smoother distribution
* Improves numerical stability

---

## 🔹 Q6: Multi-Input Feedforward Network

### 📊 Results

* Hidden activations:

  * h₁ ≈ 0.574
  * h₂ ≈ 0.750
* Output:

  * y ≈ 0.5005

---

### Loss:

* Binary Cross-Entropy ≈ **0.692**

---

## 🔹 Q7: XOR with ReLU Network

### 📊 Outputs

| Input | Output |
| ----- | ------ |
| (0,0) | 0      |
| (0,1) | 1      |
| (1,0) | 3      |
| (1,1) | 1      |

---

### ❗ Conclusion

* Network does **NOT compute XOR exactly**
* Misclassified input: **(1,1)**
* Cause: Added hidden unit introduces asymmetry

---

## 🔹 Q8: Perceptron Decision Boundary

### 📐 Boundary:

```
x₁ - 2x₂ + 1 = 0
```

---

### 📊 Classification Results

* Misclassified point: **(3,2)**
* Perceptron loss = **1**

---

### 🔄 Weight Update

New weights:

* w₁ = 4
* w₂ = 0
* b = 2

---

# 📚 Key Learning Outcomes

* Understanding of RNN sequence modeling
* Hands-on Transformer Encoder implementation
* Importance of attention scaling
* Neural network decision boundaries
* Handling vanishing gradients
* Role of LSTM gates and attention mechanisms

---

# 📌 Conclusion

This assignment demonstrates the evolution of NLP models:

* **RNNs** → sequential, limited memory
* **Transformers** → parallel, attention-based

Attention mechanisms significantly improve performance and are the foundation of modern NLP systems like GPT and BERT.

---

# 🔗 Submission

GitHub repository link submitted on **Brightspace** as per instructions.

---

# ⚠️ Notes

* Code is properly commented as required
* All outputs verified and included
* Assignment completed as per submission guidelines
