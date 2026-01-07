# Classical Lane Detection Pipeline

## Overview
This project implements a **classical computer vision–based lane detection system** for road images. Unlike deep learning approaches, it relies on traditional image processing techniques such as color space thresholding, edge detection, region-of-interest masking, and line fitting using the Hough Transform and RANSAC.

The pipeline detects **left and right lane boundaries** in structured road environments and serves as a strong **baseline approach** for lane detection.

---

##  Key Concepts Used
- Color space transformations (HLS, HSV)
- Image thresholding for lane isolation
- Edge detection (Canny)
- Geometric filtering using Region of Interest (ROI)
- Line detection using Hough Transform
- Robust line fitting using RANSAC
- Temporal averaging for stable lane visualization

---

##  Lane Detection Pipeline

1. **HLS L-channel Extraction**  
   Enhances lane brightness under varying lighting conditions.

2. **White Lane Masking (HLS + HSV)**  
   Isolates white lane markings from asphalt.

3. **Grayscale Conversion**  
   Simplifies image data for edge detection.

4. **Gaussian Blur**  
   Reduces noise while preserving edges.

5. **Canny Edge Detection**  
   Extracts strong gradients corresponding to lane boundaries.

6. **Region of Interest (ROI) Masking**  
   Applies a trapezoidal mask to eliminate irrelevant regions.

7. **Hough Transform**  
   Detects candidate line segments from edge pixels.

8. **Slope-Based Filtering**  
   Separates left and right lanes based on slope.

9. **RANSAC Line Fitting**  
   Removes outliers and fits robust lane lines.

10. **Averaging & Visualization**  
    Stabilizes lane lines and overlays them on the original image.

---

##  Scenarios Where the System Performs Well
- Well-marked highways with clear white/yellow lane lines
- Straight or gently curved roads
- Daytime driving and clear weather
- Minimal vehicle occlusions
- High-contrast lane markings on uniform surfaces

---

##  Scenarios Where the System May Struggle
- Sharp curves or winding roads
- Nighttime or low-light conditions
- Rain, fog, or snow
- Faded or worn lane markings
- Heavy traffic and construction zones

---

##  Limitations
- **Curved Roads:** Assumes approximately straight lanes
- **Lighting Sensitivity:** Shadows and glare may cause false edges
- **Weather Dependency:** Adverse weather reduces visibility
- **Occlusions:** Vehicles may block lane markings
- **Fixed ROI:** Hard-coded ROI may not generalize well
- **Computational Load:** Hough + RANSAC affects real-time performance

---

## Sample Results
The project includes intermediate visualizations such as:
- Color-masked images
- Edge-detected frames
- ROI-applied edges
- Hough line detections
- Final averaged lane overlays

---

##  Technologies Used
- Python
- OpenCV
- NumPy
- Matplotlib

---

##  Project Structure
```text
classical-lane-detection/
│
├── images/                 # Input road images
├── outputs/                # Pipeline stage outputs
├── src/
│   ├── preprocessing.py
│   ├── edge_detection.py
│   ├── roi.py
│   ├── hough.py
│   ├── ransac.py
│   └── lane_detection.py
│
├── README.md
└── requirements.txt
