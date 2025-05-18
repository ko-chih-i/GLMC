# 🌎[CVPR2023] Global and Local Mixture Consistency Cumulative Learning for Long-tailed Visual Recognitions（GLMC）
by **Fei Du, Peng Yang, Qi Jia, Fengtao Nan, Xiaoting Chen, Yun Yang**




## Overview
https://arxiv.org/pdf/2305.08661
<div align="center"><img src="https://user-images.githubusercontent.com/48430480/223947913-edbdd463-d6e1-4ae7-8e8d-b846c002a20d.png"></div>


> An overview of our GLMC: two types of mixed-label augmented images are processed by an encoder network and a projection head to obtain the representation $h_g$ and $h_l$. Then a prediction head transforms the two representations to output $u_g$ and $u_l$. We minimize their negative cosine similarity as an auxiliary loss in the supervised loss. $sg(*)$ denotes stop gradient operation.

> 
![image](https://user-images.githubusercontent.com/48430480/222028170-e63da465-e143-4c6d-bdb9-ca1b3e31d469.png)


> We propose an efficient one-stage training strategy for long-tailed visual recognition called Global and Local Mixture Consistency cumulative learning (GLMC). Our core ideas are twofold: (1) a global and local mixture consistency loss improves the robustness of the feature extractor. Specifically, we generate two augmented batches by the global MixUp and local CutMix from the same batch data, respectively, and then use cosine similarity to minimize the difference. (2) A cumulative head-tail soft label reweighted loss mitigates the head class bias problem. We use empirical class frequencies to reweight the mixed label of the head-tail class for long-tailed data and then balance the conventional loss and the rebalanced loss with a coefficient accumulated by epochs.

## Getting Started
### Requirements
All codes are written by Python 3.9 with

- PyTorch = 1.10.0 

- torchvision = 0.11.1

- numpy = 1.22.0

### Preparing Datasets
Download the datasets CIFAR-10
````
### Preparing 
!pip install tensorboardX
!mkdir -p GLMC-CVPR2023/output/
````
## Training

for CIFAR-10-LT
````
!python /content/GLMC/GLMC-2023/main.py  --dataset cifar10 --arch resnet32 --num_classes 10 --imbanlance_rate 0.02 --beta 0.5 --lr 0.01 --epochs 2 -b 64 --momentum 0.9 --weight_decay 5e-3 --resample_weighting 0.0 --label_weighting 1.2 --contrast_weight 4 --seed 42
````

## Citation


@inproceedings{
du2023global,
title={Global and Local Mixture Consistency Cumulative Learning for Long-tailed Visual Recognitions},
author={Fei Du, Peng Yang, Qi Jia, Fengtao Nan, Xiaoting Chen, Yun Yang},
booktitle={Conference on Computer Vision and Pattern Recognition 2023},
year={2023},
url={https://arxiv.org/abs/2305.08661}
}
````
