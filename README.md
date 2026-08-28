# EXP 7 - Lane Detection

# Name: Ramnithish R
# Register No: 212224230219

##  Aim

To implement a basic lane detection pipeline using OpenCV by completing missing code segments at specified locations.


##  Software Used

* Anaconda – Python 3.7
* Jupyter Notebook / VS Code
* OpenCV (cv2)
* NumPy
* Matplotlib

---

##  Algorithm 
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
## Program 

### Input image and grayscale image
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread('Tiger.jpg')  # Replace with your image path
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title('Input Image')
plt.axis('off')
```

```
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
plt.imshow(gray_image, cmap='gray')
plt.title('Grayscale Image')
plt.axis('off')

```

### Canny Edge detector output
```
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
plt.imshow(gray_image, cmap='gray')
plt.title('Grayscale Image')
plt.axis('off')
```



### Display the result of Hough transform
```
lines = cv2.HoughLinesP(edges, rho=1, theta=np.pi/180, threshold=100, minLineLength=50, maxLineGap=10)
output_image = image.copy()

if lines is not None:
    for line in lines:
        x1, y1, x2, y2 = line[0]
        cv2.line(output_image, (x1, y1), (x2, y2), (0, 255, 0), 2)
plt.imshow(cv2.cvtColor(output_image, cv2.COLOR_BGR2RGB))
plt.title('Hough Transform - Line Detection')
plt.axis('off')

```

# Output
<img width="1083" height="352" alt="image" src="https://github.com/user-attachments/assets/55b80057-76ed-4e5b-a0ae-9e4c2ff3f001" /><br>
<img width="1022" height="362" alt="image" src="https://github.com/user-attachments/assets/7feb6a72-a718-4bc7-b826-7cee8dff7cfe" /><br>
<img width="1038" height="358" alt="image" src="https://github.com/user-attachments/assets/ddec7dbc-03ad-4f1e-8ae9-517f4b9c4d54" /><br>
<img width="1092" height="362" alt="image" src="https://github.com/user-attachments/assets/b5aaed02-d504-4cb0-8406-24e81322004a" />




## Result

Thus, the lane detection pipeline is successfully implemented by completing the missing code sections. The system detects and highlights lane lines effectively.



