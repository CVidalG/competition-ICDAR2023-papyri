## Experiments details

### Yolo Detection (= localization + classification)

```bash
yolo detect val data=/path/to/my_yaml.yaml model=/path/to/my_best_model.pt
```

| ExpeName     | BaseModel   | P (val) | R (val) | mAP50 (val) | mAP50-95 (val) | classes | Image size | Val Conf | Thres. IoU | Comments                                       |
|--------------|-------------|---------|---------|-------------|----------------|---------|------------|----------|------------|------------------------------------------------|
| 2023-03-19_1 | yolov8n.pt  | 0.444   | 0.154   | 0.3         | 0.188          | 227     | 1280       | null     | 0.70       | default config                                 |
| 2023-03-19_2 | yolov5l6.pt | 0.803   | 0.269   | 0.542       | 0.339          | 227     | 1240       | null     | 0.70       | default config                                 |
| 2023-03-21_1 | yolov5l6.pt | 0.764   | 0.38    | 0.585       | 0.353          | 227     | 1240       | null     | 0.70       | without data-augment                           |
| 2023-03-21_2 | yolov5l6.pt | 0.744   | 0.371   | 0.57        | 0.347          | 227     | 1240       | 0.25     | 0.65       | with custom data-augment                       |
| 2023-03-21_3 | yolov5x6.pt | 0.765   | 0.248   | 0.515       | 0.3180         | 227     | 1240       | 0.25     | 0.65       | with custom data-augment                       |
| 2023-03-22_1 | yolov5x6.pt | 0.708   | 0.313   | 0.523       | 0.306          | 227     | 1240       | 0.25     | 0.65       | without data-augment                           |
| 2023-03-23_1 | yolov5l6.pt | 0.714   | 0.583   | 0.628       | 0.345          | 24      | 1280       | null     | 0.70       | with custom data-augment                       |
| 2023-03-25_1 | yolov5l6.pt |         |         |             |                | 24      | 1280       | null     | 0.70       | with custom data-augment / with split baseline |
| 2023-03-28_1 | yolov5l6.pt |         |         |             |                | 24      | 1280       | null     | 0.70       | with invert in data-aug / with split baseline  |
| 2023-03-28_2 | yolov5l6.pt |         |         |             |                | 24      | 1280       | null     | 0.70       | with inverted data/ with split baseline        |
| 2023-03-29_1 | yolov5x6.pt |         |         |             |                | 24      | 1536       | null     | 0.70       | with invert in data-aug / with split baseline  |
| 2023-03-30_1 | yolov5x6.pt | 0.730   | 0.521   | 0.656       | 0.402          | 24      | 1536       | 0.25     | 0.85       | with invert in data-aug / with split baseline  |
| 2023-03-30_2 | yolov5l6.pt | 0.752   | 0.537   | 0.675       | 0.406          | 24      | 1536       | 0.45     | 0.90       | with inverted data / with split baseline       |
| 2023-03-31_1 | yolov5x6.pt | 0.755   | 0.506   | 0.658       | 0.411         | 24      | 1536       | 0.45     | 0.90       | with inverted data / with split baseline       |
| 2023-04-01_1 | yolov5l6.pt | 0.699   | 0.495   | 0.630       | 0.404         | 24      | 1536       | 0.40     | 0.90       | default augment / with inverted data / with split baseline       |
| 2023-04-02_1 | yolov5l6.pt | 0.674   | 0.522   | 0.629       | 0.401         | 24      | 1536       | 0.45     | 0.90       | default augment / with inverted data / with split baseline / lrf: 0.1 / nbs: 128       |
| 2023-04-02_2 | yolov5l6.pt | 0.729   | 0.514   | 0.650       | 0.400         | 24      | 1536       | 0.45     | 0.90       | with inverted data / with split baseline / with BG img       |
| 2023-04-03_1 | yolov5l6.pt | 0.749   | 0.527   | 0.670       | 0.410         | 24      | 2048       | 0.45     | 0.90       | with inverted data / with split baseline / with BG img / BS 1      |
| 2023-04-04_full | yolov5l6.pt | 0.790   | 0.597   | 0.720       | 0.428         | 24      | 1536       | 0.45     | 0.90       | with inverted data / with split baseline / with BG img / DO 0.1      |
| 2023-04-04_default | yolov5l6.pt | 0.705   | 0.575   | 0.624       | 0.349         | 24      | 1536       | null     | 0.70       | with inverted data / default clean config |
| 2023-04-12_full | yolov5l6.pt | 0.822   | 0.403   | 0.626       | 0.38         | 24      | 1536       | 0.65     | 0.90       | with inverted data / clean install / cls 1.5 |

| 2023-04-13_full-1 | yolov5l6.pt | 0.767   | 0.536   | 0.679       | 0.416         | 24      | 1536       | 0.65     | 0.90       | with inverted data / clean install / box 3.5 / DO 0.3 |

| 2023-04-13_full-2 | yolov5l6.pt | 0.692   | 0.517   | 0.634       | 0.38         | 24      | 1280       | 0.65     | 0.90       | same 2023-04-13_full-1 with size 1280 |
| 2023-04-14_mega | yolov5x6.pt | 0.81   | 0.575   | 0.714       | 0.436         | 24      | 1536       | 0.65     | 0.90       | move some val img to train folder / reduce augmentation / box 3.5 / cls 1.0 / DO 0.15  |
| 2023-04-16_giga | yolov5l6.pt | 0.812   | 0.619   | 0.744       | 0.457         | 24      | 1536       | 0.35     | 0.70       | normal data / move some val img to train folder + all test in train / reduce augmentation / box 3.5 / cls 1.0 / DO 0.0  |
| 2023-04-17_giga | yolov5l6.pt | 0.886   | 0.59   | 0.747       | 0.466         | 24      | 1536       | 0.65     | 0.80       | inverted data / boost augmentation / box 3.5 / cls 1.0 / DO 0.0  |
| 2023-04-17_hypra | yolov5l6.pt | 0.797   | 0.65   | 0.753       | 0.459         | 24      | 1536       | 0.35     | 0.85       | inverted data / refact augmentation + boost augmentation / box 3.5 / cls 1.0 / DO 0.1 / not finished due to CUDA memory problem |

