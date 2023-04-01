# competition-ICDAR2023-papyri

Website : https://lme.tf.fau.de/competitions/2023-competition-on-detection-and-recognition-of-greek-letters-on-papyri/
Codalab : https://codalab.lisn.upsaclay.fr/competitions/11675

## Detectron 2

Source code : https://github.com/facebookresearch/detectron2

```bash
conda create --name detectron2 python=3.8
git clone https://github.com/facebookresearch/detectron2.git
python -m pip install -e detectron2
python -m pip install detectron2 -f https://dl.fbaipublicfiles.com/detectron2/wheels/cu111/torch1.8/index.html
pip install ipykernel
```

### Training / Prediction

see [notebook](https://github.com/CVidalG/competition-ICDAR2023-papyri/blob/main/notebooks/manipulations_detectron2.ipynb)

## Yolo V5

Source code : https://github.com/ultralytics/yolov5

### Installation

```bash
conda create --name yolo python=3.8
pip install ultralytics
pip install ipykernel
pip install albumentations==1.0.3
```

### Training

```bash
yolo detect train data=path/to/custom/config.yaml model=path/to/pretrained/model.pt
```

#### Configs (hyperparameters, etc)

see [configs](https://github.com/CVidalG/competition-ICDAR2023-papyri/tree/main/yolo_configs)

### Validation

```bash
yolo detect val data=path/to/custom/config.yaml model=path/to/my/model.pt
```

### Prediction

#### CLI

```bash
yolo detect predict model=path/to/my/model.pt source='path/to/my/image.jpg'
```

#### Python (see [notebook](https://github.com/CVidalG/competition-ICDAR2023-papyri/blob/main/notebooks/predict_yolo.ipynb))

```python
model = YOLO("path/to/my/model/best.pt")
results = model.predict(source="path/to/my/folder", save=True)
```

## Data transformation

Invert IMG

```bash
for i in *.jpg ; do convert $i -channel RGB -negate $i ; done
```

## To Do

- [X] balance des classes
- [X] écrire à l'équipe pour le fichier .bins
- [ ] reproduire expérience baseline
- [X] benchmark des propriétés des modèles de Detectron 2

- [X] correction des classes de Yolo
- [X] Visualisation des predictions de la baseline
- [X] Split à nouveau des données pour avoir le même ensemble pour pred
