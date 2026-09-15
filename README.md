
# OpenCV Image Processing Basics in Google Colab

This repository contains a collection of Python scripts and interactive notebooks demonstrating fundamental image processing techniques using **OpenCV (Open Source Computer Vision Library)** and **NumPy** inside a Google Colab environment.

##  Project Overview
The project covers core computer vision operations ranging from basic image loading and property inspections to advanced pixel manipulation, building collages, Region of Interest (ROI) selections, image thresholding, and an interactive command-line interface (CLI) tool for real-time image manipulation.

---

##  Features

### 1. Environment & Library Version Inspection
* Prints system and environment configurations including Python version and OpenCV version to ensure compatibility.

### 2. Image Loading & Basic Diagnostics
* Loads images in both color and grayscale modes (`cv2.IMREAD_UNCHANGED`, `cv2.IMREAD_GRAYSCALE`).
* Inspects key image properties: width, height, color channels, and total pixel count.
* Safely prints individual pixel values (BGR format).

### 3. Grayscale Conversion & Disk Storage
* Converts standard BGR images to Grayscale (`cv2.COLOR_BGR2GRAY`).
* Automatically writes and exports processed images back to disk using `cv2.imwrite`.

### 4. Dynamic Multi-Image Collage Generator
* Safely reads up to four images (`sample.jfif`, `s2.jfif`, `s3.jfif`, `s4.jfif`).
* Automatically normalizes channel configurations (converting Grayscale or RGBA to 3-channel BGR).
* Resizes all candidate images to a uniform resolution ($200 \times 200$ pixels).
* Uses NumPy horizontal (`np.hstack`) and vertical (`np.vstack`) stacking to generate a clean $2 \times 2$ grid collage.

### 5. Region of Interest (ROI) Selective Grayscaling
* Defines precise coordinate boundaries ($x, y, w, h$) to crop a specific sub-region of an image.
* Converts only the cropped area to grayscale while retaining color in the surrounding background image.
* Merges the processed ROI seamlessly back into the original color matrix.

### 6. Binary Image Thresholding
* Demonstrates fixed-level image segmentation using `cv2.threshold`.
* Generates side-by-side binary (black and white) comparisons using different threshold limits (e.g., Thresholds of `100` and `180`).

### 7. Interactive CLI Image Processor
Includes a menu-driven program (`process_image_menu`) that lets you manipulate images directly from your terminal using simple inputs:
* **Option 1**: Convert the current image to Grayscale.
* **Option 2**: Resize to custom Dimensions (Width/Height).
* **Option 3**: Crop a custom sub-region using dynamic $(x, y, w, h)$ coordinates.
* **Option 4**: Save your progress as a custom file.
* **Option 5**: Instantly display the active image state inside Google Colab.
* **Option 6**: Exit the interactive workspace loop safely.

---

##  Prerequisites & Installation

To run these files locally or in your cloud environment, install the required packages:

```bash
pip install opencv-python numpy
```

> **Note for Google Colab Users**: Standard GUI functions like `cv2.imshow()` can crash Colab runtimes. This project utilizes the secure `cv2_imshow` patch from `google.colab.patches` to render outputs inline smoothly.

---

## Quick Start

Simply open the notebook in Google Colab, upload your source images (e.g., `sample.jfif`, `s2.jfif`, `s3.jfif`, `s4.jfif`), and execute the cells sequentially!

##  Generated Outputs
The codebase automatically generates and saves the following artifacts during runtime:
* `gray_image.jpg` — Fully grayscaled image.
* `final_collage.jpg` — Beautifully resized $2 \times 2$ image grid.
* `image_with_gray_roi.jpg` — Hybrid image containing color and a grayscaled focus region.
* `binary_image_100.jpg` & `binary_image_180.jpg` — Segmented binary masks.
```
