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
I utilized the Pedestrian and Gland segmentation datasets and provided the corresponding links below:

Pedestrian: https://drive.google.com/file/d/12Wn7ZkrYYFphrYCJniI0FRWBMaoutQdw/view?usp=sharing

Gland (128 * 128): https://drive.google.com/file/d/1SRNW28GolYUYOUrdDNnMJj0F7EJKDu8v/view?usp=sharing

Gland (512 * 512): https://drive.google.com/file/d/1hBywB14KQ_B4kboovO_FYVd-RosWruky/view?usp=sharing


However, it is unnecessary to download them as the provided codes will automatically load the data from the specified addresses. The dataset roots consist of train, valid, and test folders, each containing images stored in .jpg format and masks in .png format

## Data Splitting, Normalization and Augmentation:
The datasets are split into training, testing, and validation sets. The validation dataset is used for early stopping during the training process, with a patience of 10.

For the Pedestrian images, horizontal flipping was applied as an augmentation technique. For the medical dataset, both horizontal and vertical rotation were employed.

We utilized Albumentations as a computer vision tool for normalization and augmentation. All datasets were normalized with a mean of [0.485, 0.456, 0.406] and a standard deviation of [0.229, 0.224, 0.225], based on the ImageNet dataset.

The maximum epoch was set to 100. In order to expedite the fine-tuning process, all images and masks were resized to 128x128 pixels. It is worth mentioning that larger image sizes may potentially lead to improved performance.


## Objective Function and Evaluation metric:
In the funetuning processs, Dice loss is used fo all models. We applied IoU as the comparison metric.
## A Comparision study on Pedesterian Segmentation:
The table presents a performance comparison of  various segmentation models based on IoU (Intersection over Union) scores on the test data.

For the models Unet, FPN, PSNet, Linknet, and DeepLabV3Plus, we utilized ResNet34 as the backbone model. In the case of Segformer, we performed fine-tuning using pretrained weights from the ADE20k dataset.

Among the CNN-based architectures, both Linknet and DeepLabV3Plus demonstrate superior performance with similar numbers of trainable parameters. However, the results indicate that Segformer significantly outperforms other models in terms of IoU score while also possessing a considerably lower number of trainable parameters.

You can find the codes through the following links:

Linknet :  https://colab.research.google.com/drive/1OsvJJZ5bJYhcl1Ohn7TPgS-xYopy12Hf?usp=sharing

PSNets :   https://colab.research.google.com/drive/1NWG5zMVO7nphXC0EnKKwZRFLLdEjK17X?usp=sharing

FPN :      https://colab.research.google.com/drive/1pbzTIC5fngbOgnItDFevNM4FYafLD0KK?usp=sharing

DeepLabV3Plus : https://colab.research.google.com/drive/1TXj5M2RpIvh9hceIOkIB8FOP38fyaYuL?usp=sharing

Segformer :  https://colab.research.google.com/drive/1vqCu2U6e4IadQwBeI2_CkMSrjrH9aPIb?usp=sharing

<img src="https://github.com/MoAKgit/Transfer-learning-for-image-segmentation/blob/main/results_pedestrian.PNG" width=80% height=80%>

## A Comparision study on Gland Segmetnation:
For this dataset, both the images and masks have been resized to a dimension of 256x256 pixels. Data augmentation is performed through flipping, and the images are normalized using a mean of [0.485, 0.456, 0.406] and a standard deviation of [0.229, 0.224, 0.225].

You can access the codes through the following links:


Linknet :  https://colab.research.google.com/drive/1rmLYOuJdednnpwzNMazipPUmSsicDGJl?usp=sharing

PSNets :   

FPN :      https://colab.research.google.com/drive/1zOAozV96oQ-EzZWmthXveOIouPYgk3af?usp=sharing

DeepLabV3Plus :  https://colab.research.google.com/drive/1oi5sLB02u0Zy_FCYLk9YyPVcq7TFfU2Z?usp=sharing

Segformer :  https://colab.research.google.com/drive/19xwhjSY5y3JsLaXv5zc6McWZ8gBecTxj?usp=sharing

<img src="https://github.com/MoAKgit/Transfer-learning-for-image-segmentation/blob/main/results_Gland.PNG" width=80% height=80%>


## Considering Linknet performance with cropping + flipping augmentations:
Here, I provide IoU performce of Linknet in full image size (512, 512). In the training phase, I applied random cropping with the size of (256, 256) and random horizental flipping. The average IoU score in test dataset is 0.844. 

Link of the code: https://colab.research.google.com/drive/1oZOntr0OIdoX_2BxmwiwGGW_8mrFjE_O?usp=sharing

And this is a result example of the test data:

<img src="https://github.com/MoAKgit/Transfer-learning-for-image-segmentation/blob/main/linket_512.png" width=100% height=100%>





