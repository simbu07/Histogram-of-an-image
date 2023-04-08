# Histogram and Histogram Equalization of an image

## Aim:

To obtain a histogram for finding the frequency of pixels in an Image with pixel values ranging from 0 to 255. Also write the code using OpenCV to perform histogram equalization.

## Software Required:

Anaconda - Python 3.7 .

## Algorithm:

### Step 1:

Import cv2, matplotlib.py libraries and display the saved images using cv2.imshow().

### Step 2:

Use cv2.calcHist(images, channels, mask, histSize, ranges[, hist[, accumulate]]) to find the histogram of the image.

### Step 3:

Plot the image and its stem plots using the plt.show() and plt.stem() functions.

### Step 4:

Equalize the grayscale image using the in-built function cv2.equalizeHist().

### Step 5:

Print the original and equalized image using cv2.imshow() and end the program.

## Program:

```python

## Developed By : Silambarasan. K
## Register Number : 212221230101

```

### Write your code to find the histogram of gray scale image and color image channels:

```python

import cv2
import matplotlib.pyplot as plt
gray_image = cv2.imread("gray.jpg")
clr_image = cv2.imread("color.jpg",-1)
cv2.imshow("Gray Image",gray_image)
cv2.imshow("Colour Image",clr_image)
cv2.waitKey(0)
cv2.destroyAllWindows()

```

### Display the histogram of gray scale image and any one channel histogram from color image:

```python

import cv2
import matplotlib.pyplot as plt
gray_image = cv2.imread("gray.jpg")
clr_image = cv2.imread("color.jpg",-1)
gray_hist = cv2.calcHist([gray_image],[0],None,[256],[0,256])
clr_hist = cv2.calcHist([clr_image],[0],None,[256],[0,256])
plt.figure()
plt.imshow(gray_image)
plt.show()
plt.title("Histogram")
plt.xlabel("Grayscale Value")
plt.ylabel("Pixel Count")
plt.stem(gray_hist)
plt.show()
plt.imshow(clr_image)
plt.show()
plt.title("Histogram of Color Image - Green Channel")
plt.xlabel("Intensity Value")
plt.ylabel("Pixel Count")
plt.stem(clr_hist)
plt.show()


```



### Write the code to perform histogram equalization of the image:

```python

import cv2
import matplotlib.pyplot as plt
gray_image = cv2.imread("gray.jpg",0)
cv2.imshow("Gray Image",gray_image)
equ = cv2.equalizeHist(gray_image)
cv2.imshow("Equalized Image",equ)
cv2.waitKey(0)
cv2.destroyAllWindows()

```



## Output:

### Input Grayscale Image and Color Image:

![o1](https://user-images.githubusercontent.com/94525786/230705828-e72fac26-43aa-4d1f-a6df-f0452b9d88c3.png)


### Histogram of Grayscale Image and any channel of Color Image:

![o2](https://user-images.githubusercontent.com/94525786/230705830-4fe999e9-7c3c-438b-87fc-046df59c5fc4.png)

![o3](https://user-images.githubusercontent.com/94525786/230705833-59486df0-8296-491a-b065-8ec546a2a6d2.png)



### Histogram Equalization of Grayscale Image:


![o4](https://user-images.githubusercontent.com/94525786/230705836-d961f181-51b3-4c68-87d0-aae116a76fd7.png)


## Result: 

Thus the histogram for finding the frequency of pixels in an image with pixel values ranging from 0 to 255 is obtained. Also,histogram equalization is done for the gray scale image using OpenCV.


