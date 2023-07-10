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
All bbox were labeled by Roboflow platform
- [OpenImage](https://drive.google.com/drive/folders/1aHI5zM4O4-kioMd2sqFKfQ52K-YxaJ82?usp=sharing)
- [SideView](https://drive.google.com/drive/folders/1uZwRIjzAzH3nWKIeyTnNgtMyBNPCsS0l?usp=sharing)
- [TopView](https://drive.google.com/drive/folders/1j3ubao87gRmH0-f15GpU5udjAqRvGZxP?usp=drive_link)

## Checkpoint
Detector was trained on mmDection framework
- [YOLOX-X-OpenImage-SideView-epoch-84](https://drive.google.com/file/d/102fdWTTE9yEebbpxRWq4T7IfCs3wz-Ga/view?usp=drive_link)
- [YOLOX-X-TopView-epoch-108](https://drive.google.com/file/d/107jsOQaMFDIgzhwYijcTEEzJzY4f4VIZ/view?usp=drive_link)