---
layout: post
title: YOLOv8 Fire and Smoke Detection
image: 
  path: https://cdn-images-1.medium.com/max/2000/1*HVm63Me_kPRNy0vxekCabw.gif
description: >
 Fine-Tune YOLOv8 Fire-and-Smoke-Detection on custom data
sitemap: false
---

  **Reading_time:** 6 min\
  **Tags:** [Yolov8, Fireandsmokedetection, Machine Learning, Computer Vision, AI]
- Table of Contents
{:toc .large-only}
**Table of Contents:**
- [Dataset](#dataset)
- [Model Training and Evaluation](#model-training-and-evaluation)
- [Inference](#Inference)
- [Application Area](#application-area)

| ![Media by Author - Live Fire and smoke detection and tracking using YOLOv8](https://cdn-images-1.medium.com/max/2000/1*HVm63Me_kPRNy0vxekCabw.gif) |
|:--:|
| <i>Image Credits - Media by Author - Live Fire and smoke detection and tracking using YOLOv8</i>|

Fire and smoke detection is a critical task for ensuring public safety and preventing property damage. With recent advances in computer vision and deep learning, it is possible to build accurate fire and smoke detection systems using custom datasets. One such system is YOLOv8, a state-of-the-art object detection model that can be trained on a custom dataset to detect fire and smoke.

This article will redirect you to the **[project](https://github.com/Abonia1/YOLOv8-Fire-and-Smoke-Detection)**.

**[This repository contains the code for tracking and detecting fires and smokes in real-time video using YOLOv8.](https://github.com/Abonia1/YOLOv8-Fire-and-Smoke-Detection)**

## YOLOv8

**[Ultralytics YOLOv8](https://github.com/ultralytics/ultralytics)**, developed by **[Ultralytics](https://ultralytics.com)**. YOLOv8 stands for “You Only Look Once version 8” and it is an improvement over the previous YOLO models. It is a single-shot object detection model that can detect multiple objects in an image in real-time. Unlike other object detection models that divide the image into multiple regions and perform object detection on each region, YOLOv8 performs object detection on the entire image in one forward pass through the network. This makes it fast and efficient for real-time applications.

## Dataset

We have used image dataset from roboflow where it was annoted for to find Fire, smoke and default with boxes.

Link to Fire and Smoke detection ***[dataset](https://github.com/Abonia1/YOLOv8-Fire-and-Smoke-Detection/tree/main/datasets/fire-8).***

## Model Training and Evaluation

The process of training YOLOv8 on a custom dataset involves several steps. First, a dataset of images containing fire and smoke should be collected and annotated. This involves marking the regions of interest in each image that correspond to fire and smoke. The annotated images can then be split into a training set and a validation set for use in the training process.I have useed ***[roboflow](https://roboflow.com/)*** for the annotated dataset.

**Complete code in Colab Notebook:**

**[ Notebook Link ](https://gist.github.com/Abonia1/eac0e5db887855bbab7875b914ebf429#file-train-yolov8-early-fire-smoke-detection-on-custom-dataset-ipynb)**

<script src="https://gist.github.com/Abonia1/eac0e5db887855bbab7875b914ebf429.js"></script>

Once the model is trained, it can be evaluated on the validation set to measure its performance. This can be done by running the evaluation script, which outputs the mean Average Precision (mAP) score for the validation set. The mAP score is a measure of how well the model is able to detect the objects of interest in the validation set.

![Source-Image by Author: Confusion Matrix](https://cdn-images-1.medium.com/max/6000/1*8bM1hbqo6yO3-431pTaTAg.png)

![Source-Image by Author: Train,test,validation loss and mAP](https://cdn-images-1.medium.com/max/4800/1*3-wM1-LMHxSb8PexVczhFg.png)

![Source-Image by Author: PR curve](https://cdn-images-1.medium.com/max/4500/1*xGI8pDGGspE-stuyTfNLvg.png)

Finally, the trained model can be used for inference on new images/videos. This can be done by running the inference script and providing it with the path to an image. The script will display the detected fire and smoke regions on the input image.

## Inference

Sample Results :

![](https://cdn-images-1.medium.com/max/3840/1*MlsDxcNfuYKBN88T-Y7TzA.jpeg)

![](https://cdn-images-1.medium.com/max/3840/1*0cI6BGRgIkBa7cMOHsn3CA.jpeg)

## **Application Area**

Fire and smoke detection have a wide range of applications, including:

1.**Residential and commercial buildings**: Fire and smoke detectors are mandatory in all buildings to ensure the safety of residents and workers. They can alert people in case of a fire and give them enough time to evacuate the building.

2. **Industrial facilities**: Fire and smoke detectors are crucial in industrial facilities where dangerous chemicals or flammable materials are stored. They can prevent fire outbreaks and minimize damage to property and the environment.

3.**Public transportation**: Fire and smoke detectors are essential in public transportation such as buses, trains, and airplanes. They can ensure the safety of passengers and prevent disasters.

4. **Power plants**: Fire and smoke detectors are used in power plants to detect and prevent fires that can cause damage to critical equipment and disrupt power supply.

5. **Military and defense**: Fire and smoke detectors are used in military and defense installations to detect and prevent fires that can damage sensitive equipment and compromise national security.

6. **Mining and oil and gas industries:** Fire and smoke detectors are used in mines and oil and gas facilities to detect and prevent fires that can pose a risk to workers and the environment.

7. **Forest Fire and Wildfire**: Detect and alert in-case of forest fires.It helps to take the necessary steps to prevent forest fire and its negative effects.

In addition to these applications, fire and smoke detection systems are also used in museums, archives, and data centers to protect valuable and irreplaceable items. Overall, fire and smoke detection is a crucial component of public safety and disaster preparedness.

## Conclusion

YOLOv8 is a powerful tool for building fire and smoke detection systems using custom datasets. With its speed and accuracy, it is a promising solution for real-world applications that require fast and efficient fire and smoke detection.


Connect with me on **[Linkedin](https://www.linkedin.com/in/aboniasojasingarayar/)**

Find me on **[Github](https://github.com/Abonia1)**

Visit my technical channel on **[Youtube](https://www.youtube.com/@AboniaSojasingarayar)**

Support: **[Buy me a Cofee/Chai](https://www.buymeacoffee.com/abonia)**


