# EX-08 THRESHOLDING
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm
### Step1:
Load the necessary packages.
### Step2:
Read the Image and convert to grayscale.
### Step3:
Use Global thresholding to segment the image.
### Step4:
Use Adaptive thresholding to segment the image.
### Step5:
Use Otsu's method to segment the image and display the results.
## Program
```
DEVELOPED BY: YOHESH KUMAR R.M
REGISTER NO: 212222240118
```
### Load the necessary packages
```
import numpy as np
import matplotlib.pyplot as plt
import cv2
```
### Read the Image and convert to grayscale
```
image = cv2.imread("deadpool",1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread("dark.jpeg",0)
```
### Use Global thresholding to segment the image
```
ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)
```
### Use Adaptive thresholding to segment the image
```
thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)
```
### Use Otsu's method to segment the image 
```
ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)
```
### Display the results
```
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
![image](https://github.com/yoheshkumar/THRESHOLDING-/assets/119393568/4373ab4d-10fe-4c59-8c34-bdac4231b689)


### Global Thresholding
![image](https://github.com/yoheshkumar/THRESHOLDING-/assets/119393568/07cd7004-da64-4ed5-854a-4c774c7031a3)
![image](https://github.com/yoheshkumar/THRESHOLDING-/assets/119393568/cb4ab513-4437-4892-b9b6-e6c7d7f2152e)
![image](https://github.com/yoheshkumar/THRESHOLDING-/assets/119393568/fcd0d9a4-1cba-4553-b40b-7d6166345626)
![image](https://github.com/yoheshkumar/THRESHOLDING-/assets/119393568/2e8e674e-e731-424a-8ce1-97ee6181e5fb)
![image](https://github.com/yoheshkumar/THRESHOLDING-/assets/119393568/c2dc16bc-4111-44f9-acd7-ee97f225be60)

### Adaptive Thresholding
![image](https://github.com/yoheshkumar/THRESHOLDING-/assets/119393568/3497976b-0420-400f-af41-aaac3d422325)
![image](https://github.com/yoheshkumar/THRESHOLDING-/assets/119393568/2b8bccf3-bc9f-4b77-b096-aeedd93284ec)

### Optimum Global Thesholding using Otsu's Method
![image](https://github.com/yoheshkumar/THRESHOLDING-/assets/119393568/57a71dc6-4c9e-4977-97a7-f5b560b1b1e6)

## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
