# THRESHOLDING
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
Use Otsu's method to segment the image.

### Step6:
Display the results.

## Program
```
 Developed By: YUVARAJ B
 Register No: 212222230182
```
```python
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

### Original Image
![image](https://github.com/22009011/Thresholdingg/assets/118343461/2f0b4fec-e0b7-422d-842e-99716a0adc52)




### Global Thresholding
![image](https://github.com/22009011/Thresholdingg/assets/118343461/d830e7e0-8677-414a-a480-e5b4462208c1)



![image](https://github.com/22009011/Thresholdingg/assets/118343461/10322dfc-d3a8-4f34-b459-6bdd660537a7)



![image](https://github.com/22009011/Thresholdingg/assets/118343461/096642cf-e138-4f0a-9b46-4cd699b27eda)


![image](https://github.com/22009011/Thresholdingg/assets/118343461/62c0d6e2-9de7-4235-bff2-a346a00bb3ac)


![image](https://github.com/22009011/Thresholdingg/assets/118343461/72763263-c412-4435-bc97-192b58049701)


### Adaptive Thresholding
![image](https://github.com/22009011/Thresholdingg/assets/118343461/c1d3a594-c139-4ca0-a4be-93c75f8fb6c4)


![image](https://github.com/22009011/Thresholdingg/assets/118343461/034160b4-21c3-4476-8f83-8f863e4b9c1a)


### Optimum Global Thesholding using Otsu's Method
![image](https://github.com/22009011/Thresholdingg/assets/118343461/21a786c9-d5a6-49d1-b7f0-43933125bcb6)



## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
