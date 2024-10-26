# Contour Analysis and Face Recognition using OpenCV
This repository contains a project for image processing tasks, including contour analysis, face detection, and face recognition using the Local Binary Pattern Histogram (LBPH) algorithm. The project leverages OpenCV, NumPy, and Google Colab for image processing and Google Drive integration for handling a database of face images.

## Project Overview
### Contour Analysis
The contour analysis module performs the following steps on an image:

* Image Preprocessing: Converts the image to grayscale and applies a binary threshold for clear contour detection.
* Contour Detection: Detects contours and filters out small contours based on a minimum area threshold to reduce noise.
* Centroid Calculation: Calculates the centroid of each valid contour using image moments.
* Visualization: Draws detected contours and centroids on the image, allowing visual inspection of the results.
### Face Recognition using LBPH
The face recognition module uses the Local Binary Pattern Histogram (LBPH) algorithm, which is effective for face recognition by capturing local textures in small regions of the face. It includes the following steps:

* Image Loading and Preprocessing: Loads face images from a directory, storing them in grayscale format.
* Model Training: Trains an LBPH model with the loaded face images, creating a mapping between image labels and file names.
* Face Matching: Matches a reference face image against the trained model, providing a label and confidence score.
## Features
**Contour Analysis:**
* Detects and filters contours based on area to remove noise.
* Calculates and displays centroids of valid contours.
* Avoids contours that touch the image border.
**Face Recognition:**
* Utilizes the LBPH algorithm for efficient face recognition.
* Extracts feature vectors based on LBP histograms for each region of the face.
* Compares reference images against the database and returns the closest match with confidence score.
## Project Structure
* contour_analysis.py: Code for contour detection and visualization.
* face_recognition.py: Code for face detection, model training, and face matching using LBPH.
* database/ folder: Directory for face images used in the LBPH model, stored in .pgm format.
## Prerequisites
To run this project, you will need:

* Python 3.x
* OpenCV, NumPy, SciPy, rarfile

```!pip install opencv-python opencv-contrib-python numpy scipy rarfile```
## Setup Instructions
1. **Google Drive Setup:**

* Import Google Drive in Colab to access the image database.
* Extract `.rar` files containing face images using `rarfile` to prepare the database.
2. **Loading and Training:**

* Load images from the database folder and train the LBPH face recognizer.
3. **Running Contour Analysis:**

* Execute the contour analysis code to detect, filter, and display contours on images.
4. **Face Matching:**

Use the reference image to identify matches within the database.
A lower confidence score indicates a closer match.
Example Usage
```
#Contour Analysis
python contour_analysis.py
#Face Recognition with LBPH
python face_recognition.py
```

## Results
Sample output:

* Contour Analysis: Visualizes detected contours and centroids.
* Face Recognition: Matches reference images with stored images, displaying match results and confidence.
## License
This project is licensed under the MIT License.
