# Pyramids and Optical Flow

## Overview

This project implements several classical computer vision techniques using Python, NumPy, and OpenCV.

The repository demonstrates:

- Lucas–Kanade Optical Flow
- Gaussian Image Pyramids
- Laplacian Image Pyramids
- Pyramid Image Blending

The goal is to demonstrate how **multi-scale image representations** can be used for motion estimation and seamless image blending.

---

## Repository Structure

Ex3_Pyramids_and_Optic_Flow/
│
├── ex3_utils.py
├── main.py
├── input/
├── result/
└── README.md

---

## Implemented Methods

### Optical Flow (Lucas–Kanade)

Function:
opticalFlow(img1, img2, step_size, win_size)


This function estimates motion between two images using the **Lucas–Kanade optical flow algorithm**.

The algorithm:

1. Computes spatial image gradients
2. Computes temporal differences between frames
3. Solves a least squares problem to estimate motion vectors

The output is a set of motion vectors describing the displacement between the two images.

---

### Gaussian Pyramid

Function:
gaussianPyr(img, levels)


A Gaussian pyramid represents an image at multiple resolutions.

Each level:
- Applies Gaussian smoothing
- Downsamples the image by a factor of 2

This produces progressively smaller images while preserving the overall structure of the original image.

---

### Laplacian Pyramid

Functions:
laplaceianReduce(img, levels)
laplaceianExpand(pyramid)


The Laplacian pyramid captures image details between Gaussian pyramid levels.

Construction:

1. Build a Gaussian pyramid
2. Expand the higher level
3. Subtract it from the current level

This stores the high-frequency details of the image.

The original image can later be reconstructed using `laplaceianExpand`.

---

### Pyramid Image Blending

Function:
pyrBlend(img1, img2, mask, levels)


This function blends two images using a mask and pyramid blending.

Steps:

1. Build Laplacian pyramids for both images
2. Build a Gaussian pyramid for the mask
3. Combine pyramid levels using the mask
4. Reconstruct the final blended image

This technique avoids sharp seams between the images.

---

## Running the Project

Run the demo script:

python main.py


The program demonstrates:

- Optical flow estimation
- Gaussian pyramid visualization
- Laplacian pyramid reconstruction
- Pyramid image blending

---

## Output

Generated images are saved in the `result/` folder.

Examples include:

- Optical flow visualization
- Gaussian pyramid
- Laplacian pyramid
- Blended images

---

## Dependencies

Install required packages:

pip install numpy opencv-python matplotlib


---

## Author

Moriya Bitton


-------------------------------------------------------

###### Ariel University, Israel || Semester B, 2021

