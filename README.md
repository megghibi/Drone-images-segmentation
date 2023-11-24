# Drone-images-segmentation
This code is built to perform supervised semantic segmentation of drone images of road scenes
with Convolutional Neural Networks UNet and DeepLab V3.
The code was originally written in Google Colab and using Pytorch and Segmentation Models 
found at https://github.com/qubvel/segmentation_models.pytorch.

## Dataset
The dataset used can be found at https://www.kaggle.com/datasets/bulentsiyah/semantic-drone-dataset
The segmentation labels are 22, corresponding to road types, people, house parts, animals, etc.

## Drone landing
This final section includes a prototype code to identify the available landing area and target landing spot.

## Methods
The code is made up of different sections:
### Data preprocessing
- Data import and trasformation for pretrained network
- Possibility to perform data augmentation
- Data inspection with statistical functions
### Segmentation Model
- Definition, training and evaluation, and testing of UNet model with possibility to freeze
  layers of pretrained model.
  - Validation is done with different micro and macro scores. 
### Model comparison
- Models' scores can be stored and compared among models.

### Results inspection
- Inspection of results to understand classes distribution and individual performance.

### Drone Landing
- Identifies available landing area with safe margin with convolution on the segmented image.
- Implements two methods for selecting a landing spot:
  - Selection of middle coordinates in list of available coordinates
  - Random selection from available coordinates
- Computes fraction of successful landing spot selection by comparing with original mask.
