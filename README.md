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

## Program:
### Name: Sabarinath.R
### Register NUmber: 212223100048
```
import cv2
import numpy as np
import matplotlib.pyplot as plt

image = cv2.imread('temple.jpg') 
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  
plt.title("Input Image")
plt.axis('off')
plt.show()

plt.imshow(gray_image, cmap='gray')
plt.title("Grayscale Image")
plt.axis('off')
plt.show()

edges = cv2.Canny(gray_image, 50, 150) 
plt.imshow(edges, cmap='gray')
plt.title("Canny Edge Detector")
plt.axis('off')
plt.show()

lines = cv2.HoughLinesP(edges, 1, np.pi / 180, 100, minLineLength=50, maxLineGap=10)
if lines is not None:  
    for line in lines:
        x1, y1, x2, y2 = line[0]
        cv2.line(image, (x1, y1), (x2, y2), (0, 255, 0), 2)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  
plt.title("Result of Hough Transform")
plt.axis('off')
plt.show()
```
## Output
### Input image
![Screenshot 2025-04-30 113311](https://github.com/user-attachments/assets/49c19c6c-f39d-42cf-988e-59959dad9506)

### Grayscale image
![Screenshot 2025-04-30 113320](https://github.com/user-attachments/assets/412a49ca-82d5-40d2-939c-7210d8fbb474)


### Canny Edge detector output
![Screenshot 2025-04-30 113328](https://github.com/user-attachments/assets/49644518-c24d-41f9-9b23-10aa54ccb542)


### Display the result of Hough transform
![Screenshot 2025-04-30 113336](https://github.com/user-attachments/assets/27f330f8-53ce-4d33-8873-d64b6e8c9853)


## Result:
Thus we have successfully detected lines by using Hough Transform.
