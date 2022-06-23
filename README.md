## EX.NO :  02

## DATE: 

# <p align="center"> Image-Acquisition-from-Web-Camera </p> 

## Aim
 
Aim:
 
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.
i) Write the frame as JPG 
ii) Display the video 
iii) Display the video by resizing the window
iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7
## Algorithm
### Step 1:

Import cv2 and capture the video using cv2.VideoCapture(0)

### Step 2:

Write the captured image using cv2.imwrite("JayashreeRao.jpg",frame)

### Step 3:

Resize the image using cv2.resize(frame, (0,0), fx = 0.5, fy=0.5)

### Step 4:

Display the image until the loop gets over

### Step 5:

Rotate the image using cv2.rotate(smaller_frame,cv2.cv2.ROTATE_180)

## Program:

### Developed By: PRIYADARSHINI R
### Register No: 212220230038

## i) Write the frame as JPG file
``` Python3
import cv2

videoCaptureObject = cv2.VideoCapture(0)
ret,frame = videoCaptureObject.read()
cv2.imwrite("photo1.jpg",frame)


```

## ii) Display the video
```python3
import cv2
import numpy as np

cap = cv2.VideoCapture(0)

while True:
    ret, frame = cap.read()

    cv2.imshow("photo1",frame)
    if cv2.waitKey(1) & 0xFF == ord('q'):
        break
videoCaptureObject.release()
cv2.destroyAllWindows()

```



## iii) Display the video by resizing the window
```python3
import cv2
import numpy as np

cap = cv2.VideoCapture(0)

while True:
    ret, frame = cap.read()
    width = int(cap.get(3))
    height = int(cap.get(4))
    
    image = np.zeros(frame.shape, np.uint8)
    smaller_frame = cv2.resize(frame, (0,0), fx = 0.5, fy=0.5)
    image[:height//2, :width//2] = smaller_frame
    image[height//2:, :width//2] = smaller_frame
    image[:height//2, width//2:] = smaller_frame
    image[height//2:, width//2:] = smaller_frame

    image[:height//2, :width//2] = cv2.rotate(smaller_frame,cv2.cv2.ROTATE_180)
    cv2.imshow("photo1.jpg",image)
    if cv2.waitKey(1) & 0xFF == ord('q'):
        break
videoCaptureObject.release()
cv2.destroyAllWindows()





```
## iv) Rotate and display the video
```python
import cv2
import numpy as np
cap = cv2.VideoCapture(0)

while True:
    ret, frame = cap.read()
    width = int(cap.get(3))
    height = int(cap.get(4))
    
    image = np.zeros(frame.shape, np.uint8)
    smaller_frame = cv2.resize(frame, (0,0), fx = 0.5, fy=0.5)
    image[:height//2, :width//2] = smaller_frame

    image[:height//2, :width//2] = cv2.rotate(smaller_frame,cv2.cv2.ROTATE_180)

    cv2.imshow("image.jpg",image)
    if cv2.waitKey(1) & 0xFF == ord('q'):
        break
videoCaptureObject.release()
cv2.destroyAllWindows()

```
## Output

### i) Write the frame as JPG image
![P1](https://user-images.githubusercontent.com/81132849/162459297-807091a3-89ad-4018-92d7-1e4eec9c1ff5.png)




### ii) Display the video
![P2](https://user-images.githubusercontent.com/81132849/162459379-69a6bcb7-485e-44be-98b5-713582563b27.png)





### iii) Display the video by resizing the window
![P3](https://user-images.githubusercontent.com/81132849/162459451-a9a19b40-e954-4a58-9b16-19132f69c3e4.png)



### iv) Rotate and display the video
![P4](https://user-images.githubusercontent.com/81132849/162459505-09588b19-9375-4060-987a-373363701f7a.png)








## Result:
Thus the image is accessed from webcamera and displayed using openCV.
