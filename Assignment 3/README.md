# Computer Vision - Assignment 3 

**Instructor**: Dr. Ahmad Mahmoudi Aznaveh 

**Course**: Computer Vision - spring 2024  
---

## Overview
This homework covers advanced topics in computer vision, focusing on object detection (Fast/Faster RCNN), optical flow estimation, and Vision Transformers (ViTs). It includes both theoretical and practical coding tasks that will enhance your understanding of cutting-edge methods for motion estimation, object detection, speed prediction, and image classification.

### Table of Contents
1. **Theory Questions**
   - Object Detection: Fast RCNN & Faster RCNN
   - Optical Flow Estimation
   - Vision Transformers
2. **Implementation Part**
   - Object Detection of Cats
   - Lucas-Kanade Optical Flow
   - Speed Prediction of Moving Vehicles
   - Image Classification Using Vision Transformers
3. **Setup Instructions**
4. **Requirements**

---

## 1. Theory Questions

### Question 1: Object Detection - Fast RCNN & Faster RCNN
- **Fast RCNN**: Enhanced version of RCNN with better speed and accuracy, using a Region Proposal Network (RPN) for region proposals.
- **Faster RCNN**: Integrates RPN into the pipeline, eliminating the need for an external region proposal algorithm.
- **Loss Function Components**:
  - RPN Classification Loss
  - RPN Regression Loss
  - Fast RCNN Classification Loss
  - Fast RCNN Regression Loss

### Question 2: Optical Flow Estimation
- **Comparison of Lucas & Kanade vs. Horn & Schunck**: Discusses two popular optical flow estimation algorithms.
- **Regularization Parameter (α)** in Horn & Schunck: Discuss its role in smoothing the flow field.
- **Aperture Problem**:
  - **Definition**: Motion observed through a small aperture is ambiguous, especially along edges.
  - **Impact**: Local methods struggle with complex motion; global methods and multi-scale approaches help address this limitation.

### Question 3: Optical Flow Estimation and Vision Transformers
- **FlowNet Variants**:
  - **FlowNetS**: Spatial architecture.
  - **FlowNetC**: Correlation-based model for better flow estimation.
  - Both models use "upconvolutional" layers for refinement and high-resolution optical flow predictions.

### Question 4: Vision Transformers (ViTs)
- **Key Concepts**:
  - **Self-Attention Mechanism**: Inputs are divided into patches with position embeddings. Queries, Keys, and Values are calculated, and self-attention is applied to weigh different parts of the image.
  - **ViT Implementation**: Process images using self-attention in a transformer encoder, where patches of the image are processed independently and spatial relationships are maintained using positional embeddings.

---

## 2. Implementation Part

### Question 1: Object Detection of Cats
- **Goal**: Build a model to detect cats in images using a feature pyramid network (FPN) and a ResNet-50 backbone.
- **Steps**:
  - Preprocess data by resizing images to 416x416 pixels and normalizing pixel values and bounding boxes.
  - Build an FPN with two branches for bounding box regression and class prediction.
  - Assemble the model and train it on the dataset for detecting cats.

### Question 2: Lucas-Kanade Optical Flow
- **Goal**: Implement the **Lucas-Kanade method** to estimate optical flow between consecutive frames.
- **Steps**:
  - Assume brightness constancy and small motion between frames.
  - Implement the algorithm without using pre-built libraries.
  - Calculate the motion field representing object movement across frames.

### Question 3: Speed Prediction of a Moving Vehicle
- **Goal**: Predict the speed of a moving vehicle using CNNs and optical flow.
- **Steps**:
  - Extract motion from consecutive video frames using a flow matrix.
  - Encode the direction and magnitude of pixel changes using HSV color space.
  - Train a custom CNN architecture in PyTorch to predict the vehicle’s speed and report accuracy metrics.

### Question 4: Image Classification Using Vision Transformers
- **Goal**: Use Vision Transformers (ViT) to classify images in the CIFAR-10 dataset.
- **Steps**:
  - Preprocess CIFAR-10 dataset by resizing images to 224x224 pixels and normalizing them.
  - Implement a ViT model using PyTorch and train it on the dataset.
  - Compare the performance of the ViT with baseline models like ResNet and VGG.
  - Recommended to run this task in **Google Colab** due to high computational requirements.

---

## 3. Setup Instructions
1. **Clone the Repository**:  
   ```bash
   git clone <repository_url>
   cd <repository_directory>
   ```

2. **Install Required Libraries**:  
   Make sure Python 3.x and PyTorch are installed. You can install the required dependencies using the following command:
   ```bash
   pip install -r requirements.txt
   ```

3. **Run on Google Colab (Optional for ViTs)**:
   - For **Question 4 (Vision Transformers)**, run the notebook in Google Colab to leverage the GPU and avoid local computational issues.

---

## 4. Requirements
- **Python** 3.x
- **Libraries**:  
  - `PyTorch`
  - `NumPy`
  - `OpenCV`
  - `Matplotlib`
  - `Scikit-learn`
  - `Torchvision`
- **Google Colab** (for Vision Transformer task, optional)
