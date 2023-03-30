## Experiments details

### Yolo Detection (= localization + classification)

```bash
yolo detect val data=/path/to/my_yaml.yaml model=/path/to/my_best_model.pt
```

| ExpeName     | BaseModel   | P (val) | R (val) | mAP50 (val) | mAP50-95 (val) | Comments                                                     |
|--------------|-------------|---------|---------|-------------|----------------|--------------------------------------------------------------|
| 2023-03-19_1 | yolov8n.pt  | 0.444   | 0.154   | 0.3         | 0.188          | 227 classes / default config                                 |
| 2023-03-19_2 | yolov5l6.pt | 0.803   | 0.269   | 0.542       | 0.339          | 227 classes / default config                                 |
| 2023-03-21_1 | yolov5l6.pt | 0.764   | 0.38    | 0.585       | 0.353          | 227 classes / without data-augment                           |
| 2023-03-21_2 | yolov5l6.pt | 0.744   | 0.371   | 0.57        | 0.347          | 227 classes / with custom data-augment                       |
| 2023-03-21_3 | yolov5x6.pt | 0.765   | 0.248   | 0.515       | 0.3180         | 227 classes / with custom data-augment                       |
| 2023-03-22_1 | yolov5x6.pt | 0.708   | 0.313   | 0.523       | 0.306          | 227 classes / without data-augment                           |
| 2023-03-23_1 | yolov5l6.pt | 0.714   | 0.583   | 0.628       | 0.345          | 24 classes / with custom data-augment                        |
| 2023-03-25_1 | yolov5l6.pt |         |         |             |                | 24 classes / with custom data-augment / with split baseline  |
| 2023-03-28_1 | yolov5l6.pt |         |         |             |                | 24 classes / with invert in data-aug / with split baseline   |
| 2023-03-28_2 | yolov5l6.pt |         |         |             |                | 24 classes / with inverted data/ with split baseline         |
| 2023-03-29_1 | yolov5x6.pt |         |         |             |                | 24 classes / with invert in data-aug / with split baseline  / 1536 px    |
