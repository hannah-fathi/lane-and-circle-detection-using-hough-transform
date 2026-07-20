# Lane and Circle Detection using Hough Transform

> **A modular classical computer vision framework for robust lane detection and circular object localization using Hough Transform, multi-stage edge analysis, and OpenCV.**

![Python](https://img.shields.io/badge/Python-3.10+-blue.svg)
![OpenCV](https://img.shields.io/badge/OpenCV-4.x-green.svg)
![NumPy](https://img.shields.io/badge/NumPy-Scientific%20Computing-orange.svg)
![License](https://img.shields.io/badge/License-MIT-yellow.svg)


---

# Overview

This repository presents a research-oriented implementation of the **Hough Transform** for detecting geometric structures in natural images using classical computer vision techniques.

The project focuses on two representative tasks:

* **Lane Detection** for autonomous driving using the **Probabilistic Hough Line Transform**
* **Circular Object Detection and Counting** using the **Hough Circle Transform**

Rather than relying on a straightforward Hough Transform implementation, this framework integrates multiple preprocessing and post-processing stages—including contrast enhancement, edge fusion, region-of-interest extraction, slope filtering, and statistical analysis—to improve robustness under realistic imaging conditions.

Although originally inspired by an advanced Digital Image Processing course, the project has been extensively redesigned into a modular, research-oriented repository emphasizing reproducibility, interpretability, and clean software engineering practices.

---

# Motivation

Reliable geometric feature extraction remains one of the fundamental problems in classical computer vision.

Despite the remarkable success of deep learning, algorithms such as the Hough Transform continue to provide efficient, interpretable, and computationally inexpensive solutions for many real-world applications, including autonomous driving, industrial inspection, medical imaging, and robotics.

The objective of this project is to demonstrate how a carefully designed image processing pipeline can substantially improve the robustness of Hough-based geometric feature detection while maintaining full interpretability.

---

# Key Features

* Modular computer vision pipeline
* Dynamic Region of Interest (ROI) extraction
* Contrast enhancement
* Gaussian and median filtering
* Multi-stage edge detection
* Canny edge detector
* Sobel gradient magnitude
* Otsu adaptive thresholding
* Edge fusion using logical intersection
* Probabilistic Hough Line Transform
* Hough Circle Transform
* Lane line averaging using slope estimation
* Lane polygon visualization
* Duplicate circle suppression
* Statistical analysis of detected line orientations
* Publication-quality visualizations
* Fully implemented in Python using OpenCV

---

# Repository Structure

```text
lane-and-circle-detection-using-hough-transform

│
│
├── data/
│   └── Hough Transform.zip/
│
├── docs/
│   └── Report.pdf
│
│
├── notebooks/
│   └── Lane Detection.ipynb
│
├── results/
│   ├── lane_detection/
│   ├── circle_detection/
│   ├── angle_histogram.png
│   └── lane_detection.gif
│
├── README.md
├── requirements.txt
├── LICENSE
└── CITATION.cff
```

---

# Dataset

## Lane Detection

* Sequential road images
* Google Street View
* Fixed camera viewpoint
* 23 RGB images
* Multiple lane boundaries under consistent perspective

## Circle Detection

* Classical Hough Transform benchmark images
* Two representative images selected for evaluation
* Multiple circular objects with different scales and densities

---

# Methodology

## Part I — Lane Detection Pipeline

```text
Input Image
      │
      ▼
Contrast Enhancement
      │
      ▼
Gaussian Blur
      │
      ▼
Canny Edge Detection
      │
      ▼
Sobel Gradient Magnitude
      │
      ▼
Otsu Thresholding
      │
      ▼
Edge Fusion
(Canny ∩ Sobel)
      │
      ▼
Dynamic ROI Extraction
      │
      ▼
Probabilistic Hough Line Transform
      │
      ▼
Slope Filtering
      │
      ▼
Lane Averaging
      │
      ▼
Lane Polygon Generation
      │
      ▼
Final Lane Detection
```

---

## Part II — Circle Detection Pipeline

```text
Input Image
      │
      ▼
Grayscale Conversion
      │
      ▼
Noise Reduction
      │
      ▼
Hough Circle Transform
      │
      ▼
Duplicate Circle Removal
      │
      ▼
Circle Counting
      │
      ▼
Visualization
```

---

# Implemented Algorithms

## Image Enhancement

* Contrast enhancement
* Gaussian filtering
* Median filtering

## Edge Detection

* Canny Edge Detector
* Sobel Gradient Magnitude
* Otsu Thresholding
* Edge Fusion

## Feature Detection

* Probabilistic Hough Line Transform
* Hough Circle Transform

## Post-processing

* Dynamic ROI extraction
* Lane slope filtering
* Reference line estimation
* Lane averaging
* Circle refinement
* Duplicate suppression

---

# Experimental Results

## Lane Detection

The proposed framework successfully detects the dominant left and right lane boundaries across the complete image sequence.

Pipeline visualization includes:

* Original image
* Canny edge map
* Sobel + Otsu response
* ROI mask
* Combined edge map
* Final detected lanes

<p align="center">
<img src="assets/lane_detection.gif" width="900">
</p>

---

## Statistical Analysis

A statistical analysis of detected line orientations is performed using the angle distribution of Hough line segments.

Reported statistics include:

* Number of detected lines
* Mean angle
* Standard deviation
* Orientation histogram

The results demonstrate stable geometric consistency and reliable lane estimation across the evaluated image sequence.

---

## Circle Detection

The framework accurately detects and counts circular objects using the Hough Circle Transform.

Additional post-processing removes duplicated detections resulting from overlapping circles, improving counting accuracy and visualization quality.

---

# Design Highlights

Compared with a conventional Hough Transform implementation, this project introduces several engineering improvements:

* Dynamic ROI masking
* Contrast enhancement
* Multi-stage edge extraction
* Edge fusion using logical intersection
* Lane slope averaging
* Reference line estimation
* Duplicate circle suppression
* Statistical validation of detected line orientations

---

# Technologies

* Python
* OpenCV
* NumPy
* Matplotlib
* ImageIO

---

# Installation

```bash
git clone https://github.com/hannah-fathi/lane-and-circle-detection-using-hough-transform.git

cd lane-and-circle-detection-using-hough-transform

pip install -r requirements.txt
```

---

# Quick Start

Run the demonstration notebook

```bash
notebooks/demo.ipynb
```

or execute

```bash
python examples/quick_start.py
```

---

# Repository Highlights

* Modular architecture
* Classical computer vision
* Explainable image processing pipeline
* Robust lane extraction
* Circular object localization
* Publication-quality visualizations
* Research-oriented implementation
* Reproducible experiments

---

# Current Limitations

The current implementation assumes:

* Fixed camera viewpoint
* Straight lane markings
* Daylight imaging conditions
* Limited occlusion
* Moderate image noise

---

# Future Work

Future development may include:

* Curved lane detection
* Perspective transformation
* Camera calibration
* Real-time video processing
* Automatic parameter optimization
* Multi-lane tracking
* Deep learning-based lane detection
* Benchmark evaluation on public autonomous driving datasets
* Hybrid classical–deep learning computer vision pipelines

---

# Citation

If you use this repository in your research or educational projects, please consider citing it.

```bibtex
@software{fathi2026lane,
  author  = {Hannah Fathi},
  title   = {Lane and Circle Detection using Hough Transform},
  year    = {2026},
  url     = {https://github.com/hannah-fathi/lane-and-circle-detection-using-hough-transform}
}
```

---

# Acknowledgements

This repository was originally inspired by an advanced Digital Image Processing course at Shiraz University and has been extensively refactored into a modular research-oriented implementation for reproducible computer vision experiments.

---

# Research Areas

* Computer Vision
* Image Processing
* Autonomous Driving
* Classical Computer Vision
* Feature Extraction
* Geometric Vision
* Edge Detection
* Hough Transform
* Lane Detection
* Circle Detection
* OpenCV

---

# License

This project is released under the MIT License.

---

# Author

**Hannah Fathi**

**M.Sc. Student in Artificial Intelligence and Robotics**

**Spring 2025**

**Research Interests**

* Computer Vision
* Medical AI
* Remote Sensing
* Image Processing
* Explainable AI
* Deep Learning
