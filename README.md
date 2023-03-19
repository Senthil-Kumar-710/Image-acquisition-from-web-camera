# Image-Acquisition-from-Web-Camera
## Aim:
 
 
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.<br>
i) Write the frame as JPG. <br>
ii) Display the video. <br>
iii) Display the video by resizing the window. <br>
iv) Rotate and display the video. <br>

## Software Used:
Anaconda - Python 3.7
## Algorithm:
### Step 1:
Import cv2 and capture the video using cv2.VideoCapture(0).
<br>

### Step 2:
Write the captured image using cv2.imwrite("NewPicture.jpg",frame)
<br>

### Step 3:
Resize the image using cv2.resize() to get a four-split screen.
<br>

### Step 4:
Rotate the image using cv2.rotate(smaller_frame,cv2.cv2.ROTATE_180)
<br>

### Step 5:
Display the image until the key to close the window is pressed.
<br>

## Program:

### Developed By:Senthil Kumar S
### Register No:212221230091

## i) Write the frame as JPG file
```
obj = cv2.VideoCapture(0)
while(True):
    cap,frame = obj.read()
    cv2.imshow('video_image.jpg',frame)
    cv2.imwrite("out.jpg",frame)
    if cv2.waitKey(1) == ord('q'):
        break
obj.release()
cv2.destroyAllWindows()
```
## ii) Display the video
```
obj = cv2.VideoCapture(0)
while(True):
    cap,frame = obj.read()
    cv2.imshow('video_image',frame)
    if cv2.waitKey(1) == ord('q'):
        break
obj.release()
cv2.destroyAllWindows()
```
## iii) Display the video by resizing the window
```
obj = cv2.VideoCapture(0)
while True:
    cap, frame = obj.read()
    h = int(obj.get(4))
    w = int(obj.get(3))
    sm_frame = cv2.resize(frame, (0,0), fx=0.5 , fy=0.5)
    im = np.ones(frame.shape,np.uint8)*200
    im[125:(h//2)+125,135:(w//2)+135] = sm_frame
    cv2.imshow("Pic",im)
    if cv2.waitKey(1) == ord('q'):
        break
obj.release()
cv2.destroyAllWindows()
```
## iv) Rotate and display the video
```
obj = cv2.VideoCapture(0)
while True:
    cap, frame = obj.read()
    h = int(obj.get(4))
    w = int(obj.get(3))
    im = np.ones(frame.shape,np.uint8)*185
    sf = cv2.resize(frame, (0,0), fx=0.5 , fy=0.5)
     - #+/- 80
    im[75:(height//2)+155, 35:(width//2)-45] = cv2.rotate(sf,cv2.ROTATE_90_CLOCKWISE)
    im[:height//2, width//2:] = sf
    im[height//2:, width//2:] = cv2.rotate(sf,cv2.ROTATE_180)
    cv2.imshow("Pic",im)
    if cv2.waitKey(1) == ord('q'):
        break
obj.release()
cv2.destroyAllWindows()
```
## Output:

### i) Write the frame as JPG image;

![img1](https://user-images.githubusercontent.com/93860256/226188463-91f729ad-bbd1-4e2c-bb29-2ca55b6772eb.JPG)


### ii) Display the video

![img2](https://user-images.githubusercontent.com/93860256/226188475-d0e6055a-7e08-437d-a82e-a088d75016ed.JPG)


### iii) Display the video by resizing the window

![img3](https://user-images.githubusercontent.com/93860256/226188490-cda54132-2af8-470a-8241-d3b316ab9ce4.JPG)



### iv) Rotate and display the video

![img4](https://user-images.githubusercontent.com/93860256/226188686-94ae8ce6-e58d-4b13-90e7-e99c2f97bacc.JPG)


## Result:
Thus the image is accessed from webcamera and displayed using openCV.
