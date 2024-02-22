<div align="center">
<h2>
     Yolov9-Pip: Packaged version of the Yolov9 repository
</h2>
<h4>
     <img width="600" alt="teaser" src="docs\paper.png">
</div>
<p align="center">
<a href="https://pypi.org/project/yolov9pip" target="_blank">
    <img src="https://img.shields.io/pypi/v/yolov9pip?color=%2334D058&label=pypi%20package" alt="Package version">
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

This repo is a packaged version of the [Yolov9](https://github.com/WongKinYiu/yolov9) model.

### ⭐ Installation

```
pip install yolov9pip
```

### 🌠 Yolov9 Inference

```python
import yolov9

# load pretrained or custom model
model = yolov9.load(
    "yolov9-c.pt",
    device="cpu",
)

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

## 😍 Contributing

```bash
pip install -r dev-requirements.txt
pre-commit install
pre-commit run --all-files
```

## 🤗 Citation

```bibtex
@article{wang2024yolov9,
  title={{YOLOv9}: Learning What You Want to Learn Using Programmable Gradient Information},
  author={Wang, Chien-Yao  and Liao, Hong-Yuan Mark},
  booktitle={arXiv preprint arXiv:2402.13616},
  year={2024}
}
```

### Acknowledgement

A part of the code is borrowed from [Yolov5-pip](https://github.com/fcakyon/yolov5-pip). Many thanks for their wonderful works.
