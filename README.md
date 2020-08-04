# Series-Photo-Selection

  Implementation of Paper：LEARNING MULTI-SCALE ATTENTIVE FEATURES FOR SERIES PHOTO SELECTION //ICASSP2020   
  
## Introduction
  In this paper, we develop a novel deep CNN architecture that aggregates multi scale features from different network layers, in order to capture the subtle differences between series photos. To reduce the risk of redundant or even interfering features, we introduce the spatial-channel self-attention mechanism to adaptively recalibrate the features at each layer, so that informative features can be selectively emphasized and less useful ones suppressed.   
  
## Structure
![image](https://github.com/zhenshen-mla/Series-Photo-Selection/blob/master/examples/structure.png)  
   Overview of the proposed deep network architecture for series photo selection. The backbone of our learning algorithm is an end-to-end deep CNN architecture. In our study, features from different network layers are jointly leveraged to help capture the subtle differences between series photos.  
  
## Models
  * `/models/layer_afa.py`: implementation of afa layer;
  * `/models/net_image_resnet.py`: single task network based resnet50;   
  * `/models/net_image_afalayer.py`: image tasks aggregation with afa layer;   
  * `/models/net_pixel_deeplab.py`: single task network based deeplab;   
  * `/models/net_pixel_afalayer.py`: pixel tasks aggregation with afa layer;   
  
## Requirements  

  Python >= 3.6  
  numpy  
  PyTorch >= 1.0  
  torchvision  
  tensorboardX
  

## Installation
  1. Clone the repo:   
    ```
    git clone https://github.com/zhenshen-mla/AFANet.git   
    ```   
    ```
    cd AFANet
    ```
  2. For custom dependencies:   
    ```
    pip install matplotlib tensorboardX   
    ```
## For Training   
  1. Download the dataset([NYUv2](https://cs.nyu.edu/~silberman/datasets/nyu_depth_v2.html), [Adience benckmark](https://talhassner.github.io/home/projects/Adience/Adience-data.html#frontalized)) and configure the data path.   
  2. Train the single-task and save the pretrained single-task model in `/weight`:   
  3. For pixel tasks, using Deeplabv3+ network with ResNet backbone to conduct semantic segmentation and depth prediction. For image tasks, using ResNet network to conduct age prediction and gender classification (load pretrained model in `/weight`):   
  
