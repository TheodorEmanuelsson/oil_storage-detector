# Oil Storage Detector

## The Data

This dataset is available at [Kaggle](https://www.kaggle.com/datasets/airbusgeo/airbus-oil-storage-detection-dataset) and contains 98 extract of SPOT imagery at roughly 1.2 meters resolution. Each each image is stored as a JPEG file of size 2560 x 2560 pixels (i.e. 3 kilometers on ground). The locations are selected worldwide. Accompanying the images are annotated polygons which are used in the output layer. There is only one class in the dataset, *oil-storage-tank* but it is modelled as two classes, one being the storage tank and another being background.

*Training sample*
![oil-storage-sample](https://user-images.githubusercontent.com/49917684/161306246-8cb6b416-cbd5-41d3-826a-f65789552cc3.jpg)

*Training sample with annotated bounding boxes*
![oil-storage-sample_annotated](https://user-images.githubusercontent.com/49917684/161306251-b7f00221-e27c-442e-82df-9c8c32f9b1b5.jpg)

Since the images are rather large (computationally expensive to train), they are cropped into 512x512 images with 64 pixel overlappes. This resulted in 468 cropped training images and 120 cropped valiation images. There are also 6 test images 5 which are not annotated but could be used to visually test a model on new - unseen before - images.


## The Model

The [YOLOv5](https://github.com/ultralytics/yolov5) model is used with pretrained weights which are updates during further training. Due to the low number of images in the dataset, transfer learning was required to get a well performing model.

## Training

The model was trained for 150 epochs with a batch size of 32 using SGD

*Precision-Recall curve*

![PR_curve](https://user-images.githubusercontent.com/49917684/162888831-eace19af-a2b6-4e66-a878-bd6c43bdca7d.png)

*Training metrics over epochs*

![results](https://user-images.githubusercontent.com/49917684/162888855-66d1c059-2170-4d85-b87c-10b53f6ee327.png)

## Prediction

Using a confidence cutoff of 0.65, the following results was achieved.

*Snowy image with few storage tanks*

![67f7c7ad-11a1-4c7f-9f2a-da7ef50bfdd8](https://user-images.githubusercontent.com/49917684/162888583-d0ecc2e0-d1c6-40a1-8e92-eee473686a13.jpg)

*Image with lots of storage tanks*

![605ffac0-69d5-4748-92c2-48d43f51afc1](https://user-images.githubusercontent.com/49917684/162888616-48ef1f11-0b74-410d-944a-40e647bc3021.jpg)
