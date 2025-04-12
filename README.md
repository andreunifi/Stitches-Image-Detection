# Stitches - v2 Dataset 

## 📖 Overview

The **Stitches Dataset** is a publicly available image dataset designed for detecting and analyzing stitches in grayscale images. It contains **501 images** annotated in **COCO format**, making it ideal for computer vision tasks like object detection and segmentation. The dataset is divided into three subsets: **train**, **test**, and **valid** for efficient model training, evaluation, and validation.

This dataset was conceived as a way to train a multimodal machine learning model to be able to identify and provide bounding boxes for a wide variety of stitches, obtained after medical surgeries. The model would have also been trained on both the patient medical data and on a diverse and heterogenous range of medical articles and journals to provide more specific analysis of the patient.
---

## Key Features

- **Total Images**: 501 grayscale images.
- **Annotations**: Provided in the standard **COCO format**.
- **Splits**:
  - **Train**: 70% of the dataset.
  - **Validation**: 20% of the dataset.
  - **Test**: 10% of the dataset.
- **Image Dimensions**: All images are resized to **640x640 pixels** (stretched).
- **Color Format**: Converted to grayscale using CRT phosphor simulation.

---

## Dataset Preparation

### **Preprocessing Steps**

1. **Auto-Orientation**  
   - Stripped EXIF orientation metadata and auto-corrected image orientation.

2. **Resizing**  
   - Resized all images to **640x640 pixels** using a stretching method for uniformity.

3. **Grayscale Conversion**  
   - Converted images to grayscale with CRT phosphor simulation for consistency.

4. **Auto-Contrast**  
   - Enhanced contrast using **histogram equalization**.

### **Data Augmentation**

To enhance diversity, three augmented versions of each image were generated using the following techniques:

- **Horizontal Flip**  
  - Applied with a 50% probability.

- **Rotation**  
  - Randomly applied with equal probability of:
    - No rotation.
    - 90° clockwise.
    - 90° counter-clockwise.

- **Random Cropping**  
  - Cropped between **0% and 20%** of image dimensions.

- **Gaussian Blur**  
  - Applied random Gaussian blur between **0 to 2.5 pixels**.

---

## 📂 Dataset Structure

The dataset is organized into the following structure:

```plaintext
Stitches-v2/
├── train/
│   ├── images/
│   └── annotations.json
├── valid/
│   ├── images/
│   └── annotations.json
├── test/
│   ├── images/
│   └── annotations.json
└── README.md
