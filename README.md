# AutonomusDroneHandGesture

This is a sample program which allows users to control an Airsim drone using hand gestures.


This repository contains the following contents:

- Sample program
- Airsim gesture control interface
- Hand sign recognition model(TFLite)
- Finger gesture recognition model(TFLite)
- Learning data for hand sign recognition and notebook for learning
- Learning data for finger gesture recognition and notebook for learning

# Demo

Here's how to run the sample program

```
gesture_contoller.py
```

When your webcam is turned on, you can use gesture to control the Airsim Drone

# Directory

```
│  gesture_controller.py
│  airsim_controller.py
│  KeyController.py
│  keypoint_classification.ipynb
│  keypoint_classification_EN.ipynb
│  point_history_classification.ipynb
│  requirements.txt
│  app.py
│
├─model
│  ├─keypoint_classifier
│  │  │  keypoint.csv
│  │  │  keypoint_classifier.hdf5
│  │  │  keypoint_classifier.py
│  │  │  keypoint_classifier.tflite
│  │  └─ keypoint_classifier_label.csv
│  │          
│  └─point_history_classifier
│      │  point_history.csv
│      │  point_history_classifier.hdf5
│      │  point_history_classifier.py
│      │  point_history_classifier.tflite
│      └─ point_history_classifier_label.csv
│          
├─utils
│   └─cvfpscalc.py
│
└─airsim_functions
    └─orbit.py


```

# Gestures
For the keypoint classifier

0 Stop

![image](https://user-images.githubusercontent.com/109940604/219559497-2cf1d8ad-8b45-4602-bb27-6a39ecead540.png)

1 Up

![image](https://user-images.githubusercontent.com/109940604/219559556-12659836-c8a7-4bcb-a84a-4cb4f5f8a6f4.png)

2 Down

![image](https://user-images.githubusercontent.com/109940604/219559582-89c12205-4659-495a-a8e9-5d81cb1a2252.png)

3 Left

![image](https://user-images.githubusercontent.com/109940604/219559602-1a8342f9-8300-453d-ab0c-78770571630b.png)

4 Right

![image](https://user-images.githubusercontent.com/109940604/219559614-05ff4994-144d-4a4b-a256-0b5bb9100b41.png)

5 Front

![image](https://user-images.githubusercontent.com/109940604/219559637-4ec9da42-053b-49ae-a614-d14ae2325f61.png)

6 Back

![image](https://user-images.githubusercontent.com/109940604/219559664-576c6414-9db7-44ff-a89e-513f0c061bdb.png)

7 Pointer (For turning clockwise and anticlockwise)

![image](https://user-images.githubusercontent.com/109940604/219559672-88a319d8-f091-44da-8d9e-b0995dca3e2d.png)

For the point history classifier

0 Turning clockwise

![ezgif com-video-to-gif](https://user-images.githubusercontent.com/109940604/219562062-3ab7f4b8-7306-42b2-808c-b9466c801fb9.gif)

1 Turning anticlockwise

![ezgif com-video-to-gif (1)](https://user-images.githubusercontent.com/109940604/219562808-16e95ed7-caeb-4bc1-9cfb-3d7c71a020c7.gif)

# Airsim

Documentation
```
https://microsoft.github.io/AirSim/
```

Assets
```
https://github.com/microsoft/AirSim/releases
```

# Model training

To record new keypoint gesture run app.py
- Press K key to enter gesture recording mode
- Press number key (0 ~ 9) to record the coordinates of hand.
- In the keypoint.csv the first column is the label, which is the number you pressed.
- Subsequent column is the coordinates, an array flattened to single row, of keypoints.

To record new point history gesture run app.py
- Press H key to enter gesture recording mode
- Press number key (0 ~ 9) to record the history of your point right now and 15 frames before.
- In the point_history.csv the first column is the label, which is the number you pressed.
- Subsequent column is the coordinates, an array flattened to single row, of the history of the point that you are tracking.

More info could be found on
https://github.com/kinivi/hand-gesture-recognition-mediapipe
