# THRESHOLDING
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

### Step 1:
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
~~~


PROGRAM DEVELOPED BY: SYED MUHAMMED ZAHI
REG NUMBER: 212221230114

# Load the necessary packages

import numpy as np
import matplotlib.pyplot as plt
import cv2

# Read the Image and convert to grayscale

image = cv2.imread("image1.jpg",1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread("image1.jpg",0)

# Use Global thresholding to segment the image

ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)


# Use Adaptive thresholding to segment the image

thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)

# Use Otsu's method to segment the image 

ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)

# Display the results

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
~~~
## Output

### Original Image
![image](https://github.com/SdMdZahi7/Thresholdingg/assets/94187572/0bc8a11a-7f99-46a4-8ea2-e3fc1a2ed26b)


### Global Thresholding
![image](https://github.com/SdMdZahi7/Thresholdingg/assets/94187572/60c63b27-b071-48d9-8acd-bfa586e4919f)
![image](https://github.com/SdMdZahi7/Thresholdingg/assets/94187572/44463a38-15ab-4197-a8cd-4160e4045204)
![image](https://github.com/SdMdZahi7/Thresholdingg/assets/94187572/9459ecb5-0b8f-4ede-ab9c-e9457f53c744)
![image](https://github.com/SdMdZahi7/Thresholdingg/assets/94187572/707dbbd4-211f-44e9-8f56-0fdce0f71f80)
![image](https://github.com/SdMdZahi7/Thresholdingg/assets/94187572/8b024f35-8889-4bb5-b843-3597f80a7683)

### Adaptive Thresholding
![image](https://github.com/SdMdZahi7/Thresholdingg/assets/94187572/4a76c9c2-35a7-4743-9f02-7acb892f3162)
![image](https://github.com/SdMdZahi7/Thresholdingg/assets/94187572/ccf291f3-7d70-4cb6-8f9b-036fccb21c04)


### Optimum Global Thesholding using Otsu's Method
![image](https://github.com/SdMdZahi7/Thresholdingg/assets/94187572/83458646-42fc-4b63-9230-14c204675479)



## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
