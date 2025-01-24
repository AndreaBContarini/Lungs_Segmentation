# 2D CT Scan Segmentation for COVID-19 Lung Analysis

## Overview
This project implements a 2D segmentation algorithm for CT scan images of lungs affected by COVID-19. The goal is to automatically identify and segment different types of lung tissue (normal, glass opacity, consolidation) using a U-Net deep learning model. The performance of the model was evaluated using Intersection over Union (IoU), achieving an average IoU of **0.76**.

## Features
- **Dataset**: 750 grayscale CT scan images with corresponding ground truth masks, augmented to 3000 images.
- **Model Architecture**: U-Net, tailored for biomedical image segmentation.
- **Evaluation Metrics**: IoU for segmentation accuracy.
- **Hyperparameters**:
  - Loss function: CrossEntropyLoss
  - Optimizer: Adam with learning rate `1x10^-3`
  - Batch size: 5
  - Epochs: 35

## Dataset
The dataset is based on publicly available CT scans of lungs affected by COVID-19:
- Size: 750 images (512x512) with pixel-wise labeled masks.
- Labels:
  - Background: `0`
  - Normal lung tissue: `1`
  - Glass opacity: `2`
  - Consolidation: `3`

The dataset was augmented using:
- Vertical and horizontal flips
- Rotation by 45°

## Methodology
1. **Preprocessing**:
   - Images normalized and converted to grayscale.
   - Data augmentation to prevent overfitting.
2. **Model Training**:
   - Architecture: U-Net with encoder-decoder and skip connections.
   - Loss convergence observed after ~30 epochs.
3. **Evaluation**:
   - IoU score of **0.76**.
   - Training and validation loss showed consistent convergence.

## Results
The model successfully segmented lung tissues with an IoU of **76%** and a test loss of **19%**. Examples of input images, ground truth masks, and predicted masks are included in the repository for qualitative analysis.

## Limitations and Future Work
- Limited computational resources (no Google Colab Pro) restricted the depth of the model and number of epochs.
- Future improvements could include:
  - Adding more convolutional layers to the U-Net.
  - Increasing the training duration for better convergence.

## Requirements
- Python 3.x
- PyTorch
- NumPy
- OpenCV
- Matplotlib

## Usage
1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/ct-scan-segmentation.git
