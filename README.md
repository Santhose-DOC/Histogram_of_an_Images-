# Experiment 03 -- Histogram of Images

### Name : Santhose Arockiaraj J
### Reg No: 212224230248

## Aim

To perform histogram equalization on grayscale and color images using
OpenCV and visualize the original and equalized images along with their
histograms.

## Procedure

1.  Import the required Python libraries: OpenCV (`cv2`), NumPy, and
    Matplotlib.
2.  Read the input image `MyI.jpeg` in grayscale mode using
    `cv2.imread()`.
3.  Display the original grayscale image and plot its histogram.
4.  Apply histogram equalization to the grayscale image using
    `cv2.equalizeHist()`.
5.  Display the equalized grayscale image and its histogram.
6.  Read the input image again in color mode.
7.  Convert the color image from BGR to HSV color space using
    `cv2.cvtColor()`.
8.  Apply histogram equalization to the Value (V) channel of the HSV
    image.
9.  Convert the equalized HSV image back to BGR color space.
10. Display the equalized color image, compare it with the original
    image, and plot their histograms.

## Program

``` python
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Histogram Equalization for Grayscale Images
img = cv2.imread('MyI.jpeg', cv2.IMREAD_GRAYSCALE)

plt.imshow(img, cmap='gray')
plt.title('Original Image')
plt.show()

plt.hist(img.ravel(), 256, range=[0, 256])
plt.title('Original Image')
plt.show()

img_eq = cv2.equalizeHist(img)

plt.hist(img_eq.ravel(), 256, range=[0, 256])
plt.title('Equalized Histogram')
plt.show()

plt.imshow(img_eq, cmap='gray')
plt.title('Original Image')
plt.show()

# Histogram Equalization for Color Images
img = cv2.imread('MyI.jpeg', cv2.IMREAD_COLOR)

img_hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)
img_hsv[:, :, 2] = cv2.equalizeHist(img_hsv[:, :, 2])
img_eq = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)

plt.imshow(img_eq[:, :, ::-1])
plt.title('Equalized Image')
plt.show()

plt.hist(img_eq.ravel(), 256, range=[0, 256])
plt.title('Histogram Equalized')
plt.show()

plt.figure(figsize=(20, 10))
plt.subplot(221)
plt.imshow(img[:, :, ::-1])
plt.title('Original Color Image')

plt.subplot(222)
plt.imshow(img_eq[:, :, ::-1])
plt.title('Equalized Image')
plt.show()

plt.figure(figsize=[15, 4])
plt.subplot(121)
plt.hist(img.ravel(), 256, range=[0, 256])
plt.title('Original Image')

plt.subplot(122)
plt.hist(img_eq.ravel(), 256, range=[0, 256])
plt.title('Histogram Equalized')
plt.show()
```

## Output

 **Original Grayscale Image:** 
 
<img width="309" height="351" alt="image" src="https://github.com/user-attachments/assets/362b5301-252f-4d68-9e39-005460ac1779" />


**Original Grayscale Histogram:** 

<img width="470" height="352" alt="image" src="https://github.com/user-attachments/assets/c456c097-b368-4cdc-af26-32f1d203b73c" />

**Equalized Grayscale Histogram:**

<img width="483" height="351" alt="image" src="https://github.com/user-attachments/assets/083463d8-079a-436b-b1fb-9d2ae0d474d1" />

  
**Equalized Grayscale Image:** 

<img width="286" height="347" alt="image" src="https://github.com/user-attachments/assets/8a74a1da-5e59-4341-b1b7-d12a969aaa23" />


**Equalized Color Image:**

<img width="315" height="347" alt="image" src="https://github.com/user-attachments/assets/6c705328-f736-4e56-81a3-5cd225552792" />


**Color Image Comparison:**

<img width="862" height="309" alt="image" src="https://github.com/user-attachments/assets/2153c6da-ac4e-44e7-9fbf-3f33dfbf3fce" />


**Histogram Comparison:** T

<img width="861" height="273" alt="image" src="https://github.com/user-attachments/assets/a9e45cb3-2c5d-485b-8a29-356d16b560eb" />


## Result

Thus, histogram equalization was successfully performed on grayscale and
color images using OpenCV. The original and equalized images and their
histograms were displayed and compared.