#### Experiments on HyperParameters (100 epochs)

| Expe                   | Epochs | CONF | IoU | box | cls | dfl | P     | R     | mAP   | mAP50-95 |
|------------------------|--------|------|-----|-----|-----|-----|-------|-------|-------|----------|
| 2023-04-11_full-test_1 | 100    | 0.45 | 0.9 | 7.5 | 1.0 | 1.5 | 0.557 | 0.251 | 0.414 | 0.278    |
| 2023-04-11_full-test_2 | 100    | 0.55 | 0.9 | 7.5 | 1.0 | 1.5 | 0.566 | 0.251 | 0.418 | 0.28     |
| 2023-04-11_full-test_3 | 100    | 0.65 | 0.9 | 7.5 | 1.0 | 1.5 | 0.602 | 0.255 | 0.438 | 0.294    |
| 2023-04-11_full-test_4 | 100    | 0.75 | 0.9 | 7.5 | 1.0 | 1.5 | 0.603 | 0.249 | 0.436 | 0.289    |
| 2023-04-11_full-test_5 | 100    | 0.45 | 0.9 | 7.5 | 1.5 | 1.5 | 0.604 | 0.25  | 0.432 | 0.282    |
| 2023-04-11_full-test_6 | 100    | 0.45 | 0.9 | 7.5 | 2.0 | 1.5 | 0.609 | 0.235 | 0.429 | 0.283    |
| 2023-04-12_full-test_7 | 100    | 0.45 | 0.9 | 7.5 | 2.5 | 1.5 | 0.616 | 0.235 | 0.429 | 0.286    |
| 2023-04-12_full-test_8 | 100    | 0.65 | 0.9 | 7.5 | 2.5 | 1.5 | 0.616 | 0.233 | 0.429 | 0.286    |
| 2023-04-12_full-test_9 | 100    | 0.65 | 0.9 | 3.5 | 2.0 | 1.5 | 0.64  | 0.237 | 0.44  | 0.278    |
| 2023-04-12_full-test_10 | 100    | 0.65 | 0.9 | 7.5 | 1.5 | 1.5 | 0.614  | 0.253 | 0.435  | 0.284    |
| 2023-04-12_full-test_11 | 100    | 0.65 | 0.9 | 3.5 | 1.0 | 1.5 | 0.628  | 0.273 | 0.457  | 0.292    |

#### Scores detail for our best model (2023-04-04_full)

| Set | Image | P     | R      | mAP50 | mAP50-95 |
|-----|-------|-------|--------|-------|----------|
| val | 9     | 0.345 | 0.0942 | 0.223 | 0.115    |
| val | 3000  | 0.728 | 0.453  | 0.618 | 0.346    |
| val | 3172  | 0.689 | 0.483  | 0.582 | 0.327    |
| val | 3208  | 0.6   | 0.392  | 0.514 | 0.329    |
| val | 3432  | 0.779 | 0.661  | 0.725 | 0.45     |
| val | 3711  | 0.868 | 0.782  | 0.862 | 0.547    |
| val | 3712  | 0.753 | 0.448  | 0.614 | 0.389    |
| val | 3743  | 0.847 | 0.774  | 0.802 | 0.504    |
| val | 4145  | 0.93  | 0.878  | 0.906 | 0.618    |
| val | 4960  | 0.75  | 0.655  | 0.746 | 0.47     |
| val | 4962  | 0.852 | 0.707  | 0.798 | 0.507    |
| val | 4964  | 0.681 | 0.464  | 0.594 | 0.402    |
| val | 5671  | 0.711 | 0.677  | 0.726 | 0.41     |
| val | 6184  | 0.895 | 0.729  | 0.832 | 0.502    |
| val | 7141  | 0.648 | 0.45   | 0.579 | 0.323    |
| val | 7250  | 0.526 | 0.294  | 0.423 | 0.258    |
| val | 7264  | 0.744 | 0.781  | 0.791 | 0.423    |
| val | 10196 | 0.96  | 0.82   | 0.902 | 0.622    |
| val | 10304 | 0.658 | 0.48   | 0.553 | 0.344    |
| val | 10336 | 0.694 | 0.401  | 0.561 | 0.368    |
| val | 10361 | 0.625 | 0.602  | 0.643 | 0.427    |
| val | 10425 | 0.890 | 0.86   | 0.89  | 0.563    |
| val | 10728 | 0.749 | 0.701  | 0.739 | 0.478    |
| val | 10901 | 0.714 | 0.611  | 0.691 | 0.480    |
| val | 10917 | 0.729 | 0.572  | 0.679 | 0.482    |
| val | 10988 | 0.755 | 0.658  | 0.712 | 0.382    |
| val | 11684 | 0.806 | 0.689  | 0.773 | 0.503    |
| test | 3453 | 0.771 | 0.735  | 0.794 | 0.533    |
| test | 4166 | 0.805 | 0.699  | 0.76 | 0.497    |
| test | 4967 | 0.915 | 0.842  | 0.892 | 0.584    |
| test | 7252 | 0.717 | 0.768  | 0.784 | 0.443    |
| test | 9902 | 0.808 | 0.664  | 0.767 | 0.48    |




#### benchmark submission

Voir scores