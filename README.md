# Transfer-learning-for-image-segmentation

## List of models for the segmentation in this study:
1. Unet
2. FPN
3. PSNet
4. Segformer
5. Linknet
6. DeepLabV3Plus
## List of backbone models:
1. resnet34 trained on ImageNet
2. resnet50 trained on ImageNet
3. resnet101 trained on ImageNet

## List of datasets are used for Finetuning:
Pedesterian Image Dataset
Gland Segmentation Dataset

## Data spliting:

Datasets are splited to train test and validation. Validation dataset is used for early stopping of the training process with patience equals 10.

All datasets are normalized with mean = [0.485, 0.456, 0.406]  and standard deviation = [0.229, 0.224, 0.225] , with respect to the imagenet dataset. 
To augment the datset, For Peresterian images horizental roration is applied. For the medical dataset, both horizental and vertical rotation is used.

The maximun epoch is set to 100.
All images and masks are sesized to 128*128.

## Objective Function:
In the funetuning processs, Dice loss is used fo all models.

## A Comparision study on different backbones:
## A Comparision study on Model structures:
## A Comparision study on different datasets:

