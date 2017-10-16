# Pseudo-3D Residual Networks

By [Zhaofan Qiu](http://zhaofanqiu.deepfun.club/), [Ting Yao](http://tingyao.deepfun.club/), [Tao Mei](https://www.microsoft.com/en-us/research/people/tmei/).

Microsoft Research Asia (MSRA).

### Table of Contents
0. [Introduction](#introduction)
0. [Citation](#citation)
0. [Implementation](#disclaimer-and-known-issues)
0. [Models](#models)
0. [Results](#results)
0. [Contact](#contact)

### Introduction
This repository contains the P3D ResNet models described in the paper "Learning Spatio-Temporal Representation with Pseudo-3D Residual Networks" (http://openaccess.thecvf.com/content_iccv_2017/html/Qiu_Learning_Spatio-Temporal_Representation_ICCV_2017_paper.html). These models are used in [ActivityNet 2017 challenge](activity-net.org/challenges/2017/), which won the 1st place in dense-Captioning Events in Videos task and 2rd place in Temporal Action Proposals task.

### Citation

If you use these models in your research, please cite:

    @inproceedings{qiu2017learning,
      title={Learning Spatio-Temporal Representation with Pseudo-3D Residual Networks},
      author={Qiu, Zhaofan and Yao, Ting and Mei, Tao},
      booktitle={ICCV},
      year={2017}
    }

### Implementation
0. We implement the P3D ResNet using our modified Caffe on Windows platform. For fast utilization of our model, here we give the addtional layers used in the network. So you can easily add these layers to your own Caffe branch or [Caffe master branch](https://github.com/BVLC/caffe) to support P3D ResNet.
0. In the P3D ResNet, all the blobs are 5D-blobs (num, channels, length, height, width). Some layers in early-version Caffe may only support 4D blobs due to the use of Blob<Dtype>::num(), Blob<Dtype>::channels(), Blob<Dtype>::height() and Blob<Dtype>::width(). You may need to replace these callings with Blob<Dtype>::shape(i).
0. When training the network, to speedup the network and reduce the memory demand, we use cudnnn implementation for conv_layer, relu_layer, bn_layer.
0. Our custom Caffe and training/finetuning setting files will be pulic soon.

### Models
0. P3D ResNet trained on Sports-1M dataset:
	- [OneDrive download](https://1drv.ms/f/s!ApyV7qxhN8CmuD1Psuxnuo_vn01V)
    
0. P3D Resnet trained on Kinetics dataset:
	- [OneDrive download](https://1drv.ms/f/s!ApyV7qxhN8CmuEAUq95ZgyrjRvNU)
    
## Results
Please refer to our paper for detailed results.

## Contact
If there is any question, pls feel free to contact me at zhaofanqiu@gmail.com.
