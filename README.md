# THRESHOLDING
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

## Step1:
Load the necessary packages

## Step2:
Read the Image and convert to grayscale.

## Step3:
Use Global thresholding to segment the image.

## Step4:
Use Adaptive thresholding to segment the image.

## Step5:
Use Otsu's method to segment the image and display the results.

## Program

```
# Load the necessary packages
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Read the Image and convert to grayscale

image=cv2.imread("DUCK.jpg",1)
image=cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray=cv2.imread("DUCK.jpg",0)

# Use Global thresholding to segment the image
ret,thresh_dipt1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_dipt2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_dipt3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_dipt4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_dipt5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)

# Use Adaptive thresholding to segment the image

ret,thresh_dipt6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)

# Use Otsu's method to segment the image 

thresh_dipt7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_dipt8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)

# Display the results

titles=["Gray Image","Threshold Image (Binary)","Threshold Image (Binary Inverse)","Threshold Image (To Zero)"
       ,"Threshold Image (To Zero-Inverse)","Threshold Image (Truncate)","Otsu","Adaptive Threshold (Mean)","Adaptive Threshold (Gaussian)"]
images=[image_gray,thresh_dipt1,thresh_dipt2,thresh_dipt3,thresh_dipt4,thresh_dipt5,thresh_dipt6,thresh_dipt7,thresh_dipt8]
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
![image](https://github.com/MANOKARTHICK09/Thresholdingg/assets/121785458/053cabc8-4ad9-492f-91e2-bd92b6ca65f4)

![image](https://github.com/MANOKARTHICK09/Thresholdingg/assets/121785458/ce27b5fb-f6d1-4318-8732-e336ac81418d)

![image](https://github.com/MANOKARTHICK09/Thresholdingg/assets/121785458/a409d21f-9e63-4bd0-8cbf-6e8c72cbc7e0)
![image](https://github.com/MANOKARTHICK09/Thresholdingg/assets/121785458/8a91cc1f-99cb-40bf-a0a4-6f442c1b06bc)



![image](https://github.com/MANOKARTHICK09/Thresholdingg/assets/121785458/5df57b37-0db7-46f4-a754-d03d98e02178)

![image](https://github.com/MANOKARTHICK09/Thresholdingg/assets/121785458/3166b1de-75d2-4d5e-b36b-49ec1d1e44cc)
![image](https://github.com/MANOKARTHICK09/Thresholdingg/assets/121785458/95b61d23-add2-47c1-bd34-a86662c9bc06)
![image](https://github.com/MANOKARTHICK09/Thresholdingg/assets/121785458/8c8e805b-472e-4455-8b4c-8fd16aaa3709)


![image](https://github.com/MANOKARTHICK09/Thresholdingg/assets/121785458/94f2e7db-b5f7-4008-a4cf-94b83887ec47)



## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
