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
import cv2 and capture the video using cv2.VideoCapture(0)

### Step 2:
Write the captured image using cv2.imwrite("Arun.jpg",frame)

### Step 3:
Resize the image using cv2.resize(frame,(0,0),fx = 0.5,fy=0.5)

### Step 4:
Display the image untill the loop gets over

### Step 5:
Rotate the image using cv2.rotate(smaller_frame,cv2.cv2.ROTATE_180)

## Program:
``` Python
### Developed By: R ARUNRAJ
### Register No:212220230004

## i) Write the frame as JPG file
 import cv2

videoCaptureObject = cv2.VideoCapture(0)

ret,frame = videoCaptureObject.read()
cv2.imwrite("NewPicture.jpg",frame)

videoCaptureObject.release()
cv2.destroyAllWindows()



## ii) Display the video
import cv2
import numpy as np

cap = cv2.VideoCapture(0)


while True:
    ret, frame = cap.read()

    cv2.imshow("NewPicture",frame)
    if cv2.waitKey(1) & 0xFF == ord('q'):
        break

videoCaptureObject.release()
cv2.destroyAllWindows()



## iii) Display the video by resizing the window
    import cv2
    import numpy as np
    cap=cv2.VideoCapture(0)
    while True:
        ret,frame=cap.read()
        width=int(cap.get(3))
        height=int(cap.get(4))
        image=np.zeros(frame.shape,np.uint8)
        smaller_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
        image[:height//2,:width//2]=smaller_frame
        image[height//2: , :width//2]=smaller_frame
        image[:height//2,width//2:]=smaller_frame
        image[height//2:,width//2:]=smaller_frame
        cv2.imshow('frame',image)
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
         image=np.zeros(frame.shape,np.uint8)
         smaller_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
         image[:height//2,:width//2]=cv2.rotate(smaller_frame,cv2.cv2.ROTATE_180)
         image[height//2: , :width//2]=smaller_frame
         image[:height//2,width//2:]=cv2.rotate(smaller_frame,cv2.cv2.ROTATE_180)
         image[height//2:,width//2:]=smaller_frame
         cv2.imshow('frame',image)
         if cv2.waitKey(1)==ord('q'):
             break
     cap.release()
     cv2.destroyAllWindows()






```
## Output

### i) Write the frame as JPG image
![sus](https://user-images.githubusercontent.com/75235759/163108732-8b3ff635-43c4-464f-b164-af0226f2d1a5.jpg)




### ii) Display the video

![Screenshot (38)](https://user-images.githubusercontent.com/75235759/163108896-464cae90-41ff-464c-b317-24730ae44c05.png)



### iii) Rotate and display the video
![Screenshot (38)](https://user-images.githubusercontent.com/75235759/163109025-6f427f07-7a29-49a9-b319-f5051d181c9a.png)



## Result:
Thus the image is accessed from webcamera and displayed using openCV.
