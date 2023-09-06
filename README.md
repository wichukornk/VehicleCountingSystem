# Multi-Class Vehicle Counting System for Multi-View Traffic Videos

## Project Description
Large cities have significant challenges with traffic management. Data on 
vehicle density will assist authorities in managing traffic, such as planning the 
proper time to turn on and off traffic signals based on the amount of vehicle 
density, etc. Currently, we estimate the number of vehicles using humans. 
However, due to delays and inaccuracies, this method is unsuitable for traffic 
control. This research presents a vehicle classification and counting system from 
traffic video. The system consists of object detection and object tracking. From 
testing, it was found that YOLOX performs better than YOLOv3 by 26.80% for side 
view dataset and 8.34% for top view dataset because YOLOX has a network head 
separated into box classification and box regression, which contributes to an 
increased detection and classification accuracy, and ByteTrack outperform centroid 
method for object tracking, due to the ability to handle occlusion by predicting the 
coordinates of objects that have disappeared using kalman filter, the system can 
continue tracking the object once the occlusion is over. The research findings lead 
to the conclusion that the vehicle counting system will benefit from the 
synergy between YOLOX and ByteTrack with region of interest which error from 
system is 16.67% for side view video and 23.40% for top view video. The system 
can be used to monitor the traffic for intelligent transportation system

## Image dataset
OpenImage dataset was downloaded by [OIDv4_toolkit](https://github.com/EscVM/OIDv4_ToolKit)
All bbox were labeled by Roboflow platform to 6 classes (Bus Car Motorcycle Pickup Truck Van)
- [OpenImage](https://drive.google.com/file/d/1VvSpeAeW_1VVo9lw5atmMKuLcFyFWDIa/view?usp=sharing)
- [SideView](https://drive.google.com/file/d/1WUV0sQz7cU9-iEU7Bt5ZpKgz-wrSg4ab/view?usp=sharing)
- [TopView](https://drive.google.com/file/d/1ckQwe9w8neZyAFcdNxgtWwWfo-RiNlA6/view?usp=sharing)

## Model
Detector was trained on mmDection with following parameter
- optimizer is SGD
- learning rate is 0.0025
- samples per gpu is 8
### Download
- [YOLOX-X-OpenImage](https://drive.google.com/file/d/1iyX9a9jYXBLf5ZN8UeN5F-NTD6OVcdKH/view?usp=sharing)
- [YOLOX-X-OpenImage+SideView-epoch-84](https://drive.google.com/file/d/1imimaO5LPmcw-t2NkW5W7CYrFDsVgXAb/view?usp=sharing)
- [YOLOX-X-TopView-epoch-108](https://drive.google.com/file/d/1LvYMqdvwnVhmwUvOXAIwu1HfuRn-8gA-/view?usp=sharing)

## Installation
All code use the following libraries or download [this-share-folder](https://drive.google.com/drive/folders/1XJ-6RUWl4rPU96z2U5ZTCsw0xYP2lRUL?usp=sharing) for installation
```
mmcv==1.7.1
mmdet==2.28.1
torch==1.9.0+cu111
torchvision==0.10.0+cu111
```