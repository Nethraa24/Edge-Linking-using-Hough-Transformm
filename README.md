# Edge-Linking-using-Hough-Transformm
## Aim:
To write a Python program to detect the lines using Hough Transform.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:

Import all the necessary modules for the program.
### Step2:

Load a image using imread() from cv2 module.
### Step3:

Convert the image to grayscale.
### Step4:

Using Canny operator from cv2,detect the edges of the image.
### Step5:

Using the HoughLinesP(),detect line co-ordinates for every points in the images.Using For loop,draw the lines on the found co-ordinates.Display the image.

## DEVELOPED BY : J NETHRAA
## REG NO. : 212222100031

### Input image and grayscale image
```python
import numpy as np
import cv2
import matplotlib.pyplot as plt
img=cv2.imread("Tower.jpg",0)
img_c=cv2.imread("Tower.jpg",1)
img_c=cv2.cvtColor(img_c,cv2.COLOR_BGR2RGB)
gray=cv2.cvtColor(img,cv2.COLOR_GRAY2RGB)
gray = cv2.GaussianBlur(gray,(3,3),0)
plt.figure(figsize=(13,13))
plt.subplot(1,2,1)
plt.imshow(img_c)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(gray)
plt.title("Gray Image")
plt.axis("off")
plt.show()
```
![image](https://github.com/Nethraa24/Edge-Linking-using-Hough-Transformm/assets/121215786/af7ba9fe-3ad0-43de-8ad7-4d8266e16f55)

### Canny Edge detector output
```python
canny=cv2.Canny(gray,120,150)
plt.imshow(canny)
plt.title("Canny Edge Detector")
plt.axis("off")
plt.show()
```
![image](https://github.com/Nethraa24/Edge-Linking-using-Hough-Transformm/assets/121215786/41d80769-bac1-4c70-9c5a-fae497ce1c1d)

### Detect points that form a line using HoughLinesP
```python
lines=cv2.HoughLinesP(canny,1,np.pi/180,threshold=80,minLineLength=50,maxLineGap=250)
```
### Draw lines on the image
```python
for line in lines:
    x1,y1,x2,y2=line[0]
    cv2.line(img_c,(x1,y1),(x2,y2),(255,0,0),3)
```

### Display the result of Hough transform
```python
plt.imshow(img_c)
plt.title("Result Image")
plt.axis("off")
plt.show()
```
![image](https://github.com/Nethraa24/Edge-Linking-using-Hough-Transformm/assets/121215786/d8cad39f-a2a3-4832-bfd4-21cb4de247b5)

### Result:
Thus the program is written with python and OpenCV to detect lines using Hough transform.
