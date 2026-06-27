# PyTorch — Ultimate Master Guide

> 📘 **The most complete guide to PyTorch — from zero to expert.**
>
> 🎯 *Who is this for?* Absolute beginners, Python developers, ML/DL learners, AI practitioners.
> ⏱️ *Time to complete:* Self-paced (days to months depending on depth)
> 🛠️ *What you'll gain:* Full mastery of deep learning with PyTorch — tensors, autograd, neural networks, CNNs, RNNs, Transformers, and production deployment

---

## Table of Contents

1. [🧠 What is PyTorch?](#1-what-is-pytorch-super-simple)
2. [🌍 Why This Exists](#2-why-this-exists)
3. [🧱 Core Fundamentals](#3-core-fundamentals-beginner-level)
4. [⚙️ Complete System Breakdown](#4-complete-system-breakdown)
5. [🔄 Real-World Workflow](#5-real-world-workflow)
6. [🧪 Hands-on Practice](#6-hands-on-practice)
7. [⚠️ Common Mistakes](#7-common-mistakes)
8. [🔥 Pro Tips & Hidden Tricks](#8-pro-tips--hidden-tricks)
9. [🚀 Advanced Concepts](#9-advanced-concepts-expert-level)
10. [🗺️ Complete Roadmap](#10-complete-roadmap)
11. [🧩 Bonus Deep Insights](#11-bonus-deep-insights)
12. [📌 Summary](#12-summary-quick-revision)

---

## 🧠 1. What is PyTorch? (Super Simple)

### The 12-Year-Old Explanation

Imagine you want to teach a computer to recognize cats in photos. You can't just write rules like "cats have pointy ears and whiskers" — there are too many exceptions. Instead, you show the computer thousands of cat photos, and it slowly *learns* what a cat looks like by adjusting thousands of tiny knobs (called weights) inside itself. This process is called **deep learning**.

PyTorch is the ultimate toolkit that lets you build, train, and experiment with these learning machines (called **neural networks**) using Python. It handles all the scary math — matrix multiplications, derivatives, gradient calculations — automatically. You just describe the structure of your network, feed it data, and tell it to learn.

What makes PyTorch special is that it feels like writing normal Python code. You can print values, set breakpoints, and debug line-by-line — unlike older frameworks that felt like writing in a completely foreign language. It's used by researchers at Google, Facebook, OpenAI, Tesla, and top universities worldwide, and it powers models like LLaMA, Stable Diffusion, and GPT-style architectures.

### Real-Life Analogy

💡 **Think of it like this:**
Imagine you're teaching a student (the neural network) to bake the perfect cake. Every time they bake:
1. You taste it and give a **score** (the loss function — how wrong it was)
2. You point out *exactly* what went wrong: "too much sugar in step 3" (the gradient — which direction to adjust)
3. The student **adjusts** their recipe slightly (backpropagation — updating weights)
4. Repeat thousands of times until the cake is perfect (training loop)

PyTorch is the **kitchen, measuring tools, oven, and recipe book** — all in one. You bring the ingredients (data) and the idea of what you want to bake (architecture), and PyTorch handles everything else.

### One-Line Definition

> **PyTorch** is an open-source Python deep learning framework by Meta AI that provides GPU-accelerated tensor computation and automatic differentiation for building and training neural networks.

---

## 🌍 2. Why This Exists

### The Problem It Solved

Before PyTorch (released 2016), the dominant framework was TensorFlow 1.x, which used a **static computation graph** — you had to define the entire neural network structure before running *any* code. This made debugging nightmarish (you'd get cryptic errors deep in graph execution), and experimentation was slow and painful.

PyTorch introduced the **dynamic computation graph** (define-by-run): the graph is built on-the-fly as your code executes, exactly like normal Python. This was revolutionary — researchers could finally write neural networks as naturally as any other Python program, debug them with standard tools, and iterate 10x faster.

### Where It's Used in the Real World

| Industry / Area         | How PyTorch Is Used                                                  |
|-------------------------|----------------------------------------------------------------------|
| 🤖 AI Research          | Training foundation models (LLaMA, Mistral, Stable Diffusion)        |
| 🚗 Autonomous Vehicles  | Perception models (object detection, depth estimation) at Tesla, Waymo|
| 🏥 Medical AI           | Tumor segmentation, drug discovery, protein folding (AlphaFold2)    |
| 📱 Mobile Apps          | On-device inference with PyTorch Mobile and ExecuTorch               |
| 🎮 Game AI / RL         | Training game-playing agents (reinforcement learning)                |
| 🗣️ NLP / LLMs          | Fine-tuning GPT-style models, BERT, Transformers                    |
| 🎨 Generative AI        | GANs, Diffusion Models, Image synthesis, DeepFakes                  |
| 🔬 Scientific Computing | Physics simulations, climate modeling, molecular dynamics            |
| 📊 Finance              | Time series forecasting, fraud detection, algorithmic trading        |
| 🌾 Agriculture / Drone  | Crop disease detection, yield prediction via aerial imagery          |

### Why YOU Should Learn It

1. **It's the #1 research framework** — over 80% of papers at NeurIPS, ICML, and CVPR use PyTorch. If you want to read and implement cutting-edge papers, you need PyTorch.
2. **Industry standard** — Meta, OpenAI, Hugging Face, Tesla, Microsoft, and hundreds of AI startups build on PyTorch.
3. **Most intuitive deep learning framework** — feels like Python, not a new language. Perfect for a Python dev like you.
4. **Gateway to everything modern** — LLMs, Stable Diffusion, YOLO, NeRF, AlphaFold — all PyTorch.
5. **Career-defining skill** — ML engineer, AI researcher, computer vision engineer, NLP engineer all require PyTorch fluency.

---

## 🧱 3. Core Fundamentals (Beginner Level)

> 🎯 *Goal: Build a rock-solid foundation before going deeper.*

---

### Concept 1: Tensors — The Building Block of Everything

A **tensor** is the fundamental data structure in PyTorch. Think of it as a supercharged NumPy array that can live on a GPU and knows how to compute gradients.

- **Scalar**: 0-D tensor — a single number `(42.0)`
- **Vector**: 1-D tensor — a list of numbers `[1, 2, 3]`
- **Matrix**: 2-D tensor — a table of numbers `[[1,2],[3,4]]`
- **3-D tensor**: A cube (e.g., a grayscale video: frames × height × width)
- **4-D tensor**: A hypercube (e.g., color image batch: batch × channels × height × width)

💡 **Example:**
```python
import torch

# Creating tensors
scalar  = torch.tensor(42.0)                          # 0-D
vector  = torch.tensor([1.0, 2.0, 3.0])              # 1-D
matrix  = torch.tensor([[1.0, 2.0], [3.0, 4.0]])     # 2-D
cube    = torch.zeros(3, 4, 4)                        # 3-D: all zeros
batch   = torch.randn(32, 3, 224, 224)                # 4-D: 32 RGB 224x224 images

print(scalar.shape)    # torch.Size([])
print(vector.shape)    # torch.Size([3])
print(matrix.shape)    # torch.Size([2, 2])
print(batch.shape)     # torch.Size([32, 3, 224, 224])
print(batch.dtype)     # torch.float32
print(batch.device)    # cpu  (or cuda:0 if on GPU)
```

---

### Concept 2: Tensor Operations

Tensors support all the math you'd expect — element-wise, matrix operations, reductions.

💡 **Example:**
```python
import torch

a = torch.tensor([1.0, 2.0, 3.0])
b = torch.tensor([4.0, 5.0, 6.0])

# Element-wise
print(a + b)        # tensor([5., 7., 9.])
print(a * b)        # tensor([4., 10., 18.])
print(a ** 2)       # tensor([1., 4., 9.])

# Matrix multiplication — THE most important op in deep learning
A = torch.randn(3, 4)
B = torch.randn(4, 5)
C = torch.mm(A, B)         # Matrix multiply: (3,4) @ (4,5) → (3,5)
C = A @ B                  # Same thing, cleaner syntax

# Reductions
x = torch.tensor([1.0, 2.0, 3.0, 4.0])
print(x.sum())     # tensor(10.)
print(x.mean())    # tensor(2.5)
print(x.max())     # tensor(4.)
print(x.min())     # tensor(1.)

# Reshape
x = torch.arange(12, dtype=torch.float32)   # [0,1,2,...,11]
x = x.reshape(3, 4)                          # (3, 4) matrix
x = x.view(2, 6)                             # (2, 6) — shares memory with reshape

# Indexing (same as NumPy)
mat = torch.randn(5, 5)
print(mat[0])           # First row
print(mat[:, 2])        # Third column
print(mat[1:3, 1:3])   # 2x2 sub-matrix
```

---

### Concept 3: GPU Acceleration (CUDA)

The entire power of deep learning comes from running math on **GPUs** — which can do thousands of operations in parallel. PyTorch makes this trivial.

💡 **Example:**
```python
import torch

# Check if GPU is available
device = torch.device('cuda' if torch.cuda.is_available() else 'cpu')
print(f"Using device: {device}")

# Move tensor to GPU
x = torch.randn(1000, 1000)
x_gpu = x.to(device)           # Now lives on GPU (if available)
x_gpu = x.cuda()               # Alternative

# Move back to CPU (e.g., for numpy conversion)
x_cpu = x_gpu.cpu()
x_numpy = x_cpu.numpy()

# Pro tip: create directly on device
x = torch.randn(1000, 1000, device=device)

# All ops on GPU tensors run on GPU automatically
y = x @ x.T     # (1000,1000) matrix multiply — runs on GPU!
```

---

### Concept 4: Autograd — Automatic Differentiation

This is **the magic** of PyTorch. Autograd automatically computes gradients (derivatives) of any computation. This is what makes training neural networks possible — you don't have to calculate ∂Loss/∂weight by hand.

💡 **Example:**
```python
import torch

# requires_grad=True tells PyTorch: "track operations on this tensor"
x = torch.tensor(3.0, requires_grad=True)

# Compute something
y = x ** 2 + 2 * x + 1   # y = x² + 2x + 1

# Compute gradients via backpropagation
y.backward()

# dy/dx = 2x + 2; at x=3: dy/dx = 8
print(x.grad)    # tensor(8.)

# ------- More realistic example -------
w = torch.randn(3, requires_grad=True)  # Model weights
b = torch.randn(1, requires_grad=True)  # Bias

x_data = torch.tensor([1.0, 2.0, 3.0])
y_pred = w * x_data + b        # Forward pass
loss = ((y_pred - 1.0) ** 2).mean()  # MSE loss

loss.backward()   # Compute all gradients

print(w.grad)     # ∂loss/∂w — how to update w to reduce loss
print(b.grad)     # ∂loss/∂b — how to update b to reduce loss

# Detach from computation graph (for inference or logging)
val = y_pred.detach()
val = y_pred.item()    # Scalar tensor → Python float
```

---

### Concept 5: torch.nn.Module — Building Neural Networks

`nn.Module` is the base class for all neural networks in PyTorch. You subclass it, define layers in `__init__`, and write the forward pass in `forward()`.

💡 **Example:**
```python
import torch
import torch.nn as nn

class SimpleNet(nn.Module):
    def __init__(self, input_size, hidden_size, output_size):
        super().__init__()             # ALWAYS call this!
        # Define layers
        self.fc1 = nn.Linear(input_size, hidden_size)
        self.relu = nn.ReLU()
        self.fc2 = nn.Linear(hidden_size, output_size)

    def forward(self, x):
        # Define how data flows through the network
        x = self.fc1(x)    # Linear transformation
        x = self.relu(x)   # Non-linearity
        x = self.fc2(x)    # Output layer
        return x

# Instantiate the model
model = SimpleNet(input_size=10, hidden_size=64, output_size=3)
print(model)

# Count parameters
total_params = sum(p.numel() for p in model.parameters())
print(f"Total parameters: {total_params:,}")

# Forward pass with random input
x = torch.randn(4, 10)    # Batch of 4 samples, each with 10 features
output = model(x)          # Shape: (4, 3)
print(output.shape)        # torch.Size([4, 3])
```

---

### Concept 6: Loss Functions & Optimizers

A **loss function** measures how wrong the model's predictions are. An **optimizer** uses gradients to update weights to reduce that loss.

💡 **Example:**
```python
import torch
import torch.nn as nn

model = SimpleNet(10, 64, 3)

# --- Loss Functions ---
criterion_mse    = nn.MSELoss()           # Regression
criterion_cross  = nn.CrossEntropyLoss() # Multi-class classification (includes softmax)
criterion_bce    = nn.BCEWithLogitsLoss()# Binary classification (includes sigmoid)
criterion_l1     = nn.L1Loss()           # MAE loss

# --- Optimizers ---
optimizer_sgd   = torch.optim.SGD(model.parameters(), lr=0.01, momentum=0.9)
optimizer_adam  = torch.optim.Adam(model.parameters(), lr=1e-3)
optimizer_adamw = torch.optim.AdamW(model.parameters(), lr=1e-3, weight_decay=1e-4)

# --- Single training step ---
x = torch.randn(4, 10)
y_true = torch.tensor([0, 1, 2, 1])    # Class labels

# 1. Forward pass
y_pred = model(x)

# 2. Compute loss
loss = criterion_cross(y_pred, y_true)

# 3. Zero gradients (CRITICAL — gradients accumulate by default)
optimizer_adam.zero_grad()

# 4. Backward pass — compute gradients
loss.backward()

# 5. Update weights
optimizer_adam.step()

print(f"Loss: {loss.item():.4f}")
```

---

🧪 **Mini Task 1:**
> Create a `torch.randn(5, 3)` tensor representing 5 data points with 3 features. Compute its mean along dimension 0 (per-feature mean) and dimension 1 (per-sample mean). Verify the shapes.
> ✅ *Expected outcome:* `mean(dim=0).shape = (3,)` and `mean(dim=1).shape = (5,)`

🧪 **Mini Task 2:**
> Define a simple `nn.Module` with two linear layers and a Sigmoid activation. Run a batch of 8 inputs through it. Compute binary cross-entropy loss and call `.backward()`. Print `model.parameters()` count before and after.

---

## ⚙️ 4. Complete System Breakdown

> 🎯 *Goal: Understand every major PyTorch component — nothing hidden.*

---

### Part 1: torch.Tensor (Core Data Structure)

**What it is:** Multi-dimensional array with GPU support, automatic differentiation, and a rich API.
**Why it matters:** Everything in PyTorch is a tensor — weights, inputs, outputs, gradients.
**How it works:** Internally uses strided storage — tensors share memory when possible (`.view()`, slicing).

```python
import torch

# Creation methods
t = torch.zeros(3, 4)                    # All zeros
t = torch.ones(3, 4)                     # All ones
t = torch.eye(4)                         # Identity matrix
t = torch.arange(0, 10, 2)              # [0, 2, 4, 6, 8]
t = torch.linspace(0, 1, 5)             # [0.0, 0.25, 0.5, 0.75, 1.0]
t = torch.randn(3, 4)                    # Normal distribution N(0,1)
t = torch.rand(3, 4)                     # Uniform distribution [0,1)
t = torch.randint(0, 10, (3, 4))        # Random integers

# Type casting
t = t.float()       # → torch.float32
t = t.double()      # → torch.float64
t = t.long()        # → torch.int64 (for class labels)
t = t.half()        # → torch.float16 (for mixed precision)
t = t.to(torch.bfloat16)  # → bfloat16 (good for LLMs)

# Shape manipulation
t = torch.randn(2, 3, 4)
t2 = t.permute(2, 0, 1)          # Reorder dimensions: (4, 2, 3)
t3 = t.unsqueeze(0)              # Add dim: (1, 2, 3, 4)
t4 = t3.squeeze(0)               # Remove dim: (2, 3, 4)
t5 = t.flatten()                 # → 1-D tensor
t6 = t.reshape(-1, 4)           # -1 = auto-compute
cat = torch.cat([t, t], dim=0)  # Concatenate along dim
stk = torch.stack([t, t], dim=0) # Stack — new dimension

# NumPy bridge (ZERO-COPY when on CPU)
import numpy as np
arr = np.array([1.0, 2.0, 3.0])
t = torch.from_numpy(arr)    # Shares memory!
arr2 = t.numpy()             # Shares memory!
```

---

### Part 2: Autograd Engine

**What it is:** Automatic differentiation system that tracks operations and computes gradients via reverse-mode autodiff (backpropagation).
**Why it matters:** You never manually compute ∂Loss/∂weight — autograd handles it.
**How it works:** PyTorch builds a dynamic computation graph (DAG) during the forward pass. Each tensor operation records itself. `.backward()` traverses the DAG in reverse to compute gradients via the chain rule.

```python
import torch

# The computation graph
x = torch.tensor(2.0, requires_grad=True)
y = torch.tensor(3.0, requires_grad=True)

z = x * y + x ** 2   # z = xy + x²

z.backward()

print(x.grad)   # ∂z/∂x = y + 2x = 3 + 4 = 7
print(y.grad)   # ∂z/∂y = x = 2

# No gradient tracking (for inference — faster, less memory)
with torch.no_grad():
    output = model(x_input)    # No graph built, faster

# Or use .detach() to stop a tensor from being part of the graph
a = torch.randn(3, requires_grad=True)
b = a.detach()    # b is a separate tensor, no gradient

# gradient accumulation — useful for large batches
optimizer.zero_grad()
for mini_batch in split_batch:
    loss = criterion(model(mini_batch), labels) / n_accumulate
    loss.backward()          # Accumulate gradients
optimizer.step()             # Update once with accumulated grads

# Gradient clipping — prevents exploding gradients
torch.nn.utils.clip_grad_norm_(model.parameters(), max_norm=1.0)
```

---

### Part 3: torch.nn — Neural Network Building Blocks

**What it is:** Library of pre-built layers, loss functions, and utilities for building neural networks.
**Why it matters:** You don't need to implement Linear, Conv2d, LSTM from scratch.

```python
import torch.nn as nn

# --- Linear Layers ---
nn.Linear(in_features, out_features, bias=True)  # y = Wx + b

# --- Activation Functions ---
nn.ReLU()            # max(0, x) — most common hidden layer activation
nn.LeakyReLU(0.01)  # Allows small negative values
nn.GELU()            # Gaussian Error Linear Unit — used in Transformers
nn.Sigmoid()         # Squashes to (0,1) — binary output
nn.Tanh()            # Squashes to (-1,1)
nn.Softmax(dim=1)   # Multi-class probabilities — use CrossEntropyLoss instead!

# --- Convolutional Layers ---
nn.Conv2d(in_channels, out_channels, kernel_size, stride=1, padding=0)
nn.Conv1d(in_channels, out_channels, kernel_size)   # For sequences
nn.ConvTranspose2d(...)                              # Upsampling / decoder

# --- Pooling ---
nn.MaxPool2d(kernel_size=2, stride=2)
nn.AvgPool2d(kernel_size=2)
nn.AdaptiveAvgPool2d((1, 1))  # Always outputs (1,1) regardless of input size

# --- Normalization ---
nn.BatchNorm2d(num_features)    # Normalize over batch — most common for CNNs
nn.LayerNorm(normalized_shape)  # Normalize over features — used in Transformers
nn.GroupNorm(num_groups, num_channels)

# --- Dropout (Regularization) ---
nn.Dropout(p=0.5)        # Randomly zeros 50% of neurons during training
nn.Dropout2d(p=0.5)      # Zeros entire channels (for CNNs)

# --- Recurrent Layers ---
nn.LSTM(input_size, hidden_size, num_layers, batch_first=True)
nn.GRU(input_size, hidden_size, num_layers, batch_first=True)

# --- Embedding ---
nn.Embedding(num_embeddings, embedding_dim)  # For NLP: maps token IDs to vectors

# --- Transformer ---
nn.TransformerEncoderLayer(d_model=512, nhead=8, dim_feedforward=2048)
nn.MultiheadAttention(embed_dim=512, num_heads=8)

# --- Sequential Container (for simple stacking) ---
model = nn.Sequential(
    nn.Linear(10, 64),
    nn.ReLU(),
    nn.Linear(64, 32),
    nn.ReLU(),
    nn.Linear(32, 1)
)
```

---

### Part 4: DataLoader & Dataset

**What it is:** PyTorch's data pipeline — efficiently loads, batches, shuffles, and preprocesses data.
**Why it matters:** Without this, you'd manually manage batching, shuffling, and multi-threaded loading — a nightmare.
**How it works:** `Dataset` defines how to get one sample. `DataLoader` wraps it to produce batches with parallelism.

```python
import torch
from torch.utils.data import Dataset, DataLoader
import numpy as np

# --- Custom Dataset ---
class MyDataset(Dataset):
    def __init__(self, X, y, transform=None):
        self.X = torch.tensor(X, dtype=torch.float32)
        self.y = torch.tensor(y, dtype=torch.long)
        self.transform = transform

    def __len__(self):
        return len(self.X)                 # Total number of samples

    def __getitem__(self, idx):
        x, label = self.X[idx], self.y[idx]
        if self.transform:
            x = self.transform(x)
        return x, label

# Create dummy data
X = np.random.randn(1000, 10)   # 1000 samples, 10 features
y = np.random.randint(0, 3, 1000)  # 3 classes

dataset = MyDataset(X, y)

# Split train/val
train_size = int(0.8 * len(dataset))
val_size = len(dataset) - train_size
train_ds, val_ds = torch.utils.data.random_split(dataset, [train_size, val_size])

# --- DataLoader ---
train_loader = DataLoader(
    train_ds,
    batch_size=32,
    shuffle=True,        # Shuffle training data
    num_workers=4,       # Parallel data loading (use 0 on Windows)
    pin_memory=True,     # Faster GPU transfer
    drop_last=True       # Drop last incomplete batch
)

val_loader = DataLoader(val_ds, batch_size=64, shuffle=False, num_workers=4)

# Iterate
for batch_X, batch_y in train_loader:
    print(batch_X.shape)   # (32, 10)
    print(batch_y.shape)   # (32,)
    break
```

---

### Part 5: The Training Loop

**What it is:** The core cycle of deep learning — forward pass, compute loss, backprop, update weights.
**Why it matters:** This is where learning actually happens. Understanding this loop deeply is everything.

```python
import torch
import torch.nn as nn

def train_one_epoch(model, loader, optimizer, criterion, device):
    model.train()     # CRITICAL: sets BatchNorm, Dropout to training mode
    total_loss = 0.0
    correct = 0
    total = 0

    for batch_X, batch_y in loader:
        # Move to device
        batch_X = batch_X.to(device)
        batch_y = batch_y.to(device)

        # 1️⃣ Forward pass
        predictions = model(batch_X)

        # 2️⃣ Compute loss
        loss = criterion(predictions, batch_y)

        # 3️⃣ Zero gradients (accumulation prevention)
        optimizer.zero_grad()

        # 4️⃣ Backward pass (compute gradients)
        loss.backward()

        # 5️⃣ (Optional) Gradient clipping
        torch.nn.utils.clip_grad_norm_(model.parameters(), max_norm=1.0)

        # 6️⃣ Update weights
        optimizer.step()

        # Metrics
        total_loss += loss.item()
        _, predicted = predictions.max(1)
        correct += predicted.eq(batch_y).sum().item()
        total += batch_y.size(0)

    avg_loss = total_loss / len(loader)
    accuracy = 100.0 * correct / total
    return avg_loss, accuracy


@torch.no_grad()  # Disable gradient computation for validation
def evaluate(model, loader, criterion, device):
    model.eval()    # CRITICAL: sets BatchNorm, Dropout to eval mode
    total_loss = 0.0
    correct = 0
    total = 0

    for batch_X, batch_y in loader:
        batch_X = batch_X.to(device)
        batch_y = batch_y.to(device)

        predictions = model(batch_X)
        loss = criterion(predictions, batch_y)

        total_loss += loss.item()
        _, predicted = predictions.max(1)
        correct += predicted.eq(batch_y).sum().item()
        total += batch_y.size(0)

    return total_loss / len(loader), 100.0 * correct / total
```

---

### Part 6: Saving & Loading Models

```python
import torch

# --- Save entire model (not recommended — fragile) ---
torch.save(model, 'model.pth')
model = torch.load('model.pth')

# --- Save state dict (recommended) ---
torch.save(model.state_dict(), 'model_weights.pth')

# Load weights
model = MyModel()
model.load_state_dict(torch.load('model_weights.pth', map_location='cpu'))
model.eval()

# --- Save full checkpoint (for resuming training) ---
checkpoint = {
    'epoch': epoch,
    'model_state_dict': model.state_dict(),
    'optimizer_state_dict': optimizer.state_dict(),
    'scheduler_state_dict': scheduler.state_dict(),
    'train_loss': train_loss,
    'val_loss': val_loss,
    'best_acc': best_acc
}
torch.save(checkpoint, 'checkpoint.pth')

# Load checkpoint
checkpoint = torch.load('checkpoint.pth')
model.load_state_dict(checkpoint['model_state_dict'])
optimizer.load_state_dict(checkpoint['optimizer_state_dict'])
start_epoch = checkpoint['epoch'] + 1
```

---

### 📊 Full PyTorch Component Overview

| Component               | Purpose                                      | Key API                                              |
|-------------------------|----------------------------------------------|------------------------------------------------------|
| `torch.Tensor`          | Core data structure, GPU-ready N-D arrays    | `.to()`, `.view()`, `.reshape()`, `.cuda()`          |
| `torch.autograd`        | Automatic differentiation engine             | `.backward()`, `requires_grad`, `no_grad()`          |
| `torch.nn`              | Neural network building blocks               | `Module`, `Linear`, `Conv2d`, `LSTM`, `Transformer`  |
| `torch.nn.functional`   | Stateless functional API (no parameters)     | `F.relu()`, `F.cross_entropy()`, `F.softmax()`       |
| `torch.optim`           | Gradient-based optimizers                    | `Adam`, `SGD`, `AdamW`, `lr_scheduler`               |
| `torch.utils.data`      | Data loading and batching pipeline           | `Dataset`, `DataLoader`, `random_split`              |
| `torch.cuda`            | GPU management                               | `.is_available()`, `.device_count()`, `amp`          |
| `torchvision`           | Vision datasets, transforms, pre-trained models | `datasets`, `transforms`, `models`               |
| `torchaudio`            | Audio datasets and transforms                | `datasets`, `transforms`, `functional`               |
| `torchtext`             | NLP datasets and tokenizers                  | `datasets`, `vocab`, `utils`                         |
| `torch.jit`             | TorchScript — compile models for deployment  | `@torch.jit.script`, `torch.jit.trace`               |
| `torch.onnx`            | Export models to ONNX format                 | `torch.onnx.export()`                                |
| `torch.profiler`        | Performance profiling                        | `torch.profiler.profile()`                           |

---

## 🔄 5. Real-World Workflow

> 🎯 *Goal: See exactly how PyTorch is used in a complete deep learning project.*

---

### 🟢 Beginner Workflow: Train a Simple Classifier

```
Step 1 → Prepare data (tensors or Dataset)
Step 2 → Define model (nn.Module subclass)
Step 3 → Choose loss function and optimizer
Step 4 → Training loop (forward → loss → zero_grad → backward → step)
Step 5 → Evaluate on validation set
Step 6 → Save best model
```

**Full beginner example — classify 2D points:**

```python
import torch
import torch.nn as nn
from torch.utils.data import DataLoader, TensorDataset

# 1. Generate toy data (two concentric circles)
from sklearn.datasets import make_circles
import numpy as np

X, y = make_circles(n_samples=1000, noise=0.05, random_state=42)
X = torch.tensor(X, dtype=torch.float32)
y = torch.tensor(y, dtype=torch.long)

dataset = TensorDataset(X, y)
train_ds, val_ds = torch.utils.data.random_split(dataset, [800, 200])
train_loader = DataLoader(train_ds, batch_size=32, shuffle=True)
val_loader   = DataLoader(val_ds,   batch_size=64, shuffle=False)

# 2. Define model
class CircleClassifier(nn.Module):
    def __init__(self):
        super().__init__()
        self.net = nn.Sequential(
            nn.Linear(2, 16), nn.ReLU(),
            nn.Linear(16, 16), nn.ReLU(),
            nn.Linear(16, 2)
        )
    def forward(self, x):
        return self.net(x)

device = torch.device('cuda' if torch.cuda.is_available() else 'cpu')
model = CircleClassifier().to(device)

# 3. Loss & Optimizer
criterion = nn.CrossEntropyLoss()
optimizer = torch.optim.Adam(model.parameters(), lr=1e-3)

# 4. Training loop
for epoch in range(50):
    model.train()
    epoch_loss = 0
    for xb, yb in train_loader:
        xb, yb = xb.to(device), yb.to(device)
        pred = model(xb)
        loss = criterion(pred, yb)
        optimizer.zero_grad()
        loss.backward()
        optimizer.step()
        epoch_loss += loss.item()

    # 5. Validate every 10 epochs
    if (epoch + 1) % 10 == 0:
        model.eval()
        correct = 0
        with torch.no_grad():
            for xb, yb in val_loader:
                xb, yb = xb.to(device), yb.to(device)
                pred = model(xb).argmax(dim=1)
                correct += (pred == yb).sum().item()
        acc = 100.0 * correct / len(val_ds)
        print(f"Epoch {epoch+1:3d} | Loss: {epoch_loss/len(train_loader):.4f} | Val Acc: {acc:.1f}%")

# 6. Save
torch.save(model.state_dict(), 'circle_classifier.pth')
```

---

### 🔵 Professional Workflow: Full Training Pipeline

```
Step 1  → Config management (hyperparameters, paths)
Step 2  → Dataset class with augmentation/transforms
Step 3  → Model class (modular, configurable)
Step 4  → Training utilities (train_epoch, evaluate functions)
Step 5  → LR scheduler setup
Step 6  → Experiment tracking (W&B or TensorBoard)
Step 7  → Main training loop with early stopping
Step 8  → Best model checkpointing
Step 9  → Evaluation on test set
Step 10 → Export for deployment (ONNX / TorchScript)
```

```python
import torch
import torch.nn as nn
from torch.cuda.amp import GradScaler, autocast
from torch.optim.lr_scheduler import CosineAnnealingLR

# Config
config = {
    'lr': 1e-3, 'epochs': 100, 'batch_size': 128,
    'patience': 10, 'grad_clip': 1.0, 'weight_decay': 1e-4
}

device = torch.device('cuda' if torch.cuda.is_available() else 'cpu')
scaler = GradScaler()  # For mixed precision training

model = YourModel().to(device)
optimizer = torch.optim.AdamW(model.parameters(), lr=config['lr'],
                               weight_decay=config['weight_decay'])
scheduler = CosineAnnealingLR(optimizer, T_max=config['epochs'])
criterion = nn.CrossEntropyLoss(label_smoothing=0.1)

best_val_acc = 0.0
patience_counter = 0

for epoch in range(config['epochs']):
    # --- Train ---
    model.train()
    for xb, yb in train_loader:
        xb, yb = xb.to(device), yb.to(device)
        optimizer.zero_grad(set_to_none=True)  # Faster than zero_grad()

        with autocast():   # Mixed precision forward pass
            pred = model(xb)
            loss = criterion(pred, yb)

        scaler.scale(loss).backward()
        scaler.unscale_(optimizer)
        torch.nn.utils.clip_grad_norm_(model.parameters(), config['grad_clip'])
        scaler.step(optimizer)
        scaler.update()

    scheduler.step()

    # --- Validate ---
    val_loss, val_acc = evaluate(model, val_loader, criterion, device)

    # --- Checkpoint ---
    if val_acc > best_val_acc:
        best_val_acc = val_acc
        patience_counter = 0
        torch.save({'model': model.state_dict(), 'epoch': epoch,
                    'val_acc': val_acc}, 'best_model.pth')
    else:
        patience_counter += 1
        if patience_counter >= config['patience']:
            print(f"Early stopping at epoch {epoch+1}")
            break

    print(f"Epoch {epoch+1} | Val Acc: {val_acc:.2f}% | LR: {scheduler.get_last_lr()[0]:.6f}")

print(f"Best val accuracy: {best_val_acc:.2f}%")
```

---

## 🧪 6. Hands-on Practice

> 🎯 *Goal: Build real things, not just run tutorials.*

---

### 🟢 Beginner Project: MNIST Digit Classifier (Fully Connected)

**Goal:** Train a neural network to recognize handwritten digits (0–9).
**Estimated Time:** 1–2 hours
**Skills Used:** Tensors, nn.Module, DataLoader, training loop, CrossEntropyLoss

```python
import torch
import torch.nn as nn
import torchvision
import torchvision.transforms as transforms
from torch.utils.data import DataLoader

# Data
transform = transforms.Compose([
    transforms.ToTensor(),
    transforms.Normalize((0.1307,), (0.3081,))  # MNIST mean and std
])

train_data = torchvision.datasets.MNIST('./data', train=True,  download=True, transform=transform)
test_data  = torchvision.datasets.MNIST('./data', train=False, download=True, transform=transform)

train_loader = DataLoader(train_data, batch_size=64, shuffle=True,  num_workers=2)
test_loader  = DataLoader(test_data,  batch_size=64, shuffle=False, num_workers=2)

# Model
class MNISTNet(nn.Module):
    def __init__(self):
        super().__init__()
        self.net = nn.Sequential(
            nn.Flatten(),                    # (B, 1, 28, 28) → (B, 784)
            nn.Linear(784, 256), nn.ReLU(),
            nn.Dropout(0.3),
            nn.Linear(256, 128), nn.ReLU(),
            nn.Dropout(0.3),
            nn.Linear(128, 10)               # 10 classes
        )
    def forward(self, x):
        return self.net(x)

device    = torch.device('cuda' if torch.cuda.is_available() else 'cpu')
model     = MNISTNet().to(device)
optimizer = torch.optim.Adam(model.parameters(), lr=1e-3)
criterion = nn.CrossEntropyLoss()

# Train for 5 epochs
for epoch in range(5):
    model.train()
    for xb, yb in train_loader:
        xb, yb = xb.to(device), yb.to(device)
        pred = model(xb)
        loss = criterion(pred, yb)
        optimizer.zero_grad()
        loss.backward()
        optimizer.step()

    model.eval()
    correct = 0
    with torch.no_grad():
        for xb, yb in test_loader:
            xb, yb = xb.to(device), yb.to(device)
            correct += (model(xb).argmax(1) == yb).sum().item()
    print(f"Epoch {epoch+1}: Test Acc = {100.0*correct/len(test_data):.2f}%")
```

✅ **You've succeeded when:** Test accuracy reaches ~98% within 5 epochs.

---

### 🔵 Intermediate Project: CIFAR-10 Image Classifier with CNN

**Goal:** Build a Convolutional Neural Network to classify 10 categories of images.
**Estimated Time:** 3–4 hours
**Skills Used:** Conv2d, BatchNorm, MaxPool, augmentation, LR scheduling

```python
import torch
import torch.nn as nn
import torchvision
import torchvision.transforms as T
from torch.utils.data import DataLoader

# Augmented transforms
train_transform = T.Compose([
    T.RandomHorizontalFlip(),
    T.RandomCrop(32, padding=4),
    T.ColorJitter(brightness=0.2, contrast=0.2),
    T.ToTensor(),
    T.Normalize((0.4914, 0.4822, 0.4465), (0.2023, 0.1994, 0.2010))
])
test_transform = T.Compose([
    T.ToTensor(),
    T.Normalize((0.4914, 0.4822, 0.4465), (0.2023, 0.1994, 0.2010))
])

train_data = torchvision.datasets.CIFAR10('./data', train=True,  download=True, transform=train_transform)
test_data  = torchvision.datasets.CIFAR10('./data', train=False, download=True, transform=test_transform)
train_loader = DataLoader(train_data, batch_size=128, shuffle=True, num_workers=4, pin_memory=True)
test_loader  = DataLoader(test_data,  batch_size=128, shuffle=False, num_workers=4)

# CNN Architecture
class CIFAR10CNN(nn.Module):
    def __init__(self):
        super().__init__()
        self.features = nn.Sequential(
            # Block 1
            nn.Conv2d(3, 32, 3, padding=1), nn.BatchNorm2d(32), nn.ReLU(),
            nn.Conv2d(32, 32, 3, padding=1), nn.BatchNorm2d(32), nn.ReLU(),
            nn.MaxPool2d(2), nn.Dropout2d(0.2),   # 32x32 → 16x16

            # Block 2
            nn.Conv2d(32, 64, 3, padding=1), nn.BatchNorm2d(64), nn.ReLU(),
            nn.Conv2d(64, 64, 3, padding=1), nn.BatchNorm2d(64), nn.ReLU(),
            nn.MaxPool2d(2), nn.Dropout2d(0.3),   # 16x16 → 8x8

            # Block 3
            nn.Conv2d(64, 128, 3, padding=1), nn.BatchNorm2d(128), nn.ReLU(),
            nn.Conv2d(128, 128, 3, padding=1), nn.BatchNorm2d(128), nn.ReLU(),
            nn.MaxPool2d(2), nn.Dropout2d(0.4),   # 8x8 → 4x4
        )
        self.classifier = nn.Sequential(
            nn.AdaptiveAvgPool2d((1, 1)),  # Global average pooling → (128,1,1)
            nn.Flatten(),
            nn.Linear(128, 256), nn.ReLU(), nn.Dropout(0.5),
            nn.Linear(256, 10)
        )

    def forward(self, x):
        return self.classifier(self.features(x))

device    = torch.device('cuda' if torch.cuda.is_available() else 'cpu')
model     = CIFAR10CNN().to(device)
optimizer = torch.optim.AdamW(model.parameters(), lr=1e-3, weight_decay=1e-4)
criterion = nn.CrossEntropyLoss(label_smoothing=0.1)
scheduler = torch.optim.lr_scheduler.CosineAnnealingLR(optimizer, T_max=50)

best_acc  = 0.0
for epoch in range(50):
    model.train()
    for xb, yb in train_loader:
        xb, yb = xb.to(device), yb.to(device)
        loss = criterion(model(xb), yb)
        optimizer.zero_grad()
        loss.backward()
        optimizer.step()
    scheduler.step()

    model.eval()
    correct = 0
    with torch.no_grad():
        for xb, yb in test_loader:
            xb, yb = xb.to(device), yb.to(device)
            correct += (model(xb).argmax(1) == yb).sum().item()
    acc = 100.0 * correct / len(test_data)
    if acc > best_acc:
        best_acc = acc
        torch.save(model.state_dict(), 'cifar10_best.pth')
    if (epoch+1) % 10 == 0:
        print(f"Epoch {epoch+1}/50 | Test Acc: {acc:.2f}% | Best: {best_acc:.2f}%")
```

✅ **You've succeeded when:** Test accuracy exceeds 85% (fine-tuning can push to ~92%).

---

### 🔴 Advanced Project: Custom Transformer for Text Classification

**Goal:** Implement a mini-Transformer encoder from scratch and use it to classify text sentiment.
**Estimated Time:** 1–2 days
**Skills Used:** nn.Embedding, MultiheadAttention, positional encoding, Transformer blocks, NLP pipeline

```python
import torch
import torch.nn as nn
import math

class PositionalEncoding(nn.Module):
    def __init__(self, d_model, max_len=5000, dropout=0.1):
        super().__init__()
        self.dropout = nn.Dropout(p=dropout)
        pe = torch.zeros(max_len, d_model)
        position = torch.arange(0, max_len, dtype=torch.float).unsqueeze(1)
        div_term = torch.exp(torch.arange(0, d_model, 2).float() * (-math.log(10000.0) / d_model))
        pe[:, 0::2] = torch.sin(position * div_term)
        pe[:, 1::2] = torch.cos(position * div_term)
        self.register_buffer('pe', pe.unsqueeze(0))  # (1, max_len, d_model)

    def forward(self, x):
        return self.dropout(x + self.pe[:, :x.size(1)])

class TransformerClassifier(nn.Module):
    def __init__(self, vocab_size, d_model=128, nhead=4, num_layers=2,
                 num_classes=2, max_len=256, dropout=0.1):
        super().__init__()
        self.embedding = nn.Embedding(vocab_size, d_model, padding_idx=0)
        self.pos_enc   = PositionalEncoding(d_model, max_len, dropout)

        encoder_layer  = nn.TransformerEncoderLayer(
            d_model=d_model, nhead=nhead,
            dim_feedforward=d_model * 4,
            dropout=dropout, batch_first=True
        )
        self.transformer = nn.TransformerEncoder(encoder_layer, num_layers=num_layers)
        self.norm     = nn.LayerNorm(d_model)
        self.head     = nn.Linear(d_model, num_classes)

    def forward(self, x, padding_mask=None):
        # x: (B, seq_len) token IDs
        x = self.embedding(x)         # (B, seq_len, d_model)
        x = self.pos_enc(x)           # Add positional info
        x = self.transformer(x, src_key_padding_mask=padding_mask)
        x = self.norm(x)
        x = x[:, 0, :]               # Use [CLS] token (first token)
        return self.head(x)           # (B, num_classes)

# Usage
vocab_size = 10000
model = TransformerClassifier(vocab_size=vocab_size, d_model=128, nhead=4, num_layers=2, num_classes=2)
print(f"Parameters: {sum(p.numel() for p in model.parameters()):,}")

# Dummy batch: batch_size=4, seq_len=64
x = torch.randint(1, vocab_size, (4, 64))
padding_mask = (x == 0)    # True where padding token
out = model(x, padding_mask)
print(out.shape)   # (4, 2)
```

🔥 **Challenge:** Train this on the IMDb sentiment dataset from HuggingFace Datasets. Use a tokenizer from `torchtext` or HuggingFace `tokenizers`. Aim for >90% accuracy.

---

## ⚠️ 7. Common Mistakes

> 🎯 *Goal: Avoid the traps that cost weeks of debugging.*

---

### ❌ Mistake 1: Forgetting `model.train()` and `model.eval()`

**Why it happens:** Beginners don't know that BatchNorm and Dropout behave differently during training vs inference.
**What goes wrong:** Validation accuracy is randomly wrong. Model behaves erratically at test time.

```python
# ❌ Wrong:
model = MyModel()
for epoch in range(10):
    for xb, yb in train_loader:
        pred = model(xb)    # Dropout is active — fine
        ...
    with torch.no_grad():
        for xb, yb in val_loader:
            pred = model(xb)   # Dropout STILL active → wrong results!

# ✅ Right:
for epoch in range(10):
    model.train()    # Enables Dropout, BatchNorm training behavior
    for xb, yb in train_loader:
        ...

    model.eval()     # Disables Dropout, BatchNorm uses running stats
    with torch.no_grad():
        for xb, yb in val_loader:
            ...
```

---

### ❌ Mistake 2: Not Zeroing Gradients

**Why it happens:** Beginners don't know that `.backward()` *accumulates* gradients by default.
**What goes wrong:** Gradients from previous batches pollute current batch → training diverges.

```python
# ❌ Wrong:
for xb, yb in train_loader:
    pred = model(xb)
    loss = criterion(pred, yb)
    loss.backward()    # Gradients ACCUMULATE from batch to batch!
    optimizer.step()

# ✅ Right:
for xb, yb in train_loader:
    optimizer.zero_grad()   # Clear gradients FIRST
    pred = model(xb)
    loss = criterion(pred, yb)
    loss.backward()
    optimizer.step()

# Even faster alternative:
optimizer.zero_grad(set_to_none=True)  # Sets to None instead of 0 — saves memory
```

---

### ❌ Mistake 3: Using Softmax Before CrossEntropyLoss

**Why it happens:** Beginners think they need to produce probabilities as output.
**What goes wrong:** `nn.CrossEntropyLoss` already applies `log_softmax` internally. Double-applying softmax makes gradients vanish (log(softmax(softmax(x))) ≈ -∞).

```python
# ❌ Wrong:
class BadModel(nn.Module):
    def forward(self, x):
        x = self.fc(x)
        return torch.softmax(x, dim=1)   # WRONG — CrossEntropyLoss does this!

# ✅ Right: Return raw logits
class GoodModel(nn.Module):
    def forward(self, x):
        return self.fc(x)   # Raw logits — CrossEntropyLoss handles the rest

# If you NEED probabilities (for inference):
probs = torch.softmax(model(x), dim=1)
predicted_class = probs.argmax(dim=1)
```

---

### ❌ Mistake 4: Moving Data to GPU Inside the Loop (Slowly)

**Why it happens:** Placing `.to(device)` call outside the training data loop.
**What goes wrong:** Massive slowdown, excessive GPU memory allocation/deallocation.

```python
# ❌ Wrong:
x_gpu = entire_dataset.to(device)   # Moving all data to GPU — likely OOM!

# Also wrong:
model = model.cuda()
for xb, yb in train_loader:
    pred = model(xb)    # xb is still on CPU! Error or silent CPU slowdown

# ✅ Right:
for xb, yb in train_loader:
    xb = xb.to(device, non_blocking=True)  # non_blocking for async transfer
    yb = yb.to(device, non_blocking=True)
    pred = model(xb)
```

---

### ❌ Mistake 5: Calling `.item()` Inside the Training Loop

**Why it happens:** Wanting to print the loss every step.
**What goes wrong:** `.item()` synchronizes CPU and GPU — called every step it creates a massive bottleneck (can slow training by 5-10x).

```python
# ❌ Wrong:
total_loss = 0
for xb, yb in train_loader:
    loss = criterion(model(xb), yb)
    ...
    total_loss += loss.item()   # GPU-CPU sync EVERY step!
    print(f"Step loss: {loss.item():.4f}")  # 100x slowdown

# ✅ Right:
total_loss = 0
for xb, yb in train_loader:
    loss = criterion(model(xb), yb)
    ...
    total_loss += loss.detach()   # Stay on GPU, no sync

avg_loss = total_loss.item() / len(train_loader)  # Sync once per epoch
print(f"Epoch loss: {avg_loss:.4f}")
```

---

### ❌ Mistake 6: Wrong Tensor Shape for Loss Functions

**Why it happens:** Confusing expected tensor shapes for different losses.

```python
# CrossEntropyLoss expects:
# predictions: (N, C) — N samples, C classes (raw logits)
# targets:     (N,)   — N integer class indices

# ❌ Wrong:
pred = model(x)              # (32, 10)
loss = criterion(pred, y)    # y shape (32, 1) → ERROR!
loss = criterion(pred, y)    # y is one-hot (32, 10) → ERROR!

# ✅ Right:
loss = criterion(pred, y)    # y shape (32,) — integer class indices

# BCEWithLogitsLoss expects:
# predictions: (N,) or (N, 1) — binary logits
# targets:     (N,) — float values 0.0 or 1.0
loss = nn.BCEWithLogitsLoss()(pred.squeeze(), y.float())

# MSELoss: both must have same shape
loss = nn.MSELoss()(pred, y.float())   # (N,) vs (N,)
```

---

### ❌ Mistake 7: Not Using `torch.no_grad()` During Inference

**Why it happens:** Forgetting that autograd is always on.
**What goes wrong:** 2-3x slower inference. Unnecessary memory usage building computation graphs.

```python
# ❌ Wrong:
model.eval()
predictions = model(test_data)   # Graph still being built!

# ✅ Right:
model.eval()
with torch.no_grad():
    predictions = model(test_data)   # No graph → faster, less memory

# Or use the decorator for an entire function:
@torch.no_grad()
def predict(model, x):
    return model(x)
```

---

### ❌ Mistake 8: In-place Operations on `requires_grad` Tensors

**Why it happens:** Using NumPy-style in-place operations.
**What goes wrong:** Autograd can't track in-place changes → gradient computation fails.

```python
# ❌ Wrong:
x = torch.randn(3, requires_grad=True)
x += 1        # In-place operation — breaks autograd!

# ✅ Right:
x = x + 1    # Creates new tensor — autograd tracks it properly

# Also wrong inside model:
def forward(self, x):
    x *= 2   # In-place on tensor that needs gradients — ERROR!
    return x

# Right:
def forward(self, x):
    x = x * 2    # New tensor
    return x
```

---

## 🔥 8. Pro Tips & Hidden Tricks

> 🎯 *Goal: Level up with knowledge most tutorials never share.*

---

### 💎 Tip 1: Mixed Precision Training (2x Speedup for Free)

Automatic Mixed Precision (AMP) uses float16 for forward/backward pass and float32 for weight updates. Nearly free 2x speedup on modern GPUs.

```python
from torch.cuda.amp import GradScaler, autocast

scaler = GradScaler()

for xb, yb in train_loader:
    xb, yb = xb.to(device), yb.to(device)
    optimizer.zero_grad()

    with autocast():     # Forward pass in float16
        pred = model(xb)
        loss = criterion(pred, yb)

    scaler.scale(loss).backward()   # Scaled backward pass
    scaler.step(optimizer)          # Unscale and update
    scaler.update()                 # Update scale factor
```

---

### 💎 Tip 2: `set_to_none=True` for Faster Gradient Zeroing

```python
# Slower: fills gradient tensors with 0
optimizer.zero_grad()

# Faster: deallocates gradient tensors entirely (saves memory)
optimizer.zero_grad(set_to_none=True)
```

---

### 💎 Tip 3: `torch.compile()` — 2-5x Speedup (PyTorch 2.0+)

Compiles your model with TorchInductor backend. One line, huge speedup.

```python
import torch

model = MyModel()
model = torch.compile(model)   # PyTorch 2.0+ — compiles model graph

# Training proceeds normally — PyTorch handles the rest
```

---

### 💎 Tip 4: `pin_memory=True` + `non_blocking=True` for Faster Data Transfer

```python
train_loader = DataLoader(dataset, batch_size=64, pin_memory=True)

for xb, yb in train_loader:
    # non_blocking=True allows overlap of data transfer with GPU compute
    xb = xb.to(device, non_blocking=True)
    yb = yb.to(device, non_blocking=True)
```

---

### 💎 Tip 5: Register Buffers for Non-Trainable Parameters

Buffers are tensors that are part of the model but have no gradients — they move with `.to(device)` automatically.

```python
class ModelWithBuffer(nn.Module):
    def __init__(self):
        super().__init__()
        self.fc = nn.Linear(10, 5)
        # Register as buffer — saved in state_dict, moves with .to()
        self.register_buffer('running_mean', torch.zeros(10))

    def forward(self, x):
        x = x - self.running_mean   # Buffer auto-moved to correct device
        return self.fc(x)
```

---

### 💎 Tip 6: Gradient Checkpointing (Trade Compute for Memory)

For huge models, recomputes activations during backward pass instead of storing them.

```python
from torch.utils.checkpoint import checkpoint

class BigModel(nn.Module):
    def forward(self, x):
        # Recompute block1's output during backward instead of storing it
        x = checkpoint(self.block1, x, use_reentrant=False)
        x = self.block2(x)
        return x
```

---

### 💎 Tip 7: `einops` for Readable Tensor Manipulation

`einops` makes complex reshape operations readable and less error-prone.

```python
# pip install einops
from einops import rearrange, repeat, reduce

x = torch.randn(32, 3, 224, 224)   # (batch, channel, H, W)

# Rearrange
x_hwc = rearrange(x, 'b c h w -> b h w c')     # (32, 224, 224, 3)
patches = rearrange(x, 'b c (h p1) (w p2) -> b (h w) (p1 p2 c)', p1=16, p2=16)

# Reduce
global_avg = reduce(x, 'b c h w -> b c', 'mean')  # Global avg pool

# Repeat
x_repeated = repeat(x[:1], 'b c h w -> (b n) c h w', n=4)  # Tile
```

---

### 💎 Tip 8: Use `tqdm` for Training Progress

```python
from tqdm import tqdm

for epoch in range(num_epochs):
    model.train()
    pbar = tqdm(train_loader, desc=f'Epoch {epoch+1}/{num_epochs}')
    for xb, yb in pbar:
        loss = train_step(xb, yb)
        pbar.set_postfix({'loss': f'{loss:.4f}'})  # Live update
```

---

### 🛠️ Recommended Tools & Resources

| Tool / Resource            | What It's For                                  | Notes                                      |
|----------------------------|------------------------------------------------|--------------------------------------------|
| `torchvision`              | Image datasets, transforms, pre-trained models | `pip install torchvision`                  |
| `timm` (PyTorch Image Models)| 700+ pre-trained vision models              | `pip install timm`                         |
| HuggingFace `transformers` | Pre-trained NLP/Vision Transformers            | `pip install transformers`                 |
| `einops`                   | Readable tensor manipulations                  | `pip install einops`                       |
| `wandb`                    | Experiment tracking and visualization          | `pip install wandb`                        |
| TensorBoard                | Built-in training visualization                | `pip install tensorboard`                  |
| `tqdm`                     | Progress bars for training loops               | `pip install tqdm`                         |
| `lightning` (PyTorch Lightning) | Structured training framework           | `pip install lightning`                    |
| FastAI                     | High-level PyTorch API for quick prototyping   | `pip install fastai`                       |
| PyTorch Official Docs      | Authoritative reference                        | pytorch.org/docs                           |
| d2l.ai                     | Dive into Deep Learning (free book)            | d2l.ai                                     |

---

## 🚀 9. Advanced Concepts (Expert Level)

> 🎯 *Goal: Master the techniques used in production AI systems and research.*

---

### Advanced Concept 1: Transfer Learning & Fine-Tuning

Don't train from scratch — use a pre-trained model and adapt it to your task. This is how 90% of real-world deep learning is done.

```python
import torchvision.models as models
import torch.nn as nn

# Load pre-trained ResNet50 (trained on ImageNet)
model = models.resnet50(weights=models.ResNet50_Weights.DEFAULT)

# Strategy 1: Feature Extraction — Freeze backbone, train only head
for param in model.parameters():
    param.requires_grad = False    # Freeze all layers

# Replace final classifier for our task (e.g., 5 classes)
in_features = model.fc.in_features
model.fc = nn.Sequential(
    nn.Linear(in_features, 256),
    nn.ReLU(), nn.Dropout(0.3),
    nn.Linear(256, 5)
)
# Only model.fc parameters have requires_grad=True

# Strategy 2: Fine-Tuning — Unfreeze later layers
# Freeze everything first
for param in model.parameters():
    param.requires_grad = False

# Unfreeze layer4 and classifier
for param in model.layer4.parameters():
    param.requires_grad = True
for param in model.fc.parameters():
    param.requires_grad = True

# Use different LRs for different parts
optimizer = torch.optim.AdamW([
    {'params': model.layer4.parameters(), 'lr': 1e-4},  # Lower LR for backbone
    {'params': model.fc.parameters(),     'lr': 1e-3},  # Higher LR for head
], weight_decay=1e-4)

# Check trainable params
trainable = sum(p.numel() for p in model.parameters() if p.requires_grad)
total     = sum(p.numel() for p in model.parameters())
print(f"Trainable: {trainable:,} / Total: {total:,} ({100*trainable/total:.1f}%)")
```

---

### Advanced Concept 2: Custom Loss Functions

Sometimes standard losses aren't enough. You can write your own — they must be differentiable.

```python
import torch
import torch.nn as nn
import torch.nn.functional as F

# Focal Loss — down-weights easy examples, focuses on hard ones
# Used in object detection (RetinaNet)
class FocalLoss(nn.Module):
    def __init__(self, gamma=2.0, alpha=0.25):
        super().__init__()
        self.gamma = gamma
        self.alpha = alpha

    def forward(self, inputs, targets):
        BCE_loss = F.binary_cross_entropy_with_logits(inputs, targets, reduction='none')
        pt = torch.exp(-BCE_loss)
        focal_weight = self.alpha * (1 - pt) ** self.gamma
        return (focal_weight * BCE_loss).mean()

# Dice Loss — better than BCE for imbalanced segmentation
class DiceLoss(nn.Module):
    def __init__(self, smooth=1.0):
        super().__init__()
        self.smooth = smooth

    def forward(self, pred, target):
        pred = torch.sigmoid(pred)
        intersection = (pred * target).sum(dim=(2, 3))
        dice = (2.0 * intersection + self.smooth) / \
               (pred.sum(dim=(2,3)) + target.sum(dim=(2,3)) + self.smooth)
        return 1 - dice.mean()

# Combined loss
class CombinedLoss(nn.Module):
    def __init__(self, dice_weight=0.5, bce_weight=0.5):
        super().__init__()
        self.dice = DiceLoss()
        self.bce  = nn.BCEWithLogitsLoss()
        self.dice_weight = dice_weight
        self.bce_weight  = bce_weight

    def forward(self, pred, target):
        return self.dice_weight * self.dice(pred, target) + \
               self.bce_weight  * self.bce(pred, target)
```

---

### Advanced Concept 3: Learning Rate Scheduling

The learning rate is the single most impactful hyperparameter. Scheduling it correctly is crucial.

```python
import torch
from torch.optim.lr_scheduler import (
    StepLR, MultiStepLR, ExponentialLR,
    CosineAnnealingLR, OneCycleLR, ReduceLROnPlateau
)

optimizer = torch.optim.Adam(model.parameters(), lr=1e-3)

# Decay by 0.1 every 30 epochs
scheduler = StepLR(optimizer, step_size=30, gamma=0.1)

# Decay at specific epochs
scheduler = MultiStepLR(optimizer, milestones=[50, 80, 100], gamma=0.1)

# Cosine annealing — most popular for image classification
scheduler = CosineAnnealingLR(optimizer, T_max=100, eta_min=1e-6)

# One Cycle — cyclical LR, very fast convergence (1 epoch sometimes!)
scheduler = OneCycleLR(optimizer, max_lr=1e-2,
                       steps_per_epoch=len(train_loader), epochs=10)

# Reduce when plateauing
scheduler = ReduceLROnPlateau(optimizer, mode='max', factor=0.5,
                               patience=5, verbose=True)
scheduler.step(val_accuracy)   # Pass metric

# Warmup + Cosine (most common in Transformers)
from torch.optim.lr_scheduler import LinearLR, CosineAnnealingLR, SequentialLR
warmup = LinearLR(optimizer, start_factor=0.01, end_factor=1.0, total_iters=5)
cosine = CosineAnnealingLR(optimizer, T_max=95, eta_min=1e-6)
scheduler = SequentialLR(optimizer, schedulers=[warmup, cosine], milestones=[5])
```

---

### Advanced Concept 4: Distributed Training (Multi-GPU)

Scale training across multiple GPUs with PyTorch's DistributedDataParallel (DDP).

```python
import torch
import torch.distributed as dist
from torch.nn.parallel import DistributedDataParallel as DDP
import os

def setup(rank, world_size):
    os.environ['MASTER_ADDR'] = 'localhost'
    os.environ['MASTER_PORT'] = '12355'
    dist.init_process_group("nccl", rank=rank, world_size=world_size)

def cleanup():
    dist.destroy_process_group()

def train_ddp(rank, world_size):
    setup(rank, world_size)

    # Each process uses one GPU
    model = MyModel().to(rank)
    model = DDP(model, device_ids=[rank])    # Wrap in DDP

    # Data needs DistributedSampler
    sampler = torch.utils.data.DistributedSampler(
        dataset, num_replicas=world_size, rank=rank)
    loader = DataLoader(dataset, sampler=sampler, batch_size=64)

    optimizer = torch.optim.Adam(model.parameters())

    for epoch in range(100):
        sampler.set_epoch(epoch)   # Ensure different shuffling each epoch
        for xb, yb in loader:
            xb, yb = xb.to(rank), yb.to(rank)
            loss = criterion(model(xb), yb)
            optimizer.zero_grad()
            loss.backward()    # DDP auto-syncs gradients across GPUs
            optimizer.step()

    cleanup()

# Launch with torch.multiprocessing
import torch.multiprocessing as mp
world_size = torch.cuda.device_count()
mp.spawn(train_ddp, args=(world_size,), nprocs=world_size)
```

---

### Advanced Concept 5: TorchScript — Deploy Without Python

Compile your model to be Python-independent for production deployment.

```python
import torch

model = MyModel()
model.eval()

# Method 1: Tracing — records operations for a given input
example_input = torch.randn(1, 3, 224, 224)
traced_model = torch.jit.trace(model, example_input)
traced_model.save('model_traced.pt')

# Method 2: Scripting — handles control flow (if/else, loops)
@torch.jit.script
def activate(x: torch.Tensor, mode: str) -> torch.Tensor:
    if mode == 'relu':
        return torch.relu(x)
    else:
        return torch.sigmoid(x)

scripted_model = torch.jit.script(model)
scripted_model.save('model_scripted.pt')

# Load without Python class definition
loaded = torch.jit.load('model_traced.pt')
output = loaded(example_input)

# Export to ONNX for framework-independent deployment
torch.onnx.export(model, example_input, 'model.onnx',
                  opset_version=17,
                  input_names=['input'],
                  output_names=['output'],
                  dynamic_axes={'input': {0: 'batch_size'}})
```

---

### ⚡ Performance & Optimization

| Optimization Technique                   | Impact | When to Use                                         |
|------------------------------------------|--------|-----------------------------------------------------|
| Mixed Precision (`autocast`)             | High   | Always, on any NVIDIA GPU (Ampere+: huge benefit)   |
| `torch.compile()` (PyTorch 2.0+)        | High   | Production training, PyTorch 2.0+ environment       |
| `DataLoader` with multiple workers       | High   | Any GPU training with non-trivial data loading      |
| `pin_memory=True` + `non_blocking=True`  | Medium | Any GPU training                                    |
| Gradient checkpointing                   | Medium | Models larger than GPU memory (e.g., LLMs)          |
| Gradient accumulation                    | Medium | Simulating large batch with limited VRAM            |
| `set_to_none=True` in `zero_grad()`     | Low    | Always (tiny free speedup)                          |
| Fused optimizers (`fused=True` in AdamW) | Medium | PyTorch 2.0+, CUDA only                            |
| `torch.backends.cudnn.benchmark = True` | Medium | Fixed input size (image classification/detection)   |
| `channels_last` memory format            | Medium | CNNs on Ampere+ GPUs                               |

```python
# channels_last (NHWC) — faster for Conv2d on modern GPUs
model = model.to(memory_format=torch.channels_last)
input = input.to(memory_format=torch.channels_last)

# Enable cudnn benchmark
torch.backends.cudnn.benchmark = True   # Best algo for fixed input sizes

# Fused AdamW (PyTorch 2.0+)
optimizer = torch.optim.AdamW(model.parameters(), lr=1e-3, fused=True)
```

---

## 🗺️ 10. Complete Roadmap

> 🎯 *Goal: Know exactly what to learn and in what order.*

---

### 📅 Week-by-Week Learning Path

```
PHASE 1 — PYTORCH FOUNDATION (Week 1-2)
├── Day 1-2:   Tensors — creation, ops, indexing, broadcasting
├── Day 3-4:   Autograd — requires_grad, backward, no_grad, detach
├── Day 5-6:   nn.Module — building blocks, forward(), parameter counting
└── Day 7:     Mini project: Linear Regression from scratch with autograd

PHASE 2 — TRAINING ESSENTIALS (Week 3-4)
├── Day 8-9:   Loss functions, optimizers, LR schedulers
├── Day 10-11: Dataset, DataLoader, custom datasets
├── Day 12-13: Full training loop — train/eval modes, checkpointing
└── Day 14:    Project: MNIST digit classifier (>98% accuracy)

PHASE 3 — COMPUTER VISION (Week 5-6)
├── Day 15-16: Conv2d, pooling, BatchNorm — understanding CNNs
├── Day 17-18: torchvision — pre-trained models, transforms, augmentation
├── Day 19-20: Transfer learning and fine-tuning
└── Day 21:    Project: CIFAR-10 classifier (>85% accuracy)

PHASE 4 — NLP & SEQUENCES (Week 7-8)
├── Day 22-23: Embeddings, LSTM, GRU — sequence modeling
├── Day 24-25: Attention mechanism from scratch
├── Day 26-27: Transformers — self-attention, positional encoding
└── Day 28:    Project: Sentiment classifier with Transformer

PHASE 5 — ADVANCED TECHNIQUES (Week 9-12)
├── Week 9:    Mixed precision, torch.compile, gradient clipping
├── Week 10:   Custom loss functions, advanced schedulers
├── Week 11:   HuggingFace integration — fine-tune BERT/GPT2
└── Week 12:   Full project: Fine-tune a foundation model for your domain

PHASE 6 — PRODUCTION & DEPLOYMENT (Month 4+)
├── TorchScript, ONNX export, torch.serve
├── Distributed training (DDP, FSDP)
├── Quantization, pruning for edge deployment
└── Contribute to open-source PyTorch projects
```

---

### 🏁 Milestone Checklist

- [ ] I understand tensors as multi-dimensional arrays with GPU support
- [ ] I can explain autograd and backpropagation in plain English
- [ ] I have built an `nn.Module` subclass from scratch
- [ ] I have written a complete training loop with proper train/eval modes
- [ ] I trained MNIST to >98% accuracy
- [ ] I trained CIFAR-10 with a CNN to >85% accuracy
- [ ] I have used transfer learning with a pre-trained model
- [ ] I understand the Transformer architecture
- [ ] I have used mixed precision training
- [ ] I can export a model for deployment (TorchScript or ONNX)
- [ ] I have fine-tuned a HuggingFace model on a custom dataset

---

## 🧩 11. Bonus Deep Insights

> 🎯 *Things most people spend years figuring out — here upfront.*

---

### 🔮 Mental Model: The Gradient Tape

Think of the autograd engine as a **video recorder** that watches everything that happens to your tensors. During the forward pass, it records every operation in order. During `.backward()`, it plays the tape in reverse, computing derivatives at each step using the chain rule.

This is why:
- Operations on tensors with `requires_grad=False` are never recorded (faster)
- `detach()` cuts the tape — nothing before the detach is tracked
- `torch.no_grad()` pauses the recorder entirely

Whenever you're confused about gradients, ask: "What did the tape record during the forward pass?"

---

### 🤫 Secret 1: Broadcasting Is Powerful but Dangerous

Broadcasting lets tensors of different shapes operate together — but wrong shapes give silent errors.

```python
# These work (broadcasting):
a = torch.randn(3, 4)   # (3, 4)
b = torch.randn(4,)     # (4,) — broadcasts to (3, 4)
c = a + b               # Works!

a = torch.randn(3, 4)
b = torch.randn(3, 1)   # (3, 1) — broadcasts to (3, 4)
c = a + b               # Works!

# This is DANGEROUS (silent wrong result):
a = torch.randn(3, 4)
b = torch.randn(4, 3)   # You might think this is wrong...
# c = a + b             # ERROR — shapes don't broadcast correctly
# But:
c = a + b.T             # Works — now (3,4) + (3,4). Is this what you meant?

# ALWAYS print shapes when shapes are unexpected
print(f"a: {a.shape}, b: {b.shape}, c: {c.shape}")
```

---

### 🤫 Secret 2: The `model.parameters()` vs `model.state_dict()` Distinction

```python
# model.parameters() → generator of learnable parameters (requires_grad=True)
# Use for: passing to optimizer, counting trainable params
params = list(model.parameters())
optimizer = torch.optim.Adam(model.parameters(), lr=1e-3)

# model.state_dict() → ALL tensors in the model: parameters + buffers
# Use for: saving/loading, copying weights
state = model.state_dict()
torch.save(state, 'weights.pth')

# model.named_parameters() → (name, tensor) pairs — for selective freezing
for name, param in model.named_parameters():
    if 'layer1' in name:
        param.requires_grad = False
```

---

### 🤫 Secret 3: Reproducibility is Not Automatic

By default, PyTorch is non-deterministic. For reproducible experiments:

```python
import torch, random, numpy as np

def set_seed(seed=42):
    torch.manual_seed(seed)
    torch.cuda.manual_seed_all(seed)
    np.random.seed(seed)
    random.seed(seed)
    torch.backends.cudnn.deterministic = True
    torch.backends.cudnn.benchmark = False  # Trade speed for reproducibility

set_seed(42)
```

---

### 🤫 Secret 4: DataLoader `num_workers` Pitfall on Windows

On Windows, `num_workers > 0` causes issues because Python multiprocessing uses "spawn" instead of "fork." Always wrap DataLoader creation in `if __name__ == '__main__':`.

```python
# Windows-safe:
if __name__ == '__main__':
    loader = DataLoader(dataset, num_workers=4, ...)
    train(loader)

# Or just use:
loader = DataLoader(dataset, num_workers=0)   # Single-threaded, no issues
```

---

### 🤫 Secret 5: `.clone()` vs `.detach()` vs `.clone().detach()`

```python
x = torch.randn(3, requires_grad=True)

# detach() — shares memory, no gradient
y = x.detach()       # Shares storage with x, no grad tracking

# clone() — copies data, keeps gradient connection
z = x.clone()        # New tensor, still tracked

# clone().detach() — new tensor, no gradient (most common for "snapshot")
w = x.clone().detach()    # Independent copy, no grad

# When converting to numpy, you NEED detach (and cpu if on GPU):
arr = x.detach().cpu().numpy()
```

---

### 🧠 The Big Picture

```
              Data                        Model Zoo
              (CSV, Images, Text)          (ResNet, BERT, GPT)
                    |                           |
                    ▼                           ▼
           torchvision / HuggingFace ←── Pre-trained Weights
                    |                           |
                    ▼                           ▼
              Dataset + DataLoader ──→ Fine-tuning / Training
                                            |
                                            ▼
                              PyTorch Training Loop
                           (forward → loss → backward → step)
                                            |
                              ┌─────────────┼─────────────┐
                              ▼             ▼             ▼
                         TorchScript     ONNX        PyTorch Mobile
                              │             │               │
                         C++ Server    TensorRT       iOS / Android
```

PyTorch is not just a training tool — it's the **lingua franca** of the entire modern AI stack. Every major AI advancement of the last 5 years — GPT, Stable Diffusion, LLaMA, AlphaFold, Whisper, CLIP — was built or replicated in PyTorch. Learning it deeply means you can read, understand, and implement any published AI paper.

---

## 📌 12. Summary (Quick Revision)

> 🎯 *Everything important — at a glance.*

---

### Core Concepts (1-line each)

| Concept              | What It Means                                                            |
|----------------------|--------------------------------------------------------------------------|
| Tensor               | GPU-ready N-dimensional array; the universal data unit in PyTorch        |
| Autograd             | Automatic gradient computation via reverse-mode differentiation           |
| `requires_grad`      | Tells PyTorch to track operations on a tensor for gradient computation    |
| `nn.Module`          | Base class for all neural networks; define layers in `__init__`, flow in `forward()` |
| `forward()`          | Defines how data flows through the network; called when you do `model(x)` |
| Loss Function        | Scalar measure of how wrong predictions are; must be differentiable      |
| Optimizer            | Updates weights using gradients to reduce loss (SGD, Adam, AdamW)       |
| `backward()`         | Computes gradients of loss w.r.t. all `requires_grad` tensors            |
| `zero_grad()`        | Clears accumulated gradients before each training step                   |
| `model.train()`      | Enables Dropout and BatchNorm training behavior                          |
| `model.eval()`       | Disables Dropout, uses running stats in BatchNorm — for inference        |
| `no_grad()`          | Context manager that disables gradient tracking — faster inference        |
| DataLoader           | Batches, shuffles, and loads data in parallel using multiple workers      |
| State Dict           | Dictionary of model weights — the recommended way to save/load models    |
| Transfer Learning    | Re-use pre-trained weights; freeze backbone, train only the head         |

---

### The 5 Things to Remember

1. ✅ **Always call `model.train()` before training and `model.eval()` before validation** — Dropout/BatchNorm depend on this
2. ✅ **Always `zero_grad()` before `backward()`** — PyTorch accumulates gradients by default
3. ✅ **Don't use Softmax before CrossEntropyLoss** — it includes log_softmax internally
4. ✅ **Use `torch.no_grad()` for all inference** — no graph built, 2-3x faster
5. ✅ **Save the state_dict, not the model** — `torch.save(model.state_dict(), 'weights.pth')`

---

### Quick Reference Cheat Sheet

```
INSTALLATION:
  pip install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu121

TENSOR CREATION:
  torch.tensor([1,2,3])          torch.zeros(3,4)      torch.ones(3,4)
  torch.randn(3,4)               torch.arange(0,10,2)  torch.linspace(0,1,5)
  torch.randint(0, 10, (3,4))

TENSOR OPS:
  a @ b  OR  torch.mm(a,b)       # Matrix multiply
  a.sum(dim=0)  a.mean()         # Reductions
  a.reshape(2,6)  a.view(-1,4)   # Reshape
  a.permute(2,0,1)               # Reorder dims
  torch.cat([a,b], dim=0)        # Concatenate
  torch.stack([a,b], dim=0)      # Stack (new dim)

DEVICE:
  device = torch.device('cuda' if torch.cuda.is_available() else 'cpu')
  tensor = tensor.to(device)
  tensor = tensor.cpu().numpy()

AUTOGRAD:
  x = torch.tensor(3.0, requires_grad=True)
  y = x**2; y.backward(); x.grad     # dy/dx
  with torch.no_grad(): ...           # No graph
  x.detach()                          # Remove from graph

MODEL DEFINITION:
  class Net(nn.Module):
      def __init__(self):
          super().__init__()
          self.fc = nn.Linear(10, 5)
      def forward(self, x):
          return self.fc(x)

LOSS FUNCTIONS:
  nn.CrossEntropyLoss()   # Multi-class (includes softmax)
  nn.BCEWithLogitsLoss()  # Binary (includes sigmoid)
  nn.MSELoss()            # Regression
  nn.L1Loss()             # MAE

OPTIMIZERS:
  torch.optim.Adam(model.parameters(), lr=1e-3)
  torch.optim.AdamW(model.parameters(), lr=1e-3, weight_decay=1e-4)
  torch.optim.SGD(model.parameters(), lr=0.01, momentum=0.9)

TRAINING STEP:
  model.train()
  optimizer.zero_grad()
  output = model(x)
  loss = criterion(output, y)
  loss.backward()
  torch.nn.utils.clip_grad_norm_(model.parameters(), 1.0)
  optimizer.step()

EVALUATION:
  model.eval()
  with torch.no_grad():
      output = model(x)

SAVE / LOAD:
  torch.save(model.state_dict(), 'model.pth')
  model.load_state_dict(torch.load('model.pth', map_location='cpu'))

KEY LAYERS:
  nn.Linear(in, out)                   # Fully connected
  nn.Conv2d(in_ch, out_ch, 3, padding=1) # Conv layer
  nn.BatchNorm2d(num_features)         # Batch normalization
  nn.Dropout(p=0.5)                    # Dropout regularization
  nn.LSTM(input_sz, hidden_sz, batch_first=True)  # LSTM
  nn.Embedding(vocab_size, embed_dim)  # Token embeddings
  nn.MultiheadAttention(d_model, nhead) # Attention
```

---

### What's Next?

After mastering PyTorch, consider exploring:

- 📘 **HuggingFace Transformers** — Fine-tune BERT, GPT-2, LLaMA, Whisper, CLIP with 3 lines of code
- 📘 **PyTorch Lightning** — Structured training framework; eliminates boilerplate, adds distributed/mixed precision automatically
- 📘 **Diffusion Models** — Understand and implement Stable Diffusion, DDPM from scratch in PyTorch
- 📘 **Reinforcement Learning with PyTorch** — Build game-playing agents (DQN, PPO) using `gymnasium`
- 📘 **ONNX + TensorRT** — Export PyTorch models and deploy at maximum speed on NVIDIA hardware
- 📘 **torch.fx & torch.compile internals** — Understand model compilation, graph manipulation, and custom backends

---

> 💬 *"PyTorch feels like a natural extension of Python because it was designed to get out of your way — to let you think about your model, not the framework. That's what makes it the language of AI research."*
> — Andrej Karpathy

---

*Guide generated with the MD Masterpiece Generator skill.*
*Topic: PyTorch | Version: 1.0 | Author: Deb Barman*
