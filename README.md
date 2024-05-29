# Grasping Point Calculation for Desired Object among Multiple Objects

Worked with a team to compare different **Instance Segmentation** approaches, **Training** on Benchmark Datasets, and visualizing the differences in their results. 

## Abstract
This project presents a cutting-edge methodology for Grasping Point Calculation for Desired Object among Multiple Objects, employing a hybrid model that combines the robust capabilities of Mask R-CNN with a ResNet50 and FPN backbone, in conjunction with YOLOv8 for object detection and segmentation. By synergizing the unique strengths of these models, the system adeptly identifies and isolates objects within a scene, facilitating the precise determination of the optimal grasping point for a specified object amidst a multitude of objects.
## Problem Statement
The primary challenge addressed in this report is the accurate calculation of grasping points for a desired object among multiple objects in a given scene. To overcome this challenge, this research proposes a hybrid model that combines the strengths of Mask R-CNN with a ResNet50 and FPN backbone, along with YOLOv8, for object detection and segmentation. By integrating these state-of-the-art models, the system aims to enhance object recognition and localization, enabling more accurate grasping point calculation for the desired object amidst multiple objects.
## Objectives
#### 1. To develop a robust and accurate hybrid model for object detection and segmentation, leveraging Mask R-CNN with a ResNet50 and FPN backbone, and YOLOv8.
#### 2. To integrate the outputs of Mask R-CNN and YOLOv8 to precisely identify and isolate the desired object within a scene containing multiple objects.
#### 3. To calculate the optimal grasping point for the identified desired object, ensuring efficient and reliable robotic manipulation in complex environments.
#### 4. To evaluate the performance of the proposed hybrid model and compare it with existing approaches, demonstrating its superiority in terms of accuracy, speed, and robustness.

# MaskRCNN
The Mask R-CNN model employs a robust methodology that combines feature extraction, region proposal generation, ROI alignment, classification, bounding box regression, and mask prediction to achieve accurate instance segmentation. The process begins with feature extraction using a pre-trained backbone network, such as ResNet50 with FPN, which captures hierarchical features at different scales from input images. These features are crucial for detecting objects and segmenting them precisely.
Next, the Region Proposal Network (RPN) generates region proposals by predicting bounding boxes around potential objects. The RPN utilizes anchor boxes of various aspect ratios and scales to propose regions of interest, enabling the model to detect objects at different sizes and aspect ratios. The proposed regions are then refined based on objectness scores and bounding box regressions, ensuring that only the most promising regions are considered for further processing.
To extract features from the proposed regions with high spatial accuracy, Mask R-CNN employs ROI Align. This operation preserves pixel-level details during feature extraction, enhancing the model's segmentation performance. The extracted features are then fed into classification and bounding box regression heads. The classification head predicts the object class probabilities, while the regression head refines the bounding box coordinates for accurate object localization.
The mask head network in Mask R-CNN is responsible for generating pixel-wise masks for each detected object. This branch produces segmentation masks by predicting the presence of an object at each pixel location, enabling precise instance segmentation. The mask prediction is performed in parallel with classification and bounding box regression, making the model efficient and flexible.


![image](https://github.com/LokuKakkar/Robotic-Grasping-with-Instance-Segmentation/assets/98534834/6f026994-c998-42de-89d9-3c156b476c4e)


# YOLOv8
YOLOv8 is the latest version of the YOLO object detection model, developed by Ultralytics. It is an anchor-free model, which means that it does not use pre-defined anchor boxes to predict object boundaries. Instead, it directly predicts the center of each object and its width and height. This makes YOLOv8 more flexible and accurate than previous versions of YOLO, which were limited by the use of anchor boxes. 
YOLOv8 is also faster than previous versions of YOLO. It can achieve real-time object detection on a single GPU, making it suitable for a wide range of applications, such as autonomous driving, video surveillance, and robotics.

![image](https://github.com/LokuKakkar/Robotic-Grasping-with-Instance-Segmentation/assets/98534834/083c8dd5-01f9-4300-bb7a-86981d28ded4)

Here are some of the key features of YOLOv8: 
• Anchor-free object detection 
• Real-time performance on a single GPU 
• High accuracy 
• Open-source under the Apache 2.0 license

# Experimental Results
Mask RCNN Model: 

![image](https://github.com/LokuKakkar/Robotic-Grasping-with-Instance-Segmentation/assets/98534834/dc9653df-2b37-4113-b4ca-dd8eb8cc75a5)
![image](https://github.com/LokuKakkar/Robotic-Grasping-with-Instance-Segmentation/assets/98534834/3f5c320d-8538-4c3a-af30-7360ae3d4467)

YOLOv8 model:

![image](https://github.com/LokuKakkar/Robotic-Grasping-with-Instance-Segmentation/assets/98534834/9ac20c85-87fa-4d2a-bee8-50381844372c)
![image](https://github.com/LokuKakkar/Robotic-Grasping-with-Instance-Segmentation/assets/98534834/86881575-c85f-46b3-b827-96f08c34d367)


![image](https://github.com/LokuKakkar/Robotic-Grasping-with-Instance-Segmentation/assets/98534834/f8a965a3-95c6-49f4-9344-07e236c70f72)
![image](https://github.com/LokuKakkar/Robotic-Grasping-with-Instance-Segmentation/assets/98534834/c08d04f0-6d39-4d8d-bb80-b27740b993e1)

# Long term Vision
### Using YOLOv8 for Next phase
Optimal balance between speed and accuracy.
Suitable for real-time applications.
Easier integration and maintenance.

### Integration with Grasping Algorithm
Leverage YOLOv8's bounding box outputs to identify object locations.
Apply a grasping point calculation algorithm to these locations.

### Expected Outcomes
Efficient and accurate detection of grasping points.
Improved performance in real-time applications.
Enhanced reliability in diverse object environments.
