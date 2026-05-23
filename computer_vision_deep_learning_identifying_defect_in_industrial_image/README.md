# 🖼️ Computer Vision for Industrial Defect Detection in Offset Printing

## 🚀 Overview

This project explores the application of Computer Vision (CV) and Deep Learning techniques for automated defect detection in industrial offset printing and packaging production.

The goal is to investigate how convolutional neural networks (CNNs) and transfer learning methods can help reduce production defects, improve quality control, and minimize operational waste in industrial printing environments.

The project compares multiple deep learning image classification approaches, including:
- Custom CNN
- ResNet
- EfficientNetB0 with transfer learning
- YOLO

The study evaluates how different architectures perform in detecting manufacturing defects under real-world industrial constraints.

---

# 💼 Business Problem

In offset printing and packaging production, quality inspection is traditionally performed manually by human operators. This process can be:
- labor intensive
- inconsistent
- error-prone
- difficult to scale

Printing defects such as:
- smearing
- scratches
- blur
- misalignment
- surface inconsistencies

can lead to:
- product waste
- rework costs
- customer dissatisfaction
- operational inefficiency

This project investigates whether Computer Vision models can automate defect detection and improve industrial quality control processes.

---

# 🎯 Objective

The objectives of this project are:
- Build image classification models for defect detection
- Compare traditional CNN vs transfer learning approaches
- Evaluate industrial applicability of modern Computer Vision methods
- Analyze strengths and weaknesses of different architectures
- Explore practical deployment considerations in industrial environments

---

# 📦 Dataset

### Source

Casting Product Image Data for Quality Inspection (Kaggle)

Dataset Link:  
https://www.kaggle.com/datasets/ravirajsinh45/real-life-industrial-dataset-of-casting-product

---

## Dataset Description

The dataset contains industrial product images labeled into:
- `def_front` → defective products
- `ok_front` → non-defective products

The dataset was used as a proxy industrial quality inspection dataset relevant to offset printing and packaging inspection scenarios.

---

# 🧹 Data Preparation

Preprocessing steps included:
- Image resizing
- Pixel normalization
- Train / validation / test split
- Data augmentation
- Histogram equalization experiments
- Noise and illumination analysis

The project also explored how lighting conditions and reflections impact Computer Vision model performance in industrial environments.

---

# 🧠 Methodology

The project compares multiple Computer Vision architectures:

| Model | Type |
|---|---|
| Custom CNN | Baseline convolutional model |
| ResNet | Residual deep learning architecture |
| EfficientNetB0 | Transfer learning architecture |

The workflow includes:
1. Image preprocessing
2. Data augmentation
3. CNN model training
4. Transfer learning experiments
5. Model evaluation
6. Error analysis

---

# ⚙️ Tools & Technologies

- Python
- TensorFlow / Keras
- OpenCV
- scikit-learn
- NumPy / pandas
- Matplotlib / Seaborn

---

# 📊 Evaluation Metrics

The models were evaluated using:
- Accuracy
- Precision
- Recall
- F1-score
- Confusion Matrix
- ROC / AUC
- Validation loss curves

Special attention was given to:
- defect-class precision
- defect-class recall
- industrial false-negative risk

---

# 📈 Key Findings

## 1. Transfer learning significantly improves performance

Transfer learning architectures such as EfficientNetB0 and ResNet outperformed the baseline CNN model by learning stronger image representations from pretrained large-scale datasets.

---

## 2. ResNet produced more balanced classification behavior

ResNet showed more stable and balanced confusion matrix performance between defect and non-defect classes, making it more suitable for industrial inspection tasks where minimizing false negatives is critical.

---

## 3. Industrial lighting strongly affects model performance

The project observed that:
- reflections
- inconsistent illumination
- saturated regions

can significantly impact classification accuracy.

This highlights the importance of controlled lighting and preprocessing in industrial Computer Vision systems.

---

## 4. Histogram equalization can improve visual consistency

Experiments with histogram equalization demonstrated that image preprocessing may help reduce illumination variation and improve feature visibility in industrial inspection tasks.

---

# 🔍 Industrial Relevance

This project demonstrates how Computer Vision systems can support:
- automated quality inspection
- manufacturing defect detection
- waste reduction
- operational efficiency
- production scalability

The approach is particularly relevant for:
- offset printing
- plastic packaging
- industrial manufacturing
- production-line inspection systems

---

# ⚠️ Limitations

- Dataset is not directly from offset printing production
- Limited real-world production variability
- Industrial deployment requires:
  - real-time inference
  - stable lighting conditions
  - hardware integration
  - additional defect categories

The project focuses primarily on proof-of-concept model evaluation.

---

# 🚀 Future Improvements

Potential future improvements include:
- Object detection models (YOLO)
- Real-time production-line deployment
- More diverse industrial datasets
- Segmentation-based defect localization
- Edge deployment optimization
- Vision Transformer (ViT) architectures

---

# 💡 Business Impact

Automated Computer Vision inspection systems can potentially:
- reduce manual inspection costs
- improve consistency
- reduce production waste
- improve manufacturing scalability
- detect subtle defects earlier in production

The project demonstrates how AI and Computer Vision can support Industry 4.0 manufacturing transformation.

---

# 📂 Project Structure

```text
04_cv-industrial-defect-detection/
├── README.md
├── CSCI_E_25_Graduate Project Report.ipynb
├── project_report.pdf
├── confusion_matrix.png
├── roc_curve.png
├── training_curve.png
├── sample_predictions.png
