# Exp-6--Record-EDGE-DETECTION
# EDGE-DETECTION

## Aim

To perform edge detection using Sobel, Laplacian, and Canny edge detectors.

## Software Required

- Anaconda - Python 3.7
- OpenCV
- NumPy
- Matplotlib

## Algorithm

### Step 1
Import all the necessary modules for the program.

### Step 2
Load an image using the `cv2.imread()` function.

### Step 3
Convert the image into grayscale using `cv2.cvtColor()`.

### Step 4
Use the Sobel operator from OpenCV to detect the edges of the image in the horizontal and vertical directions.

### Step 5
Use the Laplacian operator to detect edges based on second-order derivatives.

### Step 6
Use the Canny operator to detect edges in the image.

### Step 7
Display the edge-detected images using Matplotlib.

## Program

**Developed By:** VAISHNAVI S

**Register Number:** 212225230289

```python
import cv2
import numpy as np
import matplotlib.pyplot as plt

image = cv2.imread('vaishu.jpeg')  # Replace with your image path
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
# Original Image
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title('Original Image')
plt.axis('off')

sobel_x = cv2.Sobel(gray_image, cv2.CV_64F, 1, 0, ksize=5)  # Sobel in x direction
sobel_y = cv2.Sobel(gray_image, cv2.CV_64F, 0, 1, ksize=5)  # Sobel in y direction
sobel_combined = cv2.magnitude(sobel_x, sobel_y)  # Combine both directions
plt.imshow(sobel_combined, cmap='gray')
plt.title('Sobel Edge Detection')
plt.axis('off')

laplacian = cv2.Laplacian(gray_image, cv2.CV_64F)
plt.imshow(laplacian, cmap='gray')
plt.title('Laplacian Edge Detection')
plt.axis('off')

canny_edges = cv2.Canny(gray_image, 50, 150)
plt.imshow(canny_edges, cmap='gray')
plt.title('Canny Edge Detection')
plt.axis('off')  
```

## Output

### Input Image 

<img width="272" height="395" alt="Screenshot 2026-10-31 105341" src="https://github.com/user-attachments/assets/6b687e50-ccd3-4482-9343-293804812b07" />


### 1. Sobel Edge Detector

<img width="280" height="402" alt="Screenshot 2026-10-31 105347" src="https://github.com/user-attachments/assets/85327769-c894-40e8-b284-73dec6a38bc1" />


### 2. Laplacian Edge Detector

<img width="287" height="406" alt="Screenshot 2026-10-31 105505" src="https://github.com/user-attachments/assets/732ee5aa-5c62-4d57-ad15-b45c9a5dd14f" />


### 3. Canny Edge Detector

<img width="327" height="417" alt="Screenshot 2026-10-31 105437" src="https://github.com/user-attachments/assets/09fd8326-1679-4924-9d06-041902d605d6" />


## Result

Thus, the edges of the image were detected successfully using Sobel, Laplacian, and Canny edge detectors with OpenCV and Python.
