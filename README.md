# Implementation-of-filter
### Name - Priyanka K
### Register Number - 212223230162
## Aim:
To implement filters for smoothing and sharpening the images in the spatial domain.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1
Import the required libraries.

### Step2
Convert the image from BGR to RGB.

### Step3
Apply the required filters for the image separately.

### Step4
Plot the original and filtered image by using matplotlib.pyplot.

### Step5
End the program.

## Program:

### 1. Smoothing Filters
```
Name: Priyanka K
Reg.No: 212223230162
```

#### i) Using Averaging Filter
```
import cv2
import matplotlib.pyplot as plt
import numpy as np
image1=cv2.imread("flower.jpg")
image2=cv2.cvtColor(image1,cv2.COLOR_BGR2RGB)
kernel=np.ones((11,11),np.float32)/169
image3=cv2.filter2D(image2,-1,kernel)
plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Average Filter Image")
plt.axis("off")
plt.show()
```
## Output
<img width="717" height="606" alt="image" src="https://github.com/user-attachments/assets/7da361ae-2fc1-4427-a77c-f5337e87f34b" />

#### ii) Using Weighted Averaging Filter
```
kernel1=np.array([[1,2,1],[2,4,2],[1,2,1]])/16
plt.figure(figsize=(8,8))

plt.imshow(image3)
plt.title("Weighted Average Filter Image")
plt.axis("off")
plt.show()
```
## Output
<img width="364" height="656" alt="image" src="https://github.com/user-attachments/assets/c5502213-f29c-4161-857f-8b317a1d4b17" />

#### iii) Using Gaussian Filter
```
gaussian_blur=cv2.GaussianBlur(image2,(33,33),0,0)
plt.figure(figsize=(8,8))

plt.imshow(image2)
plt.imshow(gaussian_blur)
plt.title("Gaussian Blur")
plt.axis("off")
plt.show()
```
## Output
<img width="364" height="656" alt="image" src="https://github.com/user-attachments/assets/f01c41f6-179f-4839-87c4-16ce955324aa" />

#### iv)Using Median Filter
```
median=cv2.medianBlur(image2,13)

plt.imshow(median)
plt.title("Median Blur")
plt.axis("off")
plt.show()
```
## Output
<img width="226" height="409" alt="image" src="https://github.com/user-attachments/assets/9f6c78bf-85c6-4417-941a-a0fe0a9d88c4" />

### 2. Sharpening Filters

#### i) Using Laplacian Linear Kernal
```
kernel2=np.array([[-1,-1,-1],[2,-2,1],[2,1,-1]])
image3=cv2.filter2D(image2,-1,kernel2)
plt.imshow(image3)
plt.title("Laplacian Kernel")
plt.axis("off")
plt.show()
```
## Output
<img width="226" height="409" alt="image" src="https://github.com/user-attachments/assets/f3f979ab-d766-497b-81f8-535e3e79b6ac" />

#### ii) Using Laplacian Operator
```
laplacian=cv2.Laplacian(image2,cv2.CV_64F)
laplacian = cv2.convertScaleAbs(laplacian) 
plt.imshow(laplacian)
plt.title("Laplacian Operator")
plt.axis("off")
plt.show()
```
## Output
<img width="226" height="409" alt="image" src="https://github.com/user-attachments/assets/37aba842-aa95-4714-97c8-a3cccbc1339c" />

## Result:
Thus the filters are designed for smoothing and sharpening the images in the spatial domain.
