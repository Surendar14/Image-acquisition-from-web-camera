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

Use VideoCapture(0) to access web camera.
### Step 2:

Use imread to read the video or image.
### Step 3:

Use imshow to show the video.
### Step 4:

Use imshow to show the video.
### Step 5:

End the program and close the output video windows by pressing 'q'.
## Program:
``` Python
### Developed By: Surendar S
### Register No:212220230051

## i) Write the frame as JPG file
import cv2
videoCaptureObject = cv2.VideoCapture(0)
while(True):
    ret,frame = videoCaptureObject.read()
    cv2.imshow("apple.jpg",frame)
    result = False
videoCaptureObject.release()
cv2.destroyAllWindows()



## ii) Display the video
import cv2
import numpy as np
cap = cv2.VideoCapture(0)
while True:
    ret,frame = cap.read()
    cv2.imshow('frame', frame)
    if cv2.waitKey(1) == ord('q'):
        break
cap.release()
cv2.destroyAllWindows()



## iii) Display the video by resizing the window
import cv2
import numpy as np
cap=cv2.VideoCapture(0)

while True:
    ret,frame=cap.read()
    width=int(cap.get(3))
    height=int(cap.get(4))
    
    image=np.zeros(frame.shape, np.uint8)
    smaller_frame=cv2.resize(frame, (0,0), fx=0.5, fy=0.5)
    image[:height//2, :width//2]=smaller_frame
    image[height//2:, :width//2]=smaller_frame
    image[:height//2, width//2:]=smaller_frame
    image[height//2:, width//2:]=smaller_frame
    
    cv2.imshow('frame', image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()




## iv) Rotate and display the video
import cv2
import numpy as np
cap=cv2.VideoCapture(0)

while True:
    ret,frame=cap.read()
    width=int(cap.get(3))
    height=int(cap.get(4))
    
    image=np.zeros(frame.shape, np.uint8)
    smaller_frame=cv2.resize(frame, (0,0), fx=0.5, fy=0.5)
    image[:height//2, :width//2]=smaller_frame
    image[height//2:, :width//2]=smaller_frame
    image[:height//2, width//2:]=smaller_frame
    image[height//2:, width//2:]=smaller_frame
    
    cv2.imshow('frame', image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()



```
## Output

### i) Write the frame as JPG image
![Screenshot (31)](https://user-images.githubusercontent.com/75235759/163106920-32f6e7f2-8373-4486-bf4b-e531036081af.png)


### ii) Display the video

![Screenshot (34)](https://user-images.githubusercontent.com/75235759/163107014-b8185b9f-61b0-4bdc-b402-d8f6e6276ffb.png)

### iii) Display the video by resizing the window

![Screenshot (35)](https://user-images.githubusercontent.com/75235759/163107034-e8a2536a-eae8-473b-9387-056757e57741.png)

### iv) Rotate and display the video
![Screenshot (36)](https://user-images.githubusercontent.com/75235759/163107049-aa606f7c-2e33-4915-a416-f886083a3432.png)





## Result:
Thus the image is accessed from webcamera and displayed using openCV.
