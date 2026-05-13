# 🤖 Machine Vision using OpenCV, RoboDK & Dobot MG400

<div align="center">

[![Live Demo](https://img.shields.io/badge/▶_Live_Demo-00FFD1?style=for-the-badge)](https://sazzadmahfuz.github.io/machine-vision-opencv)
![Python](https://img.shields.io/badge/Python-3.10+-blue?style=for-the-badge&logo=python)
![OpenCV](https://img.shields.io/badge/OpenCV-Computer_Vision-green?style=for-the-badge&logo=opencv)
![RoboDK](https://img.shields.io/badge/RoboDK-Robot_Simulation-orange?style=for-the-badge)
![Robotics](https://img.shields.io/badge/Robotics-Dobot_MG400-red?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Completed-success?style=for-the-badge)
![License](https://img.shields.io/badge/License-MIT-lightgrey?style=for-the-badge)

### Advanced Machine Vision Pipeline for Industrial Robotics and Pick-and-Place Automation

---

**Developed by:**  
### 👨‍💻 Sazzad Ibna Mahfuz

Bachelor of Engineering — ICT Robotics  
Häme University of Applied Sciences (HAMK), Finland

</div>

---

# Project Overview

This project demonstrates a complete **Machine Vision workflow** for robotic applications using:

- Python
- OpenCV
- RoboDK
- Dobot MG400 Robot
- Image Segmentation
- Camera-Robot Calibration
- Homography Mapping
- Coordinate Transformation
- Real-time Vision Annotation

The project was developed as part of the **Machine Vision** coursework at  
**Häme University of Applied Sciences (HAMK)**.

The system simulates an industrial robotic vision pipeline capable of:

✅ Capturing images from RoboDK simulated cameras  
✅ Performing RGB channel analysis  
✅ Segmenting objects from backgrounds  
✅ Detecting object centroids and bounding boxes  
✅ Applying morphology operations  
✅ Computing homography matrices  
✅ Mapping image pixel coordinates to robot coordinates  
✅ Supporting robot pick-and-place workflows

---

# Objectives

The primary objectives of this project were:

- Understand OpenCV image processing fundamentals
- Work with simulated machine vision systems in RoboDK
- Perform image segmentation and object extraction
- Develop robust preprocessing pipelines
- Learn contour and connected component analysis
- Implement homography-based camera calibration
- Transform image coordinates into robot workspace coordinates
- Simulate industrial robotic vision applications

---

# Project Demonstration

This project combines robotics, computer vision, image segmentation, and camera calibration into a complete industrial machine vision workflow.

The following screenshots demonstrate the complete processing pipeline from image acquisition to robot coordinate mapping and visualization.

---

<table align="center">
<tr>
<td align="center" width="50%">

<img src="Pictures/1%20(1).png" width="95%">

### RGB Channel Separation

Red, Green, and Blue channel extraction using OpenCV for color analysis and feature visibility evaluation.

</td>

<td align="center" width="50%">

<img src="Pictures/1%20(2).png" width="95%">

### Segmentation Pipeline

Thresholding, grayscale conversion, CLAHE enhancement, and binary segmentation workflow.

</td>
</tr>

<tr>
<td align="center" width="50%">

<img src="Pictures/1%20(3).png" width="95%">

### Object Detection & Morphology

Connected component analysis, contour extraction, morphology cleanup, and centroid detection.

</td>

<td align="center" width="50%">

<img src="Pictures/1%20(4).png" width="95%">

### Coordinate Mapping

Pixel-to-robot coordinate transformation using homography calibration techniques.

</td>
</tr>

<tr>
<td align="center" width="50%">

<img src="Pictures/1%20(5).png" width="95%">

### Homography Calibration

Robot-camera calibration system for industrial coordinate transformation and workspace mapping.

</td>

<td align="center" width="50%">

<img src="Pictures/1%20(6).png" width="95%">

### Interactive Dashboard

Custom visualization dashboard with segmentation preview and coordinate monitoring tools.

</td>
</tr>
</table>

---

# System Architecture

```text
Camera Image
     │
     ▼
Image Acquisition
     │
     ▼
Preprocessing
(Grayscale + CLAHE + Blur)
     │
     ▼
Thresholding
(Otsu Binary Segmentation)
     │
     ▼
Morphological Operations
(Open + Close)
     │
     ▼
Connected Components
(Centroids + Bounding Boxes)
     │
     ▼
Pixel Coordinate Extraction
     │
     ▼
Homography Mapping
     │
     ▼
Robot Coordinates (X,Y)
     │
     ▼
Pick-and-Place Ready
```

---

# Technologies Used

| Technology | Purpose |
|---|---|
| Python | Core programming language |
| OpenCV | Image processing and computer vision |
| NumPy | Matrix operations |
| Matplotlib | Visualization |
| RoboDK | Robot simulation |
| Dobot MG400 | Robotic manipulator |
| HTML/CSS/JS | Interactive dashboard |
| Chart.js | Histograms and visual analytics |

---

# Machine Vision Concepts Implemented

## RGB Channel Separation

The system separates:

- Red Channel
- Green Channel
- Blue Channel

from the original image to analyze:

- Color dominance
- Illumination effects
- Object visibility
- Feature extraction potential

---

## Image Segmentation

Implemented segmentation pipeline:

```python
Image → Grayscale → CLAHE → Gaussian Blur
→ Otsu Threshold → Morphology → Detection
```

Techniques used:

- Global Thresholding
- Otsu Thresholding
- Binary Inverse Segmentation
- Connected Component Labeling

---

## Morphological Operations

Implemented:

### Opening
Used to remove noise and small blobs.

```python
cv2.morphologyEx(binary, cv2.MORPH_OPEN, kernel)
```

### Closing
Used to fill small holes and gaps.

```python
cv2.morphologyEx(opened, cv2.MORPH_CLOSE, kernel)
```

---

## Connected Components Analysis

Object extraction performed using:

```python
cv2.connectedComponentsWithStats()
```

Extracted features:

- Bounding Boxes
- Centroids
- Area
- Labels
- Width & Height

---

# RoboDK Integration

The project integrates RoboDK simulated cameras for:

- Virtual image acquisition
- Robot workspace simulation
- Industrial scene generation
- Pick-and-place validation

The system captures snapshots from RoboDK and processes them in Python using OpenCV.

---

# Robot-Camera Calibration

A homography matrix was computed to map:

```text
Pixel Coordinates (u,v)
            ↓
Robot Coordinates (X,Y)
```

using:

```python
cv2.findHomography()
```

---

# Calibration Dataset

8-point calibration mapping used:

| Point | Robot X | Robot Y | Pixel U | Pixel V |
|---|---|---|---|---|
| P1 | 350 | 0 | 604 | 717 |
| P2 | 350 | 100 | 609 | 1235 |
| P3 | 275 | 50 | 997 | 951 |
| P4 | 325 | -50 | 721 | 468 |
| P5 | 375 | -75 | 476 | 482 |
| P6 | 375 | 50 | 484 | 973 |
| P7 | 300 | -25 | 847 | 586 |
| P8 | 325 | 50 | 740 | 962 |

---

# Homography Matrix

The generated transformation matrix:

```python
H = np.array([
 [-7.51502460e-02, 1.27010501e-01, 5.81602325e+02],
 [ 7.29485611e-02, 4.03281035e-01, 3.41328093e+02],
 [ 9.18657123e-04, 3.44012941e-04, 1.00000000e+00]
])
```

---

# Pixel → Robot Coordinate Transformation

```python
def pixel_to_robot(u, v, H):
    p = np.array([u, v, 1.0], dtype=np.float32).reshape(3,1)
    pr = H @ p
    pr = pr / pr[2,0]

    X = pr[0,0]
    Y = pr[1,0]

    return X, Y
```

---

# Validation Results

| Metric | Result |
|---|---|
| Mean Error | < 1 mm |
| Maximum Error | < 2 mm |
| Processing Speed | < 0.01 sec |
| Calibration Points | 8 |
| Coordinate System | 2D Homography |

The system achieved industrial-level accuracy suitable for:

- Pick-and-place
- Coordinate localization
- Robotic sorting
- Workspace mapping

---

# Segmentation Pipeline

## Step 1 — Image Acquisition

Captured simulated and real images from RoboDK and external camera systems.

---

## Step 2 — Grayscale Conversion

```python
gray = cv2.cvtColor(img, cv2.COLOR_BGR2GRAY)
```

---

## Step 3 — CLAHE Enhancement

Contrast Limited Adaptive Histogram Equalization:

```python
clahe = cv2.createCLAHE(
    clipLimit=2.0,
    tileGridSize=(8,8)
)
```

Purpose:

- Enhance local contrast
- Improve dark object visibility
- Stabilize thresholding

---

## Step 4 — Gaussian Blur

```python
blurred = cv2.GaussianBlur(
    gray_clahe,
    (5,5),
    0
)
```

Used for:

- Noise reduction
- Smooth threshold boundaries

---

## Step 5 — Otsu Thresholding

```python
_, binary = cv2.threshold(
    blurred,
    0,
    255,
    cv2.THRESH_BINARY_INV + cv2.THRESH_OTSU
)
```

---

## Step 6 — Morphology Cleanup

```python
kernel = cv2.getStructuringElement(
    cv2.MORPH_RECT,
    (5,5)
)
```

---

## Step 7 — Object Detection

```python
connectedComponentsWithStats()
```

Objects filtered by area threshold:

```python
MIN_AREA = 1244
```

---

# Histogram Analysis

Histogram analysis was used to validate:

- Bimodal distributions
- Object-background separation
- Thresholding effectiveness

The grayscale histogram demonstrated clear separation between:

- Bright background
- Dark foreground objects

which enabled stable Otsu segmentation.

---

# Real Image Processing

The pipeline was tested on:

✅ Black markers  
✅ Dark tiles  
✅ Mixed-color objects  
✅ Real camera images  
✅ Simulated RoboDK images

The same pipeline generalized successfully across all datasets.

---

# Features

## Interactive Dashboard

The project includes a custom interactive dashboard featuring:

- RGB visualization
- Histograms
- Segmentation previews
- Mapping tools
- Homography visualization
- Live coordinate display

---

## Click-to-Map System

Users can click on image points to obtain:

```text
Pixel Coordinates → Robot Coordinates
```

in real time.

---

# Future Improvements

Potential future developments:

- Real-time webcam integration
- YOLO object detection
- ArUco marker calibration
- 3D camera calibration
- ROS2 integration
- Robot pick-and-place automation
- AI-based segmentation
- Deep learning vision pipelines
- Multi-camera fusion
- Real industrial PLC integration

---

# Key Learning Outcomes

This project helped develop practical skills in:

✅ OpenCV image processing  
✅ RoboDK simulation  
✅ Robot-camera calibration  
✅ Homography mathematics  
✅ Coordinate transformations  
✅ Morphological filtering  
✅ Object segmentation  
✅ Connected component analysis  
✅ Industrial robotics workflows  
✅ Human-machine interaction systems

---

# 👨‍💻 Author

## Sazzad Ibna Mahfuz

Bachelor of Engineering — ICT Robotics  
Häme University of Applied Sciences (HAMK)  
Finland
[Portfolio](https://sazzadmahfuz.github.io) · [LinkedIn](https://www.linkedin.com/in/sazzad-mahfuz) · [GitHub](https://github.com/sazzadmahfuz)



<div align="center">

# ⭐ If you found this project interesting, consider starring the repository!

</div>
