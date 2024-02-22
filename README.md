<div align="center">
<h2>
     MetaSeg: Packaged version of the Segment Anything repository
</h2>
<div>
    <img width="1000" alt="teaser" src="docs\paper.png">
</div>
    <a href="https://pepy.tech/project/yolov9pip"><img src="https://pepy.tech/badge/yolov9pip" alt="downloads"></a>
</div>

<p align="center">
<a href="https://pypi.org/project/yolov9pip" target="_blank">
    <img src="https://img.shields.io/pypi/v/yolov9pip?color=%2334D058&label=pypi%20package" alt="Package version">
</a>
<a href="https://pypi.org/project/yolov9pip" target="_blank">
    <img src="https://img.shields.io/pypi/dm/yolov9pip?color=red" alt="Download Count">
</a>
<a href="https://pypi.org/project/yolov9pip" target="_blank">
    <img src="https://img.shields.io/pypi/pyversions/yolov9pip.svg?color=%2334D058" alt="Supported Python versions">
</a>
<a href="https://pypi.org/project/yolov9pip" target="_blank">
    <img src="https://img.shields.io/pypi/status/yolov9pip?color=orange" alt="Project Status">
</a>
<a href="https://results.pre-commit.ci/latest/github/kadirnaryolov9-pip/main" target="_blank">
    <img src="https://results.pre-commit.ci/badge/github/kadirnar/yolov9-pip/main.svg" alt="pre-commit.ci">
</a>
</p>

This repo is a packaged version of the [Yolov7](https://github.com/WongKinYiu/yolov9) model.

### Installation

```
pip install yolov9
```

### Yolov9 Inference

```python
import yolov9

# load pretrained or custom model
model = yolov9.load("yolov7.pt")

# set model parameters
model.conf = 0.25  # NMS confidence threshold
model.iou = 0.45  # NMS IoU threshold
model.classes = None  # (optional list) filter by class

# set image
imgs = "data/zidane.jpg"

# perform inference
results = model(imgs)

# inference with larger input size and test time augmentation
results = model(img, size=640)

# parse results
predictions = results.pred[0]
boxes = predictions[:, :4]  # x1, y1, x2, y2
scores = predictions[:, 4]
categories = predictions[:, 5]

# show detection bounding boxes on image
results.show()
```

### Citation

```bibtex
@article{wang2022yolov7,
  title={{YOLOv7}: Trainable bag-of-freebies sets new state-of-the-art for real-time object detectors},
  author={Wang, Chien-Yao and Bochkovskiy, Alexey and Liao, Hong-Yuan Mark},
  journal={arXiv preprint arXiv:2207.02696},
  year={2022}
}
```

### Acknowledgement

A part of the code is borrowed from [Yolov5-pip](https://github.com/fcakyon/yolov5-pip). Many thanks for their wonderful works.
