# Key-Geo-Elements Dataset

This is the official dataset repository for the paper: **"Target-Oriented Formulation for Extracting Key Geospatial Elements under Extreme Class Imbalance"**.

## 📖 Introduction
Remote sensing semantic segmentation often struggles with severe pixel-level class imbalance. To address this, we construct a large-scale remote sensing dataset containing **10,482 high-resolution image tiles**. This dataset exhibits a severe long-tailed distribution, designed to benchmark semantic segmentation models under extreme class imbalance using a target-oriented formulation.

## 📊 Dataset Characteristics
* **Total Images:** 10,482 tiles
* **Spatial Resolution:** $256 \times 256$ pixels
* **Image Format:** 3-channel RGB uint8 JPG
* **Mask Format:** Single-channel uint8 PNG
* **Categories:** 14 semantic categories (including background)

### Pre-processing Information
To mitigate illumination variations, all input images should be normalized prior to training using the following calculated dataset statistics:
* **Mean:** 115.65, 117.62, 106.01
* **Standard Deviation:** 56.83, 53.46, 56.07

## 🎯 Key Target Categories
While the dataset contains 14 classes, our study primarily focuses on four key geospatial elements formulated as one-vs-rest binary segmentation tasks. The extreme class imbalance is demonstrated by the pixel ratios:

| ID | Category Name | RGB Color | Pixel Ratio (%) |
| :--- | :--- | :--- | :--- |
| 1 | **Building** | (255, 60, 60) | 36.21% |
| 2 | **Cultivated Land** | (255, 207, 207) | 32.34% |
| 9 | **Water** | (255, 175, 175) | 5.61% |
| 13 | **Nursery** | (255, 142, 142) | 0.72% |

*(Note: The pixel ratio between Buildings and Nurseries exceeds 50:1, highlighting the severe long-tailed distribution.)*

## 📁 Directory Structure
Please organize the downloaded data as follows:
```text
Key-Geo-Elements/
├── images/
│   ├── image_00001.jpg
│   ├── image_00002.jpg
│   └── ...
└── masks/
    ├── mask_00001.png
    ├── mask_00002.png
    └── ...
