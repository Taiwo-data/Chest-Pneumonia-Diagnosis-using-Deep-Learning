# Chest-Pneumonia-Diagnosis-using-Deep-Learning
This project implements a custom CNN and transfer learning models (VGG16, ResNet50, DenseNet121, MobileNetV2) to detect pneumonia from chest X-rays. VGG16 achieved 90% accuracy, outperforming the baseline CNN. Preprocessing, augmentation, and Grad-CAM visualizations enhance model performance and interpretability.

This repository contains the implementation of a **custom CNN (CNN2023)** and multiple **transfer learning models** (VGG16, ResNet50, DenseNet121, and MobileNetV2) for the detection of **pneumonia from chest X-ray images**. The work is based on a dissertation project at *Middlesex University, London*.  

---

## Motivation
- Pneumonia causes over **700,000 child deaths annually** and affects nearly **7% of the global population** (WHO, 2023).  
- Chest X-rays are essential for diagnosis but remain challenging to interpret.  
- Deep learning can assist radiologists in providing **faster, more accurate, and consistent diagnoses**.  

---

## Models Implemented

| Model                   | Accuracy (%) |
|--------------------------|--------------|
| CNN2023 (baseline)       | 70.93        |
| CNN2023 + Class Weights  | 84.31        |
| AKVGG16                  | 90.07        |
| AKDenseNet121            | 88.20        |
| AKResNet50               | 86.33        |
| AKMobileNetV2            | 84.74        |

 **Insight:** Transfer learning significantly outperformed the baseline CNN due to robust pre-trained feature extraction.  
## Model Interpretation & Comparative Analysis
1. Baseline CNN (CNN2023)

Performance: 70.93% accuracy.

Interpretation: The custom CNN provides a strong starting point but struggles with class imbalance and feature generalization. Its relatively lower accuracy reflects the challenges of training from scratch on a moderate dataset (~3,475 X-rays).

Improvement: Incorporating class weights improved accuracy to 84.31%, demonstrating that handling imbalanced classes (Normal vs. Pneumonia) is critical for real-world datasets.

2. Transfer Learning Models

Transfer learning leverages pre-trained feature extractors trained on large datasets (ImageNet) to detect pneumonia effectively, even with limited X-ray data.

Model	Accuracy	Interpretation
AKVGG16	90.07%	Outperformed all other models; deep convolutional layers effectively captured relevant pulmonary patterns. Grad-CAM visualization confirms attention to opacity regions.
AKDenseNet121	88.20%	Dense connectivity improved feature reuse and gradient flow, yielding high performance. Slightly lower than VGG16 possibly due to overfitting on small dataset.
AKResNet50	86.33%	Residual connections allowed deeper network training but showed moderate performance, indicating dataset size limited full potential.
AKMobileNetV2	84.74%	Lightweight architecture performed adequately but less accurate than heavier models, reflecting trade-offs between efficiency and feature richness.

## A virsual representation is giving below
<img width="2379" height="1180" alt="777a5962-82e9-4e0c-8056-1ee20aebb148" src="https://github.com/user-attachments/assets/4b4677c3-c934-426b-831d-0b931e884400" />
Here’s a visual comparison of your models versus past studies.

Blue bars: MY models from this work.

Orange bars: Previous studies for reference.

Insights:

VGG16 from your study (90.07%) is very competitive with larger datasets like Kermany et al. (92.8%).

DenseNet121 and ResNet50 also perform strongly, reinforcing the effectiveness of transfer learning on moderate datasets.

Lightweight models like MobileNetV2 offer decent accuracy with reduced computational cost.
 
---

## Dataset
- **Chest X-ray Dataset (Mendeley)**  
- Classes: `Normal`, `Lung Opacity`, `Viral Pneumonia`  
- Size: ~3,475 images  

Dataset link: [Mendeley Data](https://data.mendeley.com/datasets/rscbjbr9sj/2)  

 Due to licensing restrictions, raw data is **not included** in this repo. Please download directly from Mendeley.  

---

## Preprocessing
- **Resizing:** 224Ã—224 pixels  
- **Normalization:** Model-specific scaling  
- **Noise reduction:** Gaussian filter  
- **Contrast Enhancement:** CLAHE (Contrast Limited Adaptive Histogram Equalization)  
- **Augmentation:** Random rotation, flipping, zooming  

Example (Before & After CLAHE):  
![CLAHE Example](results/clahe_example.png)  

---

## Results & Analysis
- The baseline CNN2023 achieved **70.93%** accuracy.  
- Applying **class weights** improved CNN2023 to **84.31%**, addressing class imbalance.  
- Transfer learning models (VGG16, ResNet50, DenseNet121, MobileNetV2) all surpassed the custom CNN.  
- **VGG16** achieved the best accuracy (**90.07%**).  

### Example Grad-CAM visualization:
![Grad-CAM Example](results/gradcam_examples/vgg16_gradcam.png)  

---

## Future Work
- Train on **larger datasets** such as NIH and CheXpert.  
- Apply **cross-validation** to improve robustness.  
- Extend to **CT scan analysis** for richer diagnostic capability.  

---

##  Tech Stack
- Python 3.10  
- TensorFlow / Keras  
- OpenCV  
- NumPy, Pandas, Matplotlib  
- Scikit-learn  

---

## Citation
If you use this repository, please cite:

```
Akinwekomi, T.O. (2025). Chest Pneumonia Diagnosis using Deep Learning. Department of Computer Science, Middlesex University, London.
```

---

## Contact
**Taiwo Oluwapelumi Akinwekomi**  
Department of Computer Science, Middlesex University, London  
 [Your Email / LinkedIn / GitHub Profile Link]  

