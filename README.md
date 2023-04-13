# Image-Acquisition-from-Web-Camera
## AIM
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.
i) Write the frame as JPG 
ii) Display the video 
iii) Display the video by resizing the window
iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7
## ALGORITHM 
Step 1:
Use VideoCapture(0) to access web camera<br>
Step 2:
Use imread to read the video or image<br>
Step 3:
Use imwrite to save the image<br>
Step 4:
Use imshow to show the video<br>
Step 5:
End the program and close the output video windows by pressing 'q'.

## Program:
## Developed By: Mohamed Fashroon Adhil I
### Register No: 212220230032

## i) Write the frame as JPG file
```python
    import cv2
    import numpy as np
    cap=cv2.VideoCapture(0)
    ret,frame=cap.read()
    cv2.imwrite("myself.jpg",frame)
    cap.release()
    cv2.destroyAllWindows()
```
## ii) Display the video
```python
    import cv2
    import numpy as np
    cap=cv2.VideoCapture(0)
    while True:
        ret,frame=cap.read()
        cv2.imshow('frame',frame)
        if cv2.waitKey(1)==ord('q'):
             break
    cap.release()
    cv2.destroyAllWindows()
```
## iii) Display the video by resizing the window
```python
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
         image[:height//2,width//2:]= smaller_frame
         image[height//2:,width//2:]=smaller_frame
         cv2.imshow('frame',image)
         if cv2.waitKey(1)==ord('q'):
             break
    cap.release()
    cv2.destroyAllWindows()
```
## iv) Rotate and display the video
```python
    import cv2
    import numpy as np
    cap=cv2.VideoCapture(0)
    while True:
        ret,frame=cap.read()
        width=int(cap.get(3))
        height=int(cap.get(4))
        image=np.zeros(frame.shape,np.uint8)
        smaller_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
        image[:height//2,:width//2]=image[:height//2, :width//2] = cv2.rotate(smaller_frame,cv2.cv2.ROTATE_180)
        image[height//2: , :width//2]=smaller_frame
        image[:height//2,width//2:]= image[:height//2, :width//2] = cv2.rotate(smaller_frame,cv2.cv2.ROTATE_180)
        image[height//2:,width//2:]=smaller_frame
        cv2.imshow('frame',image)
        if cv2.waitKey(1)==ord('q'):
            break
    cap.release()
    cv2.destroyAllWindows()
```
## Output
### i) Write the frame as JPG image
![1](https://user-images.githubusercontent.com/75235369/231701518-baf8243a-d607-466c-95bb-ddd9de72562e.png)

### ii) Display the video
![2](https://user-images.githubusercontent.com/75235369/231701544-5f1dc521-d81a-43b3-abca-cd674315f232.png)

### iii) Display the video by resizing the window

### iv) Rotate and display the video

## Result:
Thus the image is accessed from webcamera and displayed using openCV.
