# Ex. No: 03 Histogram Processing
# NAME : Dhanappriya S
# REG NO :212224230056

# Aim

To perform histogram equalization on grayscale and color images using OpenCV and Matplotlib to improve the contrast and visual clarity of the images.



# Procedure

## **Part 1: Histogram Equalization for Grayscale Images**

1. **Import Libraries:** Import the necessary libraries (`cv2`, `numpy`, and `matplotlib.pyplot`).
2. **Load the Image:** Read the input image in grayscale mode (`cv2.IMREAD_GRAYSCALE`).
3. **Display Original Image:** Plot and display the original grayscale image using `plt.imshow()`.
4. **Plot Original Histogram:** Compute and plot the pixel intensity distribution (histogram) of the original grayscale image using `plt.hist()`.
5. **Apply Equalization:** Enhance the contrast of the grayscale image using OpenCV's histogram equalization function (`cv2.equalizeHist()`).
6. **Display Equalized Results:** Plot the histogram and display the equalized image to observe the improvement in contrast.

## **Part 2: Histogram Equalization for Color Images**

1. **Load Color Image:** Read the input image in color mode (`cv2.IMREAD_COLOR`).
2. **Convert Color Space:** Convert the image from the BGR color space to the HSV color space using `cv2.cvtColor()`.
3. **Equalize the Value Channel:** Extract the Value ($V$) channel (which represents brightness/intensity) from the HSV image and apply histogram equalization specifically to it, preserving the color information.
4. **Convert Back to BGR:** Merge the channels and convert the HSV image back to the BGR color space.
5. **Visualize and Compare:**
* Display both the original color image and the equalized color image side by side using subplots.
* Plot and compare the histograms of the original and equalized color images.
  
# Code:
```python
import cv2
import numpy as np
import matplotlib.pyplot as plt
img = cv2.imread('photo.jpg', cv2.IMREAD_GRAYSCALE)
plt.imshow(img, cmap='gray')
plt.title('Original Image')
plt.show()
plt.hist(img.ravel(),256,range = [0, 256]);
plt.title('Original Image')
plt.show()
img_eq = cv2.equalizeHist(img)
plt.hist(img_eq.ravel(), 256, range = [0, 256])
plt.title('Equalized Histogram')
plt.imshow(img_eq, cmap='gray')
plt.title('Original Image')
plt.show()
img = cv2.imread('photo.jpg', cv2.IMREAD_COLOR)
img_hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)
img_hsv[:,:,2] = cv2.equalizeHist(img_hsv[:, :, 2])
img_eq = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)
plt.imshow(img_eq[:,:,::-1]); plt.title('Equalized Image');plt.show()
plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized');plt.show()
plt.figure(figsize = (20,10))
plt.subplot(221); plt.imshow(img[:, :, ::-1]); plt.title('Original Color Image')
plt.subplot(222); plt.imshow(img_eq[:, :, ::-1]); plt.title('Equalized Image')
plt.show()
plt.figure(figsize = [15,4])
plt.subplot(121); plt.hist(img.ravel(),256,range = [0, 256]); plt.title('Original Image')
plt.subplot(122); plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized')
```
# Output:
<img width="1372" height="560" alt="image" src="https://github.com/user-attachments/assets/72203373-d60e-4e34-aac9-fa817f995a13" />
<img width="1386" height="557" alt="image" src="https://github.com/user-attachments/assets/48311415-9ec1-41a3-9482-9d98fb3b3afa" />
<img width="1440" height="613" alt="image" src="https://github.com/user-attachments/assets/c322be5f-e5a8-41e1-97ef-7b2dd17d9d65" />
<img width="1497" height="480" alt="image" src="https://github.com/user-attachments/assets/2c3ac7da-1167-4ecd-a69e-4203782af9dc" />
<img width="1430" height="515" alt="image" src="https://github.com/user-attachments/assets/6efbe43f-4175-4e91-8a54-ea35c21dbc16" />

# Result:
Thus the histogram equalization on grayscale and color images using OpenCV and Matplotlib to improve the contrast and visual clarity of the images was verified succssfully.




