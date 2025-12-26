![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![PyTorch](https://img.shields.io/badge/PyTorch-Deep%20Learning-red)
![CUDA](https://img.shields.io/badge/CUDA-GPU%20Accelerated-green)
![Computer Vision](https://img.shields.io/badge/Domain-Computer%20Vision-purple)
![Segmentation](https://img.shields.io/badge/Task-Semantic%20Segmentation-orange)

# Road Extraction from Satellite Images using Deep Learning

## Project Overview
This project focuses on **automatic road extraction from satellite images** using **deep learning–based semantic segmentation** techniques.  
The objective is to accurately classify each pixel as **road** or **background**, enabling applications such as **urban planning, navigation systems, and GIS mapping**.

---

## Models Implemented
The following models were implemented, trained, and compared:

- U-Net Lite  
- U-Net Full  
- U-Net++  
- DeepLabV3+ (ResNet-50 backbone)  
- HRNet-Small  
- SegFormer-B0  
- **U-Net-ResNet34 (Best Performing Model)**  

---

## Dataset Structure

- **Training set** contains both images and ground-truth masks.
- **Validation and Test sets** contain only images and are used for prediction and qualitative evaluation.

---

## Preprocessing & Augmentation
- Images resized to **256 × 256**
- Pixel normalization
- Binary mask generation
- Data augmentation:
  - Horizontal and vertical flips
  - Brightness and contrast adjustment
  - Rotation and scaling

---

## Training Configuration
- **Image Size:** 256 × 256  
- **Batch Size:** 4  
- **Epochs:** 15–20  
- **Optimizer:** Adam  
- **Loss Function:**  
  - Binary Cross-Entropy (BCE)  
  - Dice Loss  
  - Combined Loss = 0.5 × BCE + 0.5 × Dice  

- **Framework:** PyTorch  
- **Hardware:** GPU (CUDA-enabled)

---

## Evaluation Metrics
Due to class imbalance in segmentation tasks, the following metrics were used:

- **Intersection over Union (IoU)** – primary metric  
- **Dice Score** – overlap-based metric  

> Pixel accuracy was not used as it can be misleading in imbalanced datasets.

---

## Prediction & Visualization
- Trained models generate binary road masks
- Predictions are overlaid on satellite images for visualization
- Test predictions are saved automatically to disk

---

## Applications
- Road network extraction
- Smart city planning
- Navigation systems
- Disaster management
- Remote sensing analysis

