# Transfer-learning-for-image-segmentation

# List of models for the segmentation in this study:
1. Unet
2. FPN
3. PSNet
4. Segformer
5. Mask R-CNN
# List of backbone models:
1. resnet34 trained on ImageNet
2. resnet50 trained on ImageNet

# List of datasets are used for Finetuning:
Pedesterian Image Dataset

## Data spliting:

Datasets are splited to train test and validation. Vlaidation dataset is used for early stoppin of the traning process with patience set to 10.
The maximun epoch is set to 100.
All images and masks are sesized to 128*128.
