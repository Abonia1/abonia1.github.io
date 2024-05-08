---
layout: post
title: YOLO Segmentation Predictions to Labelme and Anylabeling-Compatible JSON
image: 
  path: https://raw.githubusercontent.com/Abonia1/yolosegment2labelme/main/images/labelme_test/logo.png
description: >
  yolosegment2labelme - a Python package that allows you to convert YOLO segmentation prediction results to LabelMe and anylabeling JSON format. This tool facilitates the annotation easy.
sitemap: true
---

  **Reading_time:** 5 min\
  **Tags:** [YOLO, ,Annotation, LabelMe, AnyLbaeling, ComputerVision, Json]
- Table of Contents
{:toc .large-only}
**Table of Contents:**
- [Setting your environment)](#using-a-virtual-environment)
- [Sample Usage](#sample-usage)
- [Sample Output in Annotation tool](#sample-output-in-anylabeling-annotation-tool)

# Installing YOLO Segment to LabelMe Converter

I'm excited to announce the release of a new Python package, **[yolosegment2labelme](https://github.com/Abonia1/yolosegment2labelme)**, which is now available on PyPI. This tool is specifically designed to streamline the conversion process of YOLO segmentation masks into a format that's fully compatible with LabelMe and anylabeling, a widely recognized annotation tool for image segmentation tasks. In this guide, I'll walk you through the installation process and provide you with a clear understanding of how to utilize this package effectively in your projects.

**![Source-Image by Author: Github - yolosegment2labelme ](/assets/img/blog/yolosegment2labelme.png)**

# Installing [YOLO Segment to LabelMe Converter](https://pypi.org/project/yolosegment2labelme/)

This guide will walk you through the process of installing the **[yolosegment2labelme](https://pypi.org/project/yolosegment2labelme/)** package, a tool designed to convert YOLO segmentation masks into a format compatible with LabelMe, a popular annotation tool for image segmentation tasks.

The source code for `yolosegment2labelme` can be found on **[GitHub](https://github.com/Abonia1/yolosegment2labelme)**, where you can contribute, report issues, or explore the codebase.


## Prerequisites

Before you begin, ensure you have the following prerequisites installed on your system:

- Python 3.x
- pip (Python package installer)

## Installation

To install the `yolosegment2labelme` package, you can use the `pip` command. Open your terminal or command prompt and execute the following command:

```bash
python -m pip install yolosegment2labelme
```

If you're using Python 3 and have both Python 2 and Python 3 installed, you might need to use `python3` instead:

```bash
python3 -m pip install yolosegment2labelme
```

### Specifying a Version

If you need a specific version of the package, you can specify it by appending `==<version>` to the package name. For example, to install version 0.0.4, you would use:

```bash
python -m pip install yolosegment2labelme==0.0.4
```

## Using a Virtual Environment

It's recommended to use a virtual environment when installing Python packages to avoid conflicts between package versions. You can create a virtual environment using `venv` (included in Python 3.3 and later) or `virtualenv`.

### Creating a Virtual Environment with venv

1. Create a virtual environment:

```bash
python3 -m venv myenv
```

2. Activate the virtual environment:

- On Windows:

```bash
myenv\Scripts\activate
```

- On macOS and Linux:

```bash
source myenv/bin/activate
```

3. With the virtual environment activated, install the `yolosegment2labelme` package:

```bash
python -m pip install yolosegment2labelme
```
## Sample Usage

To convert segmentation masks from a directory of images using the default model (`yolo8n-seg`) and a default confidence score of 0.2, you can use the following command:

```bash
python yolosegment2labelme.py --images ../images
```

In this example, replace `../images` with the path to the directory containing your YOLO segmentation mask images. The script will process all images in the specified directory, applying the default model and confidence score to generate LabelMe-compatible annotations.


### Customizing the Model and Confidence Score

If you prefer to use a specific YOLO model or your custom fine-tuned model and adjust the confidence score for the predictions, you can do so by specifying the `--model` and `--conf` options:

```bash
python yolosegment2labelme.py --model yolov5n-seg.pt --images ../images --conf 0.3
```

In this command:

- `--model yolov8n-seg.pt` specifies the path to the YOLO model file you wish to use. Replace `yolov8n-seg.pt` with the path to your desired model file.
- `--images ../images` indicates the directory containing the images you want to process. Replace `../images` with the actual path to your image directory.
- `--conf 0.3` sets the confidence score threshold for the predictions. Adjust this value according to your needs; higher values require more confident predictions to be considered.

### Run

```python
!yolosegment2labelme --model yolov8n-seg.pt --images ../images  --conf 0.3
```

    
    image 1/10 /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/1.jpg: 448x640 1 bear, 118.4ms
    image 2/10 /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/10.jpg: 448x640 1 cup, 1 laptop, 1 cell phone, 2 books, 93.8ms
    image 3/10 /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/2.jpg: 640x448 1 dog, 83.3ms
    image 4/10 /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/3.jpg: 480x640 4 chairs, 97.9ms
    image 5/10 /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/4.jpg: 544x640 2 persons, 2 sports balls, 128.5ms
    image 6/10 /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/5.jpg: 448x640 4 persons, 1 sports ball, 3 kites, 81.2ms
    image 7/10 /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/6.jpg: 448x640 1 bird, 85.1ms
    image 8/10 /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/7.jpg: 416x640 1 person, 1 dog, 84.8ms
    image 9/10 /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/8.jpg: 448x640 11 persons, 5 cars, 4 traffic lights, 88.8ms
    image 10/10 /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/9.jpg: 448x640 1 person, 79.8ms
    Speed: 1.5ms preprocess, 94.1ms inference, 78.1ms postprocess per image at shape (1, 3, 448, 640)
    Results saved to [1mruns/segment/predict7[0m
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/1.jpg with label bear
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/10.jpg with label cup
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/10.jpg with label laptop
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/10.jpg with label book
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/10.jpg with label cell phone
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/10.jpg with label book
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/2.jpg with label dog
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/3.jpg with label chair
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/3.jpg with label chair
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/3.jpg with label chair
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/3.jpg with label chair
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/4.jpg with label person
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/4.jpg with label sports ball
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/4.jpg with label sports ball
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/4.jpg with label person
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/5.jpg with label person
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/5.jpg with label sports ball
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/5.jpg with label kite
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/5.jpg with label person
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/5.jpg with label kite
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/5.jpg with label person
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/5.jpg with label kite
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/5.jpg with label person
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/6.jpg with label bird
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/7.jpg with label dog
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/7.jpg with label person
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/8.jpg with label car
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/8.jpg with label person
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/8.jpg with label person
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/8.jpg with label person
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/8.jpg with label person
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/8.jpg with label car
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/8.jpg with label car
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/8.jpg with label person
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/8.jpg with label person
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/8.jpg with label traffic light
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/8.jpg with label traffic light
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/8.jpg with label person
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/8.jpg with label traffic light
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/8.jpg with label person
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/8.jpg with label person
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/8.jpg with label person
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/8.jpg with label person
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/8.jpg with label car
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/8.jpg with label car
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/8.jpg with label traffic light
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/9.jpg with label person



```python
!python yolosegment2labelme.py --images ../images 
```

    
    image 1/10 /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/1.jpg: 448x640 1 bear, 111.5ms
    image 2/10 /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/10.jpg: 448x640 1 cup, 1 laptop, 1 cell phone, 5 books, 149.6ms
    image 3/10 /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/2.jpg: 640x448 1 dog, 92.1ms
    image 4/10 /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/3.jpg: 480x640 4 chairs, 101.8ms
    image 5/10 /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/4.jpg: 544x640 2 persons, 2 sports balls, 119.7ms
    image 6/10 /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/5.jpg: 448x640 6 persons, 1 sports ball, 3 kites, 91.8ms
    image 7/10 /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/6.jpg: 448x640 1 bird, 83.4ms
    image 8/10 /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/7.jpg: 416x640 1 person, 1 dog, 78.1ms
    image 9/10 /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/8.jpg: 448x640 19 persons, 7 cars, 4 traffic lights, 85.0ms
    image 10/10 /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/9.jpg: 448x640 1 person, 1 tv, 88.7ms
    Speed: 1.1ms preprocess, 100.2ms inference, 72.5ms postprocess per image at shape (1, 3, 448, 640)
    Results saved to [1mruns/segment/predict4[0m
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/1.jpg with label bear
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/10.jpg with label cup
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/10.jpg with label laptop
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/10.jpg with label book
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/10.jpg with label cell phone
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/10.jpg with label book
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/10.jpg with label book
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/10.jpg with label book
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/10.jpg with label book
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/2.jpg with label dog
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/3.jpg with label chair
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/3.jpg with label chair
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/3.jpg with label chair
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/3.jpg with label chair
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/4.jpg with label person
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/4.jpg with label sports ball
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/4.jpg with label sports ball
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/4.jpg with label person
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/5.jpg with label person
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/5.jpg with label sports ball
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/5.jpg with label kite
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/5.jpg with label person
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/5.jpg with label kite
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/5.jpg with label person
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/5.jpg with label kite
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/5.jpg with label person
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/5.jpg with label person
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/5.jpg with label person
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/6.jpg with label bird
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/7.jpg with label dog
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/7.jpg with label person
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/8.jpg with label car
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/8.jpg with label person
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/8.jpg with label person
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/8.jpg with label person
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/8.jpg with label person
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/8.jpg with label car
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/8.jpg with label car
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/8.jpg with label person
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/8.jpg with label person
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/8.jpg with label traffic light
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/8.jpg with label traffic light
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/8.jpg with label person
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/8.jpg with label traffic light
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/8.jpg with label person
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/8.jpg with label person
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/8.jpg with label person
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/8.jpg with label person
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/8.jpg with label car
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/8.jpg with label car
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/8.jpg with label traffic light
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/8.jpg with label person
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/8.jpg with label person
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/8.jpg with label person
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/8.jpg with label car
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/8.jpg with label person
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/8.jpg with label person
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/8.jpg with label person
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/8.jpg with label person
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/8.jpg with label car
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/8.jpg with label person
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/9.jpg with label person
    Polygon information saved for /Users/aboniasojasingarayar/Documents/Github/yolosegment2labelme/yolosegment2labelme/../images/9.jpg with label tv



<div align="center">
    📦 <a href="https://github.com/Abonia1/yolosegment2labelme/blob/main/yolosegment2labelme/example.ipynb" target="_blank"><b>Sample Notebook</b></a>
</div>


## Sample Output in Anylabeling Annotation Tool

Below are examples of image annotations created in json using yolosegment2labelme and viewed in the [Anylabeling](https://github.com/vietanhdev/anylabeling) annotation tool:

| Sample Image 1                                      | Sample Image 2                                      |
|-----------------------------------------------------|-----------------------------------------------------|
| ![Sample Image 1](https://raw.githubusercontent.com/Abonia1/yolosegment2labelme/main/images/labelme_test/sample1.png)      | ![Sample Image 2](https://raw.githubusercontent.com/Abonia1/yolosegment2labelme/main/images/labelme_test/sample2.png)      |
| Sample Annotation for Image 1                      | Sample Annotation for Image 2                      |

| Sample Image 3                                      | Sample Image 4                                      |
|-----------------------------------------------------|-----------------------------------------------------|
| ![Sample Image 3](https://raw.githubusercontent.com/Abonia1/yolosegment2labelme/main/images/labelme_test/sample3.png)      | ![Sample Image 4](https://raw.githubusercontent.com/Abonia1/yolosegment2labelme/main/images/labelme_test/sample4.png)      |
| Sample Annotation for Image 3                      | Sample Annotation for Image 4                      |


By following these steps, you should now have the `yolosegment2labelme` package installed on your system, ready to convert YOLO segmentation masks into LabelMe-compatible formats.Hope this tool will be a helpful asset for researchers and developers working with image segmentation tasks, streamlining the process of preparing data for further analysis or model training.Stay tuned for our upcoming article! Until then, catch you in another exciting article!

---
# *Thanks for Reading!*


Connect with me on **[Linkedin](https://www.linkedin.com/in/aboniasojasingarayar/)**

Find me on **[Github](https://github.com/Abonia1)**

Visit my technical channel on **[Youtube](https://www.youtube.com/@AboniaSojasingarayar)**

Support: **[Buy me a Cofee/Chai](https://www.buymeacoffee.com/abonia)**



