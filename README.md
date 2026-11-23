# EXP-7-HOUGH-TRANSFORM LANE DETECTION
## Aim
To implement a basic lane detection pipeline using OpenCV by completing missing code segments at specified locations.

## Learning Objective
Understand each stage of image processing

Learn how to build a complete computer vision pipeline

Practice writing code in guided sections

Important Instruction: 👉 Write code ONLY in places marked as # Your Code Here 👉 Do NOT modify any other part of the code

## Software Used
Anaconda – Python 3.7

Jupyter Notebook / VS Code

OpenCV (cv2)
NumPy
Matplotlib

## Algorithm & Explanation
Step 1: Import Libraries
import cv2
import numpy as np
import matplotlib.pyplot as plt

Step 2: Read the Image
#Read the image using OpenCV

Step 3: Convert to Grayscale
#Convert to grayscale.

Step 4: Display Images
plt.figure(figsize=(10,5))

Step 5: Thresholding
#Apply thresholding

Step 6: Region of Interest (ROI)
#ROI masking already provided
#(Do not modify)

Step 7: Edge Detection (Canny)
#Perform Edge Detection

Step 8: Gaussian Blur
#Apply Gaussian Blur

Step 9: Hough Transform
#Detect lines using Hough Transform

Step 10: Lane Detection Logic
 Already implemented

## PROGRAM 
## DEVELOPED BY:
## NAME: MONISHA S
## REGISTER NO: 212225040258
 
## CODE:
```
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Step 2: Load the image using imread() from cv2 module
image = cv2.imread('PHOTO1.jpeg')  # Replace 'image.jpg' with your image path

# Step 3: Convert the image to grayscale
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)

# Input image and grayscale image
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title("Input Image")
plt.axis('off')

plt.imshow(gray_image, cmap='gray')
plt.title("Grayscale Image")
plt.axis('off')

# Step 4: Using Canny operator from cv2, detect the edges of the image
edges = cv2.Canny(gray_image, 50, 150)

# Canny Edge Detector output
plt.imshow(edges, cmap='gray')
plt.title("Canny Edge Detector")
plt.axis('off')

# Step 5: Using the HoughLinesP(), detect line coordinates for every point in the image
# The parameters of HoughLinesP are: image, resolution, threshold, minLineLength, maxLineGap
lines = cv2.HoughLinesP(
    edges,
    1,
    np.pi / 180,
    100,
    minLineLength=50,
    maxLineGap=10
)

# Step 6: Using a for loop, draw the lines on the original image using the detected coordinates
# The lines variable contains the endpoints of the detected lines

import os
os.environ["OPENBLAS_NUM_THREADS"] = "1"

# Step 6: Draw the detected lines on the original image

for line in lines:
    x1, y1, x2, y2 = line[0]
    cv2.line(image, (x1, y1), (x2, y2), (0, 255, 0), 2)

# Display the result of Hough Transform (Image with lines)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title("Result of Hough Transform")
plt.axis('off')
```
 
 
## OUTPUT:
<img width="333" height="390" alt="image" src="https://github.com/user-attachments/assets/3ed54bf5-5ad1-4c67-8015-555762c0dddb" />


<img width="352" height="396" alt="image" src="https://github.com/user-attachments/assets/f4105ea1-9212-4be7-a2b4-79c334ed2755" />


<img width="350" height="395" alt="image" src="https://github.com/user-attachments/assets/f657d052-a6e1-442e-816d-77dc719f8eb9" />


<img width="357" height="400" alt="image" src="https://github.com/user-attachments/assets/2dae4f6a-a6e7-4045-89cc-bce633bcd2c3" />

## RESULT :
Thus, the lane detection pipeline is successfully implemented by completing the missing code sections. The system detects and highlights lane lines effectively.








