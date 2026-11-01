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


2.  **Original Grayscale Histogram:** A histogram showing the
    distribution of pixel intensity values in the original grayscale
    image.
3.  **Equalized Grayscale Histogram:** The histogram after applying
    histogram equalization.
4.  **Equalized Grayscale Image:** The grayscale image after contrast
    enhancement.
5.  **Equalized Color Image:** The color image after equalizing the
    Value (V) channel in HSV color space.
6.  **Color Image Comparison:** The original color image and equalized
    color image are displayed side by side.
7.  **Histogram Comparison:** The histograms of the original and
    equalized color images are displayed for comparison.

*Note: The output images and histograms depend on the contents of
`MyI.jpeg`. The notebook contains the visual outputs generated during
execution.*

## Result

Thus, histogram equalization was successfully performed on grayscale and
color images using OpenCV. The original and equalized images and their
histograms were displayed and compared.
