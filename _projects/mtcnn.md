---
layout: page
title: MTCNN package
description: A Python Package implementation of the MTCNN Face detection algorithm
img: assets/img/mtcnn_intro.jpg
importance: 1
category: Artificial Intelligence
featured: true
bibliography: mtcnn.bib
---


<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/mtcnn_ivan_drawn.jpg" title="My face detected by MTCNN" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    The MTCNN face detection algorithm detecting the bounding box corresponding to the face and the corresponding five keypoints.
</div>

The **MTCNN (Multi-task Cascaded Convolutional Networks)**, first proposed by Zhang et al. <d-cite key="ZHANG2016"></d-cite> in 2016, is an advanced facial detection system widely employed in computer vision. It is notable for its adeptness in precisely identifying facial structures within digital images. At its core, MTCNN leverages the capabilities of artificial neural networks, which are mathematical models inspired by the human brain's structure and function.

MTCNN's operation unfolds through a cascade of three specialized phases:

1. **First Stage (P-Net):** In the initial stage, MTCNN employs a P-Net, a neural network, to conduct a swift preliminary assessment of the image. This neural network acts like a filter, identifying regions that exhibit potential characteristics of human faces. It generates a set of candidate bounding boxes, effectively outlining these regions.

2. **Second Stage (R-Net):** Following the preliminary detection, MTCNN delves deeper with the assistance of an R-Net, another neural network. The R-Net conducts a comprehensive examination of the previously identified candidate regions. It evaluates these regions for definitive facial attributes, confirming the presence of faces and providing refined bounding box coordinates.

3. **Third Stage (O-Net):** The final phase involves meticulous analysis performed by an O-Net, yet another neural network. The O-Net scrutinizes the facial regions with precision, identifying and localizing key facial features, including the eyes, nose, and mouth. Simultaneously, it furnishes an encompassing bounding box around the entire face.

MTCNN operates in a sequential manner, progressively narrowing its focus from a global image assessment to the intricate identification of facial components. This multifaceted approach, underpinned by artificial neural networks, results in robust and precise facial detection.

This project, based on TensorFlow, harnesses the power of MTCNN, providing a Python-based implementation for streamlined facial detection within images. The package is readily installable via `pip` using `pip install mtcnn`, enabling users to effortlessly integrate MTCNN's neural network-driven capabilities into their image analysis endeavors.



## USAGE EXAMPLE

The following snippet shows how to use the package once installed.

```python
>>> from mtcnn import MTCNN
>>> import cv2
>>>
>>> img = cv2.cvtColor(cv2.imread("ivan.jpg"), cv2.COLOR_BGR2RGB)
>>> detector = MTCNN()
>>> detector.detect_faces(img)
[
    {
        'box': [277, 90, 48, 63],
        'keypoints':
        {
            'nose': (303, 131),
            'mouth_right': (313, 141),
            'right_eye': (314, 114),
            'left_eye': (291, 117),
            'mouth_left': (296, 143)
        },
        'confidence': 0.99851983785629272
    }
]
```

## REFERENCES

You can find this project's website at the following links:

 * Source code: [GitHub](https://github.com/ipazc/mtcnn/)
 * PyPI Package: [PyPI](https://pypi.org/project/mtcnn/)
