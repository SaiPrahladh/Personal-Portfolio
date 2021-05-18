---
title: Real time Eye/Gaze Tracking.
summary: Real time Eye/Gaze tracking is a process which is really useful in the field of medical science and has proven to be the only method to objectively and accurately record and analyse visual behaviour. This use case is designed as a part of a larger medical subsystem catered towards improving the quality of life of Huntington's disease patients. This eye tracking implementation enables us to quantify the range of voluntary eye movement of HD patients through Occular Pursuit exercises. This implementation leverages the vast capabilities of the OpenCV library.
tags:
- Computer Vision
date: "2016-04-27T00:00:00Z"

# Optional external URL for project (replaces project detail page).
external_link: ""

image:
  caption: Photo by immersed.io contributors
  focal_point: Smart

links:
# - icon: twitter
#  icon_pack: fab
#  name: Follow
#  url: https://twitter.com/georgecushen
url_code: "https://github.com/SaiPrahladh/Eye_tracking"
url_pdf: ""
url_slides: ""
url_video: "https://drive.google.com/file/d/15fTBYAUQUwgOJLGPpowxUFlVlh8FshTx/view?usp=sharing"

# Slides (optional).
#   Associate this project with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
# slides: example
---
**MOTIVATION:**

Huntington's disease(HD) is an autosomal dominant genetic disorder. Symptoms generally start to appear in patients’ middle age, and death usually occurs 15 to 20 years after onset. The clinical symptoms of Huntington's disease are complex and varied including motor, cognitive and psychiatric symptoms. The main characteristics of this disease are dance - like movements accompanied by progressive cognition, mental dysfunction and eventually dementia. One such area of degeneration is in the eye muscles, where, as the diseases progresses, the patients are not able to maintain the same range of eye movement as a normal person. This is where the eye tracking implementation comes into play. Ocular pursuit is one of the prominent exercises used to observe this reduction in the range of eye movement. The eye tracking algorithm will log the coordinates of the left and the right pupil throughout the duration of the exercise and then calculate the horizontal and vertical range of the patient's eye movement. The logging of these ranges will allow us to quantify this degeneration and helps us maintain a medical history.

This project leverages the capabilities of OpenCV to identify the coordinates of pupils in each frame of the video. Additionaly, the facial features are detected using the facial landmarks detector present in 'dlib' library.

**HOW IS THE TRACKING PERFORMED?**
1. The first step is to detect the face in the video frame using the 'get_frontal_face_detector' feature from the dlib library.
2. The predictor is initialized using the pretrained 68 keypoints facial feature detector.
3. Obtain video frames from a webcam and perform the tracking operation frame by frame.
4. Perform preprocessing steps as mentioned in the comments of the code and obtain a masked and thresholded image.
5. Obtain the coordinates of the pupils and contour the thresholded image to highlight the pupils in each frame.
6. Append these coordinates to obtain a list of coordinates of the left and the right pupil.
7. Calculate the range of horizontal and vertical motion for both the eyes.
8. (Optional) Push these ranges onto an MQTT database.

Check out the working demo linked through the video button!

