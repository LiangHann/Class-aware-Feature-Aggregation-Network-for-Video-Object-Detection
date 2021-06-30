# CFA-Net for Video Object Detection (Under Construction)

By Liang Han, Pichao Wang, Zhaozheng Yin, Fan Wang, and Hao Li.

This repo is an official implementation of ["Class-aware Feature Aggregation Network for Video Object Detection"](https://www.researchgate.net/publication/352523251_Class-aware_Feature_Aggregation_Network_for_Video_Object_Detection), accepted by TCSVT 2021. This repository contains a PyTorch implementation of our approach CFA-Net based on [maskrcnn_benchmark](https://github.com/facebookresearch/maskrcnn-benchmark), as well as some training scripts to reproduce the results on ImageNet VID reported in our paper. 

## Citing CFA-Net
Please consider to cite our paper in your publications if it helps your research.


## Main Results

Source code and Pretrained models will be available soon.

## Installation

Please follow [INSTALL.md](INSTALL.md) for installation instructions.

## Data preparation

Please download ILSVRC2015 DET and ILSVRC2015 VID dataset from [here](http://image-net.org/challenges/LSVRC/2015/downloads). After that, we recommend to symlink the path to the datasets to `datasets/`. And the path structure should be as follows:

    ./datasets/ILSVRC2015/
    ./datasets/ILSVRC2015/Annotations/DET
    ./datasets/ILSVRC2015/Annotations/VID
    ./datasets/ILSVRC2015/Data/DET
    ./datasets/ILSVRC2015/Data/VID
    ./datasets/ILSVRC2015/ImageSets
    
**Note**: We have already provided a list of all images we use to train and test our model as txt files under directory `datasets/ILSVRC2015/ImageSets`. You do not need to change them.

## Usage

**Note**: Cache files will be created at the first time you run this project, this may take some time! Don't worry!

**Note**: Currently, one GPU could only hold 1 image. Do not put 2 or more images on 1 GPU!

**Note** We provide template files named `BASE_RCNN_{}gpus.yaml` which would automatically change the batch size and other relevant settings. This behavior is similar to detectron2. If you want to train model with different number of gpus, please change it by yourself :) But assure **1 GPU only holds 1 image**! That is to say, you should always keep `SOLVER.IMS_PER_BATCH` and `TEST.IMS_PER_BATCH` equal to the number of GPUs you use.


### Demo Usage
Please follow [demo/README.md](demo/README.md) to see how to visualize your own images or video.


## Contributing to the project
Any pull requests or issues are welcomed.

## Acknowledgement
This implementation is mainly based on the MEGA ["Memory Enhanced Global-Local Aggregation for Video Object Detection"] (https://github.com/Scalsol/mega.pytorch)