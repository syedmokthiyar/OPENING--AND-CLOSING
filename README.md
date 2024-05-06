## Aim
To implement Opening and Closing using Python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV
## Algorithm:
### Step1:
Import the necessary packages

### Step2:
Create the Text using cv2.putText

### Step3:
Create the structuring element

### Step4:
Use Opening operation

### Step5:
Use Closing Operation
 
## Program:
```
Developed by : Syed Mokthiyar S.M
Register no : 212222230156
```
## Import the necessary packages
```
import cv2
import numpy as np
from matplotlib import pyplot as plt
```
## Create the Text using cv2.putText
```
# Read the color image
input_image_path = 'bheem.png'
color_image = cv2.imread(input_image_path)

# Convert the color image to grayscale
gray_image = cv2.cvtColor(color_image, cv2.COLOR_BGR2GRAY)

# Perform edge detection using Canny
edges = cv2.Canny(gray_image, 100, 200)  # you can adjust the thresholds as needed

# Define the kernel size for erosion and dilation
kernel_size = 5
kernel = np.ones((kernel_size, kernel_size), np.uint8)

# Perform erosion
erosion = cv2.erode(edges, kernel, iterations=1)

# Perform dilation
dilation = cv2.dilate(edges, kernel, iterations=1)

# Perform opening
opening = cv2.morphologyEx(edges, cv2.MORPH_OPEN, kernel)

# Perform closing
closing = cv2.morphologyEx(edges, cv2.MORPH_CLOSE, kernel)
```


## Create the structuring element
```
plt.figure(figsize=(15, 10))
plt.subplot(2, 3, 1)
plt.imshow(cv2.cvtColor(color_image, cv2.COLOR_BGR2RGB))
plt.title('Original Color Image')
plt.axis('on')
```


## Use Opening operation
```
plt.subplot(2, 3, 2)
plt.imshow(opening, cmap='gray')
plt.title('Opening')
plt.axis('on')
```



## Use Closing Operation
```
plt.subplot(2, 3, 3)
plt.imshow(closing, cmap='gray')
plt.title('Closing')
plt.axis('on')

plt.show()

```
## Output:
### Display the input Image

![Screenshot 2024-05-06 233444](https://github.com/syedmokthiyar/OPENING--AND-CLOSING/assets/118787294/cfc9cac5-87e4-489d-84c6-7e2558016158)


### Display the result of Opening

![Screenshot 2024-05-06 233521](https://github.com/syedmokthiyar/OPENING--AND-CLOSING/assets/118787294/f8ae5368-6a6e-4bd6-bf7f-c547dddddaa0)


### Display the result of Closing

![Screenshot 2024-05-06 233546](https://github.com/syedmokthiyar/OPENING--AND-CLOSING/assets/118787294/0fde6594-ac41-4609-86a8-5f7b9b21caef)


## Result
Thus the Opening and Closing operation is used in the image using python and OpenCV.
