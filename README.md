# Transfer-learning-for-image-segmentation

## List of models for the segmentation in this study:
1. Unet
2. FPN
3. PSNet
4. Segformer
5. Linknet
6. DeepLabV3Plus
## List of the backbone models:
1. resnet34 trained on ImageNet
4. Segformer trained on ADE20k

## List of the datasets are used for Finetuning:
Pedesterian Image Dataset
Gland Segmentation Dataset

## Datasets:
I used Pedestrian and Gland segmentation datasets. I provided the datasets in the following links:

Pedestrian: https://drive.google.com/file/d/12Wn7ZkrYYFphrYCJniI0FRWBMaoutQdw/view?usp=sharing

Gland: https://drive.google.com/file/d/1SRNW28GolYUYOUrdDNnMJj0F7EJKDu8v/view?usp=sharing

However, you dont need to download them. The provided codes will load the data from the addresses.

## Data spliting, normalization and augmentation:

Datasets are splited to train test and validation. Validation dataset is used for early stopping of the training process with patience equals 10.

We applied Albumentations as a computer vision tool for normlaization and augmentation. All datasets are normalized with mean = [0.485, 0.456, 0.406]  and standard deviation = [0.229, 0.224, 0.225] , with respect to the imagenet dataset. 
To augment the datset, For Peresterian images horizental roration is applied. For the medical dataset, both horizental and vertical rotation is used.

The maximun epoch is set to 100.
All images and masks are sesized to 128*128.

## Objective Function and comparison metric:
In the funetuning processs, Dice loss is used fo all models. We applied IoU as the comparison metric.
## A Comparision study on Pedesterian Segmentation:
The table compares the performence of different segmentation models with respect to IoU (intersection over union) scores on test data.
We used resnet34 as a backbone model for  Unet, FPN, PSNet, Linknet, and DeepLabV3Plus. In Segformer, we finetuned the model with pretrained weights from ADE20k dataset.

Between CNN based structures, Linknet and  DeepLabV3Plus outperform with almost same number of traning parameters. However, results indicate that Segformer is significantly outperforms other structures in terms of IoU score and also has less number of trainable parameters.

Codes are provided by the following links:
Linknet :  https://colab.research.google.com/drive/1OsvJJZ5bJYhcl1Ohn7TPgS-xYopy12Hf?usp=sharing

PSNets :   https://colab.research.google.com/drive/1NWG5zMVO7nphXC0EnKKwZRFLLdEjK17X?usp=sharing

FPN :      https://colab.research.google.com/drive/1pbzTIC5fngbOgnItDFevNM4FYafLD0KK?usp=sharing

DeepLabV3Plus : https://colab.research.google.com/drive/1TXj5M2RpIvh9hceIOkIB8FOP38fyaYuL?usp=sharing

Segformer :  https://colab.research.google.com/drive/1vqCu2U6e4IadQwBeI2_CkMSrjrH9aPIb?usp=sharing




## A Comparision study on Gland Segmetnation:
For this dataset, the images and masks are resized to 256*256. Flippin is applied for data augmentation and images are normalized with mean = [0.485, 0.456, 0.406] and std = [0.229, 0.224, 0.225].




