#License Plate and Car Detection using TensorFlow v1 (MobileNet SSD)

##Selection of Framework
TensorFlow is used here instead of PyTorch or other frameworks as I am more familiar with TensorFlow. However, picking up PyTorch shouldn't be a problem.

##Selection of TensorFlow version
TensorFlow 1 is used here for the following reasons:
- Roboflow has a fantastic tutorial on using MobileNet v2 SSD on object detection

##Selection of platform
Google Colab is used here as I do not have a GPU enabled machine.

##Selection of Model
Model selected: **MobileNet v2 SSD**
- MobileNet v2 SSD is selected as it goes inline with what I have learnt about object detection models like YOLO, SSD and Faster R-CNN. Among these, SSD on MobileNet v2 is efficient enough to be run on mobile devices and be accurate at the same time. However, in this notebook, the metrics are not exactly satisfactory. I have listed several things I could do to enhance the performance of the model, which also explain why the model is not performing great.

##Dataset
Custom dataset from Roboflow here
The dataset consists of:
    - 245 training images
    - 70 validation images
    - 35 test images

All images are annotated with two classes:
    - vehicle
    - license_plate
    
##Test video
One of the test video is a personal video on license plate and cars, hence it won't be uploaded for public use.
However, the other test video used is a video from YouTube that can be found here

##Task Accomplishment and Performance of Model
The trained model was tested on 2 test videos. The first test video is a test of video of my own and the second one is a trimmed video from the given video link. Due to limitations in Google Colab, I could only manage to run inference for a limited amount of time, hence the test videos are kept as short as possible.
In general, the license plate object detection task achieved a fairly good performance, with a lot more room to improve.
However, the license plate recognition is subpar due to lack of image processing after extraction of the ROI from the bounding boxes. With that acknowledged, image processing techniques can be employed to improve the recognition task. This should reduce the number of false recognition in the .txt file.
  - Average precision: 0.323
  - Average recall: 0.345
  - Mean average precision (mAP): 0.3227

##Future work
    - Number of epochs could be increased to increase precision, recall and mAP.
    - Number of images in the dataset could be increased:
        - by finding bigger and better datasets
        - by performing augmentation (can only augment a limited number of images before the model still overfits)
    - An attempt on using other detection algorithms like EfficientDet could be explored.
