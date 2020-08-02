# DRISHTI

DRISHTI non-invasive biometric system that captures face, expression and gesture of targeted persons (criminals) through a network of distributed  CCTV cameras and also maintains detailed log in a database.

## DRISTI has following sub-modules:
### 1. Face recognition

We are able to identify both known and unknown person in images as well as realtime video stream. 
### 2. Face Anti-spoofing

Most entry level Face recognition systems are susceptible to presentation attaks.
But our system can identify if the face visible in camera frame is reak or fake.
### 3. Emotion Recognition

We are able to detect following emotions from input video feed
[]
### 4. Age/Gender Detestion

Dreishti can dtetct both gender as well as perceivable age of person present in the video frame. We still need to impreove age detection accuray further, we are working on it. 
### 6. Action Recognition

Currently we are not looking into temporal information to recognise action being perfoermed. we are using simple neural network to classify the the skeletal data taken from OpenPose. 

We plan to accomodate temporal info by passing OpenPose output to recently opensourced View Adaptive Recurrent Neural Networks.

https://github.com/microsoft/View-Adaptive-Neural-Networks-for-Skeleton-based-Human-Action-Recognition/blob/master/README.md  

Actions beigng recognised are:
[Kick, punch, sit, squat, stand, wave, walk, jump, run]
### 7. Gait Recognition
### 8. Person-Weapon detection and Tracking
We are able to detect persons and weapons present in the video ferame using YOLOv3. The bounding box of each person is associated with his/her name using Face Frecognition module. These detections along with thier preper lables from both face Recognition and YOLO are paased to DeepSort Tracking.

So you can see that we can detect weapon present in the video frame and issue warning.

Aslo even if we could capture the face of suspect in any one frame we can track the person no matter howe hard he tries to hide his face. 
### 9. Server that aggregates ingormation from all the modules and updates GUI in real-time

In real time we plan that all these modules will run parallely and send the output to central server which then updates Dashboard GUI in realtime. 

Following is the screen-shot of the proposed GUI:

### Detaiks of each modules are further available in readme files of respective folderrs 


### Face Anti-spoofing


### Age Detection


### Gender Detestion


### Action Recognition


### Gait Recognition

### Person-Weapon detection and Tracking

### GUI

Whenever an activity is performed by a person, it usually lasts a few seconds. 
It is essential to look into temporal (time) variation of data to predict the activity class with desired accuracy.
Hence, we use OpenPose and a Convolutional Neural Network (CNN).

### Pose Estimation
Deep Learning Model: cmu (pretrained on COCO dataset) 
 Input: image (frame)
 Number of layers: 101
 Output: skeleton is marked on the image (Positions of skeletal joints)

### Tracking
It is used for tracking each person.
Euclidean distance between the joints of two skeletons is used for matching two skeletons.

### Classification
Classification into the various action types is performed with the help of neural network classifier.
 Output: probability of a particular action detected


## How to use

`python action_recognition.py`

