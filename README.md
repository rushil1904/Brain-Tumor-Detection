# Brain Tumor Detection in MRI Images

## Overview
This project implements an image processing pipeline for detecting brain tumors in MRI images. The pipeline involves various techniques for noise reduction, contrast enhancement, image segmentation, edge detection, and feature extraction. The goal is to enhance the visibility of potential tumor regions and assist in early detection, which is crucial for improving patient outcomes.

## Table of Contents
- [Introduction](#introduction)
- [Methodology](#methodology)
  - [Dataset](#dataset)
  - [Image Preprocessing](#image-preprocessing)
  - [Feature Extraction](#feature-extraction)
  - [Classification](#classification)
- [Results](#results)
- [Conclusion](#conclusion)
- [References](#references)

## Introduction
Brain tumors are a significant health concern, and early detection is critical for improving treatment outcomes. MRI is the primary imaging technique used in brain tumor diagnosis due to its superior contrast resolution. However, interpreting MRI scans is often challenging due to factors like noise, low contrast, and variability in tumor appearance.

This project aims to develop a multi-step image processing pipeline to enhance MRI images and aid in brain tumor detection. The key objectives include:
1. Improving contrast and visibility of potential tumor regions.
2. Segmenting regions of interest (ROI) that may indicate the presence of tumors.
3. Extracting relevant features from processed images to assist in tumor detection.

## Methodology
### Dataset
We used the [Brain Tumor MRI Dataset](https://www.kaggle.com/datasets/ahmedhamada0/brain-tumor-detection/data) from Kaggle, which contains 3060 brain MRI images categorized into TEST, TRAIN, and VAL folders. The images are in JPG format and vary in size and quality, simulating a realistic clinical scenario.

### Image Preprocessing
The image processing pipeline includes the following steps:
1. **Image Acquisition and Normalization:** MRI images are loaded in grayscale and normalized to the range [0, 1].
2. **Noise Reduction:** A Gaussian filter is applied to reduce noise while preserving important edge information.
3. **Contrast Enhancement:** Histogram equalization is used to improve contrast.
4. **Image Segmentation:** Otsu's thresholding is used to segment the images, followed by morphological operations to refine the segmentation.

### Feature Extraction
Several features are extracted from the processed images:
- **Shape Features:** Area, perimeter, compactness, eccentricity, solidity.
- **Texture Features:** Contrast, correlation, energy, homogeneity (using Gray Level Co-occurrence Matrix).
- **Intensity Features:** Mean and standard deviation of intensity in the segmented region.

### Classification
A rule-based classification system is implemented to detect tumors based on the extracted features. Tumors are identified if certain criteria related to area, compactness, contrast, and intensity are met.

## Results
The processing pipeline effectively enhances MRI images, making tumor regions more visible. The extracted features allow for reliable differentiation between tumor and non-tumor images. The average processing time per image was approximately 1.23 seconds, indicating potential for real-time application.

Visual analysis of the images processed through the pipeline showed clear improvements in contrast and segmentation accuracy.

## Conclusion
This project demonstrates that a well-designed image processing pipeline can significantly enhance MRI images for brain tumor detection. The combination of noise reduction, contrast enhancement, segmentation, and feature extraction techniques proved effective in isolating tumor regions and extracting relevant features.

Future work could involve integrating machine learning techniques for more robust segmentation and classification, as well as validating the approach on larger and more diverse datasets.

## References
1. Maini, R., & Aggarwal, H. (2010). A Comprehensive Review of Image Enhancement Techniques. *arXiv preprint arXiv:1003.4053*.
2. Bhardwaj, N., Kaur, G., & Singh, P. K. (2018). A Systematic Review on Image Enhancement Techniques. In *Sensors and Image Processing* (pp. 227-235). Springer.
3. Kimori, Y. (2013). Morphological image processing for quantitative shape analysis of biomedical structures: Effective contrast enhancement. *Journal of Synchrotron Radiation*, 20(6), 848-853.
4. Anantharajan, S., Gunasekaran, S., & Subramanian, T. (2024). MRI brain tumor detection using deep learning and machine learning approaches. *Measurement: Sensors*, 31, 101026.

## Appendix
- **Dataset:** [Kaggle Brain Tumor MRI Dataset](https://www.kaggle.com/datasets/ahmedhamada0/brain-tumor-detection/data)
- **Code Repository:** [GitHub Repository](https://github.com/rushil1904/Brain-Tumor-Detection)
- **Python Notebook:** The complete code is available in the repository in the `.ipynb` format.
