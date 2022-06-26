# UB_Capstoneproject_ObjectDetection_YOLOv5-MassimilianoBrevini
In this notebook I assamble a dataset and train a custom YOLOv5 model to recognise Voi e-scooters parked in the streets of Milan.

I’ve labelled 760 pictures from original artifact with Milan users end ride parking photos.

->> I’ve annotate them with 4 adifferent labels:
rack_bicycle
rack_general
scooter
whitelines

->> Split the dataset into (70%-20%-10%)

->> Preprocessing:
Auto-Orient --> Discard EXIF rotations and standardize pixel ordering.
Resize --> Downsize images for smaller file sizes and faster training.

->> Augmentation:
Crop --> (0 - 10%) Add variability to positioning and size to help model be more resilient to subject translations and camera position.
Rotation --> (0 - 15`) Add variability to rotations to help model be more resilient to camera roll.
Brightness --> (0 - 10%) Add variability to image brightness to help your model be more resilient to lighting and camera setting changes.
Exposure --> (0 - 7%) Add variability to image brightness to help model be more resilient to lighting and camera setting changes.
Mosaic --> to perform better on small objects (racks + whitelines).

->> Training:
--img 416 --batch 16 --epochs 150
weights: specify a path to weights to start transfer learning from. Here we choose the generic COCO pretrained checkpoint.
Attached Output
Metrics, Train curve
Voi zip (containing labelled pictures)
best (1) - weights to be used for transfer learning
ex. output test pictures
