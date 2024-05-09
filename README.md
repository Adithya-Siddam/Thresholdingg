# THRESHOLDING
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm
### Step1:
Load the necessary packages.
### Step 2:
Read the Image and convert to grayscale.
### Step 3:
Use Global thresholding to segment the image.
### Step 4:
Use Adaptive thresholding to segment the image.
### Step 5:
Use Otsu's method to segment the image.
### Step 6:
Display the results.

## Program
```
Developed by: S Adithya Chowdary.
Register No: 212221230100.
```
### Load the necessary packages
```python
import numpy as np
import matplotlib.pyplot as plt
import cv2
```
### Read the Image and convert to grayscale
```python
image = cv2.imread("dodge.jpg",1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread("dodge.jpg",0)
```
### Use Global thresholding to segment the image
```python
ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)
```
### Use Adaptive thresholding to segment the image
```python
thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)
```
### Use Otsu's method to segment the image
```python
ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)
```
### Display the results
```python
titles=["Gray Image","Threshold Image (Binary)","Threshold Image (Binary Inverse)","Threshold Image (To Zero)"
       ,"Threshold Image (To Zero-Inverse)","Threshold Image (Truncate)","Otsu","Adaptive Threshold (Mean)","Adaptive Threshold (Gaussian)"]
images=[image_gray,thresh_img1,thresh_img2,thresh_img3,thresh_img4,thresh_img5,thresh_img6,thresh_img7,thresh_img8]
for i in range(0,9):
    plt.figure(figsize=(10,10))
    plt.subplot(1,2,1)
    plt.title("Original Image")
    plt.imshow(image)
    plt.axis("off")
    plt.subplot(1,2,2)
    plt.title(titles[i])
    plt.imshow(cv2.cvtColor(images[i],cv2.COLOR_BGR2RGB))
    plt.axis("off")
    plt.show()
```
## Output

### Original Image
![image](https://github.com/Adithya-Siddam/Thresholdingg/assets/93427248/b8f5ca88-cf04-46ae-b76c-e4c4c8fae3ad)

### Global Thresholding
![image](https://github.com/Adithya-Siddam/Thresholdingg/assets/93427248/de337d12-50f5-47c7-9e83-85788aa6214d)
![image](https://github.com/Adithya-Siddam/Thresholdingg/assets/93427248/56cf018e-67c5-4112-af1f-ad9a5e986ef9)
![image](https://github.com/Adithya-Siddam/Thresholdingg/assets/93427248/e2a047f7-6902-4dd3-a808-26d7d455afa1)
![image](https://github.com/Adithya-Siddam/Thresholdingg/assets/93427248/dd9b6a5d-993e-4fb6-9ee2-8225f0f3e2a4)
![image](https://github.com/Adithya-Siddam/Thresholdingg/assets/93427248/7fde1188-cb61-466d-b0a4-6a421d1e0a8b)


### Adaptive Thresholding
![image](https://github.com/Adithya-Siddam/Thresholdingg/assets/93427248/0a9bfaf2-8820-4387-9d02-834e9f76c7da)
![image](https://github.com/Adithya-Siddam/Thresholdingg/assets/93427248/26892a4d-9c09-45f4-a1d2-97270d074be7)

### Optimum Global Thesholding using Otsu's Method
![image](https://github.com/Adithya-Siddam/Thresholdingg/assets/93427248/d946153b-337e-42c6-9c75-37f41dbb372b)

## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
