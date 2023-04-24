# Edge-Linking-using-Hough-Transform

## Aim:

To write a Python program to detect the lines using Hough Transform.

## Software Required:

Anaconda - Python 3.7

## Algorithm:

### Step1:

Import all the necessary packages required for the program.

### Step2:

Load a image using imread() from cv2 module.

### Step3:

Convert the image to grayscale image.

### Step4:

Using Canny edge operator from cv2, detect the edges of the image.

### Step5:

Using the HoughLinesP(), detect the line co-ordinates for every points in the images. Using For loop, draw the lines on the found co-ordinates.

### Step6:

Display the image found by the HoughLinesP() and end the program.

## Program:

```python

# Read image and convert it to grayscale image

import numpy as np
import matplotlib.pyplot as plt
import cv2
image = cv2.imread("tree.jpg",0)
img = cv2.GaussianBlur(image,(3,3),0)
plt.axis('off')
plt.imshow(img)
plt.show()

# Find the edges in the image using canny detector and display

edge = cv2.Canny(img,150,175)
plt.imshow(edge,cmap='gray')
plt.title('Edge Image')
plt.xticks([])
plt.yticks([])
plt.show()

# Detect points that form a line using HoughLinesP

lines=cv2.HoughLinesP(edge,1,np.pi/180, threshold=80, minLineLength=50,maxLineGap=250)

# Draw lines on the image

for line in lines:
    x1,y1,x2,y2 = line[0]
    cv2.line(edge,(x1,y1),(x2,y2),(255,0,0),3)
    
# Display the result

plt.imshow(edge)
plt.axis('off')
plt.show()

```

## Output:

### Input image:

![tree](https://user-images.githubusercontent.com/94231938/234076953-b7a6b112-40fa-47b7-a624-e2e394a2633b.jpg)

### Grayscale image

![i1](https://user-images.githubusercontent.com/94231938/234076989-ce9de0ea-2041-431d-bbb4-de60285f90a1.png)

### Canny Edge detector output:

![i2](https://user-images.githubusercontent.com/94231938/234077002-8e1ff14b-9bc0-4d08-be6c-1086b44dd334.png)

### Display the result of Hough transform

![i3](https://user-images.githubusercontent.com/94231938/234077022-c53c35be-7906-4941-b263-2c765c7acb82.png)

## Result:

Thus the program is written with python and OpenCV to detect lines using Hough transform.

