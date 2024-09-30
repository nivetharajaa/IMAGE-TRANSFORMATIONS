# IMAGE-TRANSFORMATIONS


## Aim
To perform image transformation such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping using OpenCV and Python.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Import the necessary libraries and read the original image and save it as a image variable.

### Step2:
Translate the image using a function warpPerpective()

### Step3:
Scale the image by multiplying the rows and columns with a float value.

### Step4:
Shear the image in both the rows and columns.

### Step5:
Find the reflection of the image.

## Program:
Developed By:Nivetha A
Register Number:212222230101

### i) Original Image:
```
import numpy as np
import cv2
import matplotlib.pyplot as plt
input_img = cv2.imread("rapunzel.jpg")
# cv2.imshow("image webp",input_img)
input_img = cv2.cvtColor(input_img, cv2.COLOR_BGR2RGB)
plt.axis('off')
plt.imshow(input_img)
plt.show()
```
### ii)Image Translation
```
rows,cols,dim=input_img.shape
M=np.float32([[1,0,50],  [0,1,100],  [0,0,1]])
translated_image=cv2.warpPerspective(input_img,M,(cols,rows))
plt.axis('off')
plt.imshow(translated_image)
plt.show()
```

### iii) Image Scaling
```
scale_factor = 1.5
M_scale = np.float32([[scale_factor, 0, 0],
                      [0, scale_factor, 0],
                      [0, 0, 1]])

scaled_img = cv2.warpAffine(input_img, M[:2], (int(cols*scale_factor), int(rows*scale_factor)))
plt.axis('off')
plt.imshow(scaled_img)
plt.show()
```

### iv)Image shearing
```
M_x = np.float32([[1, 0.2, 0],
                  [0, 1, 0],
                  [0, 0, 1]])

sheared_img_xaxis = cv2.warpAffine(input_img, M_x[:2], (cols, rows))
plt.axis('off')
plt.imshow(sheared_img_xaxis)
plt.show()
M_y = np.float32([[1, 0, 0],
                  [0.2, 1, 0],
                  [0, 0, 1]])

sheared_img_yaxis = cv2.warpAffine(input_img, M_y[:2], (cols, rows))
plt.axis('off')
plt.imshow(sheared_img_yaxis)
plt.show()
```

### v)Image Reflection
```
M_x = np.float32([[-1, 0, cols],
                  [0, 1, 0],
                  [0, 0, 1]])

reflected_img_xaxis = cv2.warpAffine(input_img, M_x[:2], (cols, rows))

plt.axis("off")
plt.imshow(reflected_img_xaxis)
plt.show()

M_y = np.float32([[1, 0, 0],
                  [0, -1, rows],
                  [0, 0, 1]])

reflected_img_yaxis = cv2.warpAffine(input_img, M_y[:2], (cols, rows))

plt.axis("off")
plt.imshow(reflected_img_yaxis)
plt.show()
```

vi)Image Rotation
```
angle = np.radians(-60)
M = np.float32([[np.cos(angle), -np.sin(angle), 0],
                [np.sin(angle), np.cos(angle), 0]])
center = (cols // 2, rows // 2)
M = cv2.getRotationMatrix2D(center, -60, 1.0)
rotated_img = cv2.warpAffine(input_img, M, (cols, rows))

plt.axis('off')
plt.imshow(rotated_img)
plt.show()
```


vii)Image Cropping
```
cropped_img = input_img[50:200, 200:400]
plt.axis('off')
plt.imshow(cropped_img)
plt.show()



```
## Output:
 ### i)Original Image:
 
 ![image](https://github.com/user-attachments/assets/d927a8bc-bc4e-4cd8-9295-81c421df5f00)


### ii)Image Translation

![image](https://github.com/user-attachments/assets/0a768d79-e360-4ae2-aadc-8776b46fb12d)


### iii) Image Scaling

![image](https://github.com/user-attachments/assets/9228b9dc-d910-42fb-a308-29d9551c6c22)



### iv)Image shearing

![image](https://github.com/user-attachments/assets/9d50f34f-b9a5-486f-89a2-80784503e9dd)

![image](https://github.com/user-attachments/assets/4ce2ae82-ee79-42de-936c-f7b0d9de6859)


### v)Image Reflection

![image](https://github.com/user-attachments/assets/b3873b8b-0de7-4c62-93e5-45bbfe4dad41)

![image](https://github.com/user-attachments/assets/f5725ffe-c30f-411f-afda-b4dd2c67c6bf)

### vi)Image Rotation

![image](https://github.com/user-attachments/assets/56fadc42-d5b4-4303-8b3f-f654efd4dd60)

### vii)Image Cropping

![image](https://github.com/user-attachments/assets/e57689a0-27d3-4741-9c2e-e492798f815a)

## Result: 

Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.
