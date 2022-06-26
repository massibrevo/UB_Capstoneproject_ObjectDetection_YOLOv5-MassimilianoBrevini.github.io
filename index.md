# UB Capstoneproject YOLOv5

This project has been developed in agreement with Voi Technology. S.L.; the tools and frameworks used have been previously agreed by both university and the company.

In this notebook I assamble a dataset and train a custom YOLOv5 model to recognise Voi e-scooters parked in the streets of Milan.

The project and Notebook is divided in two parts:

## EDA
->> here is where I run a small EDA to undestand the data of % of bad parkings in the city of Milan and to decide if was worth to develop the project on this city (Milan).

## MODEL
I’ve labelled and annotate 760 pictures from Milan users end ride parking photos, using Roboflow software.

I’ve annotate them with 4 adifferent labels: rack_bicycle rack_general scooter whitelines

I've used Roboflow software also to run different experiments and finally I used the following TRAINING OPTION CONFIGURATION:

### Split the dataset
70% TRAIN 20% VALIDATION 10% TEST

### Preprocessing:
Auto-Orient --> Discard EXIF rotations and standardize pixel ordering. Resize --> Downsize images for smaller file sizes and faster training.

### Augmentation:
- Crop --> (0 - 10%) Add variability to positioning and size to help model be more resilient to subject translations and camera position.
- Rotation --> (0 - 15`) Add variability to rotations to help model be more resilient to camera roll.
- Brightness --> (0 - 10%) Add variability to image brightness to help your model be more resilient to lighting and camera setting changes.
- Exposure --> (0 - 7%) Add variability to image brightness to help model be more resilient to lighting and camera setting changes.
- Mosaic --> to perform better on small objects (racks + whitelines).

### Training:
--img 416 --batch 16 --epochs 150 weights: specify a path to weights to start transfer learning from. Here we choose the generic COCO pretrained checkpoint. Attached Output Metrics, Train curve Voi zip (containing labelled pictures) best (1) - weights to be used for transfer learning
