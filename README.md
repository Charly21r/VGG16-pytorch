# 🧠 VGG16 Model (PyTorch)

This repository contains a custom implementation of the **VGG16** model in PyTorch, designed for image classification tasks. The model closely follows the classic architecture proposed by *Simonyan & Zisserman (2014)*, with modifications to support a configurable number of output classes.

---

## 📐 Model Architecture

The model is composed of 6 main blocks:

### 1. **First Block**
- 2 convolutional layers: `3 → 64 → 64` channels, with 3x3 kernels and padding of 1
- 1 MaxPooling layer: `kernel=2x2`, `stride=2`

### 2. **Second Block**
- 2 convolutional layers: `64 → 128 → 128`
- 1 MaxPooling layer

### 3. **Third Block**
- 3 convolutional layers: `128 → 256 → 256 → 256`
- 1 MaxPooling layer

### 4. **Fourth Block**
- 3 convolutional layers: `256 → 512 → 512 → 512`
- 1 MaxPooling layer

### 5. **Fifth Block**
- 3 convolutional layers: `512 → 512 → 512 → 512`
- 1 MaxPooling layer

### 6. **Sixth Block (Fully Connected)**
- Tensor flattening: `512 x 7 x 7`
- 2 fully connected layers with 4096 units each + ReLU + Dropout
- Output layer with linear activation (adjustable to `num_classes`)
