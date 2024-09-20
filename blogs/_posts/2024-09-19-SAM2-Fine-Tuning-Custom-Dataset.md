---
layout: post
title: SAM 2 Advanced Object Segmentation for Images and Videos
image: 
  path: /assets/img/blog/SAM2.png
description: >
    SAM 2 (Segment Anything Model 2) is an advanced machine learning model designed for comprehensive object segmentation in both static images and dynamic videos. Developed by Meta AI Research, SAM 2 represents a significant leap forward in computer vision capabilities, offering real-time performance and zero-shot generalization. This tutorial will explore the key features of SAM 2, its architecture, and how to get started with using this powerful tool.
sitemap: false
---

**[Link to the complete hands-on tutorial on Advanced Object Segmentation for Images](https://youtu.be/93xJstG_zl8)** 


  **Reading_time:** 5 min\
  **Tags:** [SAM, Object Segmentation, Segment Anything, Object Detection, Tracking , ComputerVision]
- Table of Contents
{:toc .large-only}

### Object Segmentation — Segment Anything

SAM 2 (Segment Anything Model 2) is an advanced machine learning model designed for comprehensive object segmentation in both static images and dynamic videos. Developed by Meta AI Research, SAM 2 represents a significant leap forward in computer vision capabilities, offering real-time performance and zero-shot generalization. This tutorial will explore the key features of SAM 2, its architecture, and how to get started with using this powerful tool.

<iframe width="900" height="500" src="https://www.youtube.com/embed/93xJstG_zl8" frameborder="0" allowfullscreen></iframe>

## Key Features

### Unified Model Architecture

SAM 2 boasts a unified model architecture that can handle both image and video segmentation tasks efficiently. This design allows for seamless integration across various applications, from still-image analysis to real-time video processing.

### Real-Time Performance

One of the standout features of SAM 2 is its ability to operate in real-time, making it suitable for applications requiring immediate visual analysis. This capability is crucial for applications such as autonomous vehicles, surveillance systems, and interactive media platforms.

### Zero-Shot Generalization

Unlike traditional models that require extensive fine-tuning for new tasks, SAM 2 demonstrates zero-shot generalization. This means it can adapt to new object categories without retraining, significantly reducing the time and computational resources required for deployment in new scenarios .

### Interactive Refinement

SAM 2 incorporates an interactive refinement feature, allowing users to guide the segmentation process through simple text prompts. This capability enhances the model’s flexibility and makes it easier to refine segmentations based on specific requirements .

### Advanced Visual Handling

The model is equipped with advanced visual handling capabilities, enabling it to process complex visual data effectively. This feature is particularly useful for dealing with challenging scenes, occlusions, and varying lighting conditions .

## Getting Started with SAM 2

To begin working with SAM 2, follow these steps:
>  📌 Github : [https://github.com/facebookresearch/segment-anything-2](https://github.com/facebookresearch/segment-anything-2)
>  📌 Paper: [https://ai.meta.com/research/publications/sam-2-segment-anything-in-images-and-videos/](https://ai.meta.com/research/publications/sam-2-segment-anything-in-images-and-videos/)
>  📌 Demo: [https://sam2.metademolab.com/](https://sam2.metademolab.com/)
>  📌 Dataset: [https://ai.meta.com/datasets/segment-anything-video/](https://ai.meta.com/datasets/segment-anything-video/)

 1. Download and Installation: In the tutorial, we have download SAM 2 from its official repo . Ensure you have the required dependencies installed on your system.

    
    !git clone https://github.com/facebookresearch/segment-anything-2.git

    
    !pip install -e /content/segment-anything-2

In colab , to download checkpoints,

    # Change to the checkpoints directory
    %cd /content/segment-anything-2/checkpoints
    
    # Make sure the script is executable
    !chmod +x download_ckpts.sh
    
    # Run the script
    !./download_ckpts.sh

2. Model Loading: Load the pre-trained SAM 2 model into your preferred deep learning framework. The model weights are typically stored in a PyTorch-compatible format.

    
    
    import numpy as np
    import torch
    import matplotlib.pyplot as plt
    from PIL import Image
    
    #use bfloat16 for the entire notebook
    torch.autocast(device_type="cuda", dtype=torch.bfloat16).__enter__()
    
    if torch.cuda.get_device_properties(0).major >= 8:
    #turn on tfloat32 for Ampere GPUs (https://pytorch.org/docs/stable/notes/cuda.html#tensorfloat-32-tf32-on-ampere-devices)
    torch.backends.cuda.matmul.allow_tf32 = True
    torch.backends.cudnn.allow_tf32 = True
    
    from sam2.build_sam import build_sam2
    from sam2.automatic_mask_generator import SAM2AutomaticMaskGenerator
    
    sam2_checkpoint = "../checkpoints/sam2_hiera_large.pt"
    model_cfg = "sam2_hiera_l.yaml"
    
    sam2 = build_sam2(model_cfg, sam2_checkpoint, device ='cuda', apply_postprocessing=False)
    
    mask_generator = SAM2AutomaticMaskGenerator(sam2)

3. Image/Video Input: Prepare your input images or videos. SAM 2 can handle both single-frame images and video streams.

4. Segmentation Process: Apply the loaded model to generate masks for objects within the input images or frames.

5. Post-processing: Refine the generated masks if needed, utilizing the interactive refinement capabilities of SAM 2.

Here is the code sample :

    
    import os
    
    def generate_mask_plot(image, mask_generator):
      image = Image.open(image)
      image = np.array(image.convert("RGB"))
      masks = mask_generator.generate(image)
      plt.figure(figsize=(20,20))
      plt.imshow(image)
      show_annotations(masks)
      plt.axis('off')
      plt.show()
    
    def show_annotations(anns, borders=True):
        if len(anns) == 0:
            return
        sorted_anns = sorted(anns, key=(lambda x: x['area']), reverse=True)
        ax = plt.gca()
        ax.set_autoscale_on(False)
    
        img = np.ones((sorted_anns[0]['segmentation'].shape[0], sorted_anns[0]['segmentation'].shape[1], 4))
        img[:,:,3] = 0
        for ann in sorted_anns:
            m = ann['segmentation']
            color_mask = np.concatenate([np.random.random(3), [0.5]])
            img[m] = color_mask
            if borders:
                import cv2
                contours, _ = cv2.findContours(m.astype(np.uint8),cv2.RETR_EXTERNAL, cv2.CHAIN_APPROX_NONE)
                # Try to smooth contours
                contours = [cv2.approxPolyDP(contour, epsilon=0.01, closed=True) for contour in contours]
                cv2.drawContours(img, contours, -1, (0,0,1,0.4), thickness=1)
    
        ax.imshow(img)
    
    image_dir = '/content/images/'
    image_names = [f for f in os.listdir(image_dir) if f.endswith(('.jpeg', '.png', '.jpg'))]
    for image_name in image_names:
      generate_mask_plot(image_dir+image_name, mask_generator)

### Complete Notebook

<script src="https://gist.github.com/Abonia1/ee907b4dbd630b38dd088dcee2f84188.js"></script>


## Conclusion

SAM 2 represents a significant advancement in object segmentation technology, offering real-time performance, zero-shot generalization, and advanced visual handling capabilities. Its unified architecture makes it versatile across various applications, from static image analysis to dynamic video processing. As researchers continue to refine and expand SAM 2’s capabilities, we can expect to see even more innovative applications in fields such as computer vision, robotics, and interactive media.


---
***Thanks for Reading!***

**[Website/Newletter](https://abonia1.github.io/)**
**[AIMagazine Substack](https://aboniasojasingarayar.substack.com)**

Connect with me on **[Linkedin](https://www.linkedin.com/in/aboniasojasingarayar/)**

Find me on **[Github](https://github.com/Abonia1)**

Visit my technical channel on **[Youtube](https://www.youtube.com/@AboniaSojasingarayar)**

Support: **[Buy me a Cofee/Chai](https://www.buymeacoffee.com/abonia)**