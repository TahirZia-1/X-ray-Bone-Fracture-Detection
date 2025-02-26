# Bone Fracture Classification with CNN

This repository implements a Convolutional Neural Network (CNN) for classifying X-ray images as either "fractured" or "not fractured." Built using TensorFlow/Keras, the model is trained on a dataset of bone X-ray images and deployed via a Gradio interface for easy user interaction. The project demonstrates binary classification with data augmentation, model training, and real-time inference.

## Overview

The goal is to distinguish between fractured and non-fractured bone X-rays using a CNN. The dataset contains 8,863 training images and 600 validation images, split into two classes. The trained model achieves high accuracy and is accessible through a simple web interface powered by Gradio.

### Key Features
- **Dataset**: 8,863 training and 600 validation X-ray images (fractured vs. not fractured).
- **Model**: CNN with convolutional, pooling, and dense layers.
- **Data Augmentation**: Shear, zoom, and horizontal flips for robust training.
- **Deployment**: Gradio interface for uploading and classifying X-ray images.
- **Monitoring**: TensorBoard callbacks for training visualization.

## Implementation

### Dataset
- **Source**: [Mega.nz Link](https://mega.nz/file/zcdywLhI#fck4ufXy_o_Uiu0vGqh-cZiKHw5Xe_n4M2qWUWSheAI)
- **Structure**: 
  - `archive (6)/train`: 8,863 images (2 classes)
  - `archive (6)/val`: 600 images (2 classes)
- **Preprocessing**: Images resized to 150x150, normalized to [0,1], and augmented.

### Model Architecture
- **Input**: 150x150x3 (RGB images)
- **Layers**:
  - Conv2D: 32 filters, 3x3 kernel, ReLU activation
  - MaxPooling2D: 2x2 pool size
  - Flatten
  - Dense: 128 units, ReLU activation
  - Dense: 1 unit, sigmoid activation
- **Parameters**: ~22.43M trainable
- **Optimizer**: Adam
- **Loss**: Binary Crossentropy
- **Metrics**: Accuracy

### Training
- **Batch Size**: 32
- **Epochs**: 15
- **Results**:
  - Epoch 1: 57.29% accuracy, 1.1869 loss
  - Epoch 15: 91.80% accuracy, 0.2111 loss
- **Callbacks**: TensorBoard for logging

### Deployment
- **Gradio Interface**: Upload an X-ray image, receive "fractured" or "not fractured" prediction.
- **Model File**: Saved as `x_ray.keras`

## Installation

### Prerequisites
- Python 3.x
- Required libraries:
  - TensorFlow (`pip install tensorflow`)
  - NumPy (`pip install numpy`)
  - Gradio (`pip install gradio`)
  - Keras (`pip install keras`)

### Setup
1. **Clone the Repository**:
   ```bash
   git clone https://github.com/TahirZia-1/bone-fracture-classification.git
   cd bone-fracture-classification
