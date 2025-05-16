# 🧠 VGG16 Model (PyTorch)

Este repositorio contiene una implementación personalizada del modelo **VGG16** en PyTorch, diseñada para tareas de clasificación de imágenes. El modelo sigue de cerca la arquitectura clásica propuesta por *Simonyan & Zisserman (2014)*, con modificaciones para adaptarse a un número de clases configurable.

---

## 📐 Arquitectura del Modelo

El modelo consta de 6 bloques principales:

### 1. **Primer Bloque**
- 2 capas convolucionales: `3 → 64 → 64` canales, con kernels 3x3, padding 1
- 1 capa MaxPooling: `kernel=2x2`, `stride=2`

### 2. **Segundo Bloque**
- 2 capas convolucionales: `64 → 128 → 128`
- 1 capa MaxPooling

### 3. **Tercer Bloque**
- 3 capas convolucionales: `128 → 256 → 256 → 256`
- 1 capa MaxPooling

### 4. **Cuarto Bloque**
- 3 capas convolucionales: `256 → 512 → 512 → 512`
- 1 capa MaxPooling

### 5. **Quinto Bloque**
- 3 capas convolucionales: `512 → 512 → 512 → 512`
- 1 capa MaxPooling

### 6. **Sexto Bloque (Fully Connected)**
- Aplanamiento del tensor `512 x 7 x 7`
- 2 capas densas con 4096 unidades + ReLU + Dropout
- Capa de salida con activación lineal (ajustable a `num_classes`)
