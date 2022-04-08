# Image-Acquisition-from-Web-Camera
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
cv2.imwrite("image.jpg",frame)


```

## ii) Display the video
```python3
import cv2
import numpy as np

cap = cv2.VideoCapture(0)

while True:
    ret, frame = cap.read()

    cv2.imshow("image1",frame)
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
    cv2.imshow("image.jpg",image)
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
![O1](https://user-images.githubusercontent.com/81132849/162367993-0d39d342-3913-4c62-90d1-49b0bfffb2f4.png)



### ii) Display the video
![O2](https://user-images.githubusercontent.com/81132849/162368028-2cc9a033-1bcf-4f0d-ab08-ed68c9262199.png)





### iii) Display the video by resizing the window
![O3](https://user-images.githubusercontent.com/81132849/162368096-dd14572b-7f63-41d9-8d5d-3829236eb7b6.png)




### iv) Rotate and display the video
![O4](https://user-images.githubusercontent.com/81132849/162368463-feacf926-f404-4c21-bb42-d5b46d7845e3.png)








## Result:
Thus the image is accessed from webcamera and displayed using openCV.
