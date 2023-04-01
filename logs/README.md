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
| 2023-03-31_1s | yolov5x6.pt | 0.755   | 0.506   | 0.658       | 0.411         | 24      | 1536       | 0.45     | 0.90       | with inverted data / with split baseline       |