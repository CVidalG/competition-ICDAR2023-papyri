# competition-ICDAR2023-papyri

## Detectron 2

Source code : https://github.com/facebookresearch/detectron2

```bash
conda create --name detectron2 python=3.8
git clone https://github.com/facebookresearch/detectron2.git
python -m pip install -e detectron2
python -m pip install detectron2 -f https://dl.fbaipublicfiles.com/detectron2/wheels/cu111/torch1.8/index.html
pip install ipykernel
```

## Yolo V5

Source code : https://github.com/ultralytics/yolov5

```bash
conda create --name yolo python=3.8
pip install ultralytics
pip install ipykernel
```

## To Do

- [ ] balance des classes
- [ ] reproduire expérience baseline
- [ ] benchmark des propriétés des modèles de Detectron 2
