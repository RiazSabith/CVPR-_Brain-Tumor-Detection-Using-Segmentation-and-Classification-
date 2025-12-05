# Brain Tumor Analysis Project

This project implements a comprehensive pipeline for Brain Tumor Analysis, utilizing Deep Learning techniques for Segmentation, Classification, and Synthetic Image Generation.

## 📂 Dataset Information
The dataset comprises **3064 T1-weighted contrast-enhanced MRI images** collected from 233 patients. It includes three specific types of brain tumors:
* **Meningioma** (708 slices)
* **Glioma** (1426 slices)
* **Pituitary Tumor** (930 slices)

## 🏗️ Project Structure
* `Brain-Tumor Segmentation (1).ipynb`: Implementation of the segmentation model (U-Net based).
* `Brain_Tumor_classification.ipynb`: Implementation of classification models, featuring a custom 23-layer architecture and comparative Transfer Learning models.
* `Brain_Tumor_Stylegan2.ipynb`: Implementation of StyleGAN2 for generating synthetic MRI images.

## 📊 Results

### 1. Segmentation
The segmentation model achieves high precision in isolating tumor regions.

**Performance Metrics:**
* **Test Loss:** 0.1360
* **Test Accuracy:** 99.63%
* **Dice Coefficient:** 0.8945
* **IoU Score:** 0.8106
* **Sensitivity (Recall):** 85.73%
* **Specificity:** 99.89%
* **Precision:** 93.46%

**Confusion Matrix (Pixel-level):**
| | Predicted Background | Predicted Tumor |
|---|---|---|
| **Actual Background** | 59,126,771 (TN) | 66,040 (FP) |
| **Actual Tumor** | 156,965 (FN) | 943,344 (TP) |

### 2. Classification
The custom 23-layer model demonstrates superior performance compared to standard Transfer Learning architectures.

**Custom 23-Layer Model Performance:**
* **Overall Accuracy:** 96.56%

**Detailed Class Report:**
*Note: Class labels are inferred from dataset distribution (Class 0: Meningioma, Class 1: Glioma, Class 2: Pituitary).*

| Class | Label | Precision | Recall | F1-Score | Support |
|---|---|---|---|---|---|
| 0 | Meningioma | 0.93 | 0.93 | 0.93 | 141 |
| 1 | Glioma | 0.96 | 0.96 | 0.96 | 277 |
| 2 | Pituitary | 0.99 | 1.00 | 1.00 | 192 |
| **Avg** | | **0.97** | **0.97** | **0.97** | **610** |

**Transfer Learning Comparison:**
| Model | Accuracy |
|---|---|
| **Custom 23-Layer** | **0.9656** |
| EfficientNetB0 | 0.9572 |
| ResNet-50 | 0.9213 |
| VGG16 | 0.8918 |
| DenseNet121 | 0.8443 |
| SqueezeNet | 0.7328 |
| AlexNet | 0.6475 |

### 3. Image Generation (StyleGAN2)
* **FID Score (fid50k_full):** 155.69
    * *Lower FID indicates better image quality and diversity.*
