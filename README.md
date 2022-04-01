# Oil Storage Detector

## The Data

This dataset is available at [Kaggle](https://www.kaggle.com/datasets/airbusgeo/airbus-oil-storage-detection-dataset) and contains 98 extract of SPOT imagery at roughly 1.2 meters resolution. Each each image is stored as a JPEG file of size 2560 x 2560 pixels (i.e. 3 kilometers on ground). The locations are selected worldwide. Accompanying the images are annotated polygons which are used in the output layer.

**Training sample**
![oil-storage-sample](https://user-images.githubusercontent.com/49917684/161306246-8cb6b416-cbd5-41d3-826a-f65789552cc3.jpg)

**Training sample with annotated bounding boxes**
![oil-storage-sample_annotated](https://user-images.githubusercontent.com/49917684/161306251-b7f00221-e27c-442e-82df-9c8c32f9b1b5.jpg)


## The Model

The [YOLOv5](https://github.com/ultralytics/yolov5) model is used with pretrained weights which are updates during further training. Due to the low number of images in the dataset, transfer learning was required to get a well performing model.

## 


