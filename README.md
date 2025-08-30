# 🎥 Motion-Based Frame Extraction

This repository contains an **educational project** that demonstrates how to detect movement in a video and extract frames where significant changes occur.

The code uses **OpenCV** and related image-processing libraries to compare consecutive frames of a video, highlight moving objects with bounding boxes, and save frames containing meaningful activity.


## 📌 Project Overview

The purpose of this project is to explore **computer vision techniques** for motion detection and frame extraction.

The approach involves:

1. Reading a video file frame by frame.
2. Converting frames to grayscale and applying Gaussian blur to reduce noise.
3. Computing the absolute difference between consecutive frames.
4. Thresholding and applying morphological operations to isolate moving regions.
5. Detecting contours and drawing bounding boxes around moving objects.
6. Saving frames with detected movement to a specified folder.

This project is **educational** and aims to help understand the basics of video motion analysis with OpenCV.


## ⚙️ Technologies Used

* **Python 3.8+**
* **OpenCV (cv2)** – Computer vision and image processing.
* **scikit-image** – Image utilities.
* **Matplotlib** – Visualization.
* **Google Colab + Google Drive** – Used in this project to run code and manage video/frame files.


## 📊 Features

* Detects moving objects between consecutive video frames.
* Highlights detected movement with bounding boxes.
* Saves frames containing significant activity.
* Adjustable parameters for flexibility across different types of videos.


## 🔧 Configurable Parameters

The following values are **tunable** depending on the type of video and the size of objects you want to detect:

* **Threshold value** in

  ```python
  _, threshold_frame = cv2.threshold(diff_frame, 20, 255, cv2.THRESH_BINARY)
  ```

  Controls the sensitivity of motion detection. A lower threshold detects smaller changes, but may increase noise.

* **Contour area bounds** in

  ```python
  if 4500 < cv2.contourArea(contour) < 100000:
  ```

  Filters out minimal (noise) or very large (irrelevant) moving areas. Values should be adjusted depending on the object size in your video.

* **Kernel size** in

  ```python
  kernel = cv2.getStructuringElement(cv2.MORPH_RECT, (10, 10))
  ```

  Affects how nearby regions merge. Increasing the kernel size can help group fragmented object parts.

---

## 📂 Workflow

1. **Input** – A video file (`.mp4` in this example).
2. **Processing** – Frame-by-frame motion detection using OpenCV.
3. **Output** – Frames with significant motion saved as `.png` files.

---

## 💻 Running the Project

### Option 1: Google Colab + Google Drive

This project was developed in **Google Colab**, storing input videos and output frames in **Google Drive**.

* Pros: Easy setup, cloud-based execution, no need to install locally.
* Steps:

  * Mount Google Drive in Colab.
  * Adjust file paths (`/content/drive/...`) accordingly.
  * Run the notebook.

### Option 2: Local Execution

The code can also be executed locally with the right environment.

#### Requirements

* Python 3.8+
* OpenCV
* scikit-image
* matplotlib

Install dependencies:

```bash
pip install opencv-python scikit-image matplotlib
```

#### Run

```bash
python motion_detection.py
```

Make sure to update:

* `path` → path to your input video.
* `output_path` → directory where frames will be saved.

---

## 🚀 Key Learning Outcomes

* How to compare consecutive frames for motion detection.
* Using **thresholding** and **morphological operations** to filter noise.
* Detecting and bounding moving objects with **contours**.
* Saving significant frames for further analysis.

