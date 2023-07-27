# Slice Transformer and Self-supervised Learning for 6DoF Localization in 3D Point Cloud Maps

This repository is for transformer based self-supervised localization method and dataset introduced in the following paper

[Muhammad Ibrahim,  Naveed Akhtar,  Saeed Anwar, Michael Wise and  Ajmal Mian, "[Slice Transformer and Self-supervised Learning for 6DoF Localization
in 3D Point Cloud Maps]", IEEE International Conference on Robotics and Automation (ICRA), 2023

## Contents
1. [Introduction](#introduction)
2. [Requirements](#requirements)
3. [Citation](#citation)
4. [Acknowledgements](#acknowledgements)

## Introduction
Deep convolutional neural networks perform better on images containing spatially invariant degradations, also known as synthetic degradations; however, their performance is limited on real-degraded photographs and requires multiple-stage network modeling. To advance the practicability of restoration algorithms, this paper proposes a novel single-stage blind real image restoration network (R<sup>2</sup>Net) by employing a modular architecture. We use a residual on the residual structure to ease low-frequency information flow and apply feature attention to exploit the channel dependencies. Furthermore, the evaluation in terms of quantitative metrics and visual quality for four restoration tasks, i.e., Denoising, Super-resolution, Raindrop Removal, and JPEG Compression on  11 real degraded datasets against more than 30 state-of-the-art algorithms demonstrate the superiority of our R<sup>2</sup>Net. We also present the comparison on three synthetically generated degraded datasets for denoising to showcase our method's capability on synthetics denoising. 


## Requirements
- PyTorch 0.4.0, PyTorch 0.4.1 
- Tested on Ubuntu 14.04/16.04 environment 
- torchvision=0.2.1
- python 3.6
- CUDA 9.0 
- cuDNN 5.1 
- imageio
- pillow
- matplotlib
- tqdm 
- scikit-image

---

---

## Citation
If you find the code helpful in your resarch or work, please cite the following papers.
```
@article{Anwar2021R2NET,
    title={Attention Prior for Real Image Restoration},
    author={Saeed Anwar and Nick Barnes and Lars Petersson},
    journal={IEEE Transactions on Neural Networks and Learning Systems (TNNLS)},
    year={2021}

}

@article{anwar2019ridnet,
  title={Real Image Denoising with Feature Attention},
  author={Anwar, Saeed and Barnes, Nick},
  journal={IEEE International Conference on Computer Vision (ICCV-Oral)},
  year={2019}
}

@article{Anwar2020IERD,
  author = {Anwar, Saeed and Huynh, Cong P. and Porikli, Fatih },
    title = {Identity Enhanced Image Denoising},
    journal={IEEE Computer Vision and Pattern Recognition Workshops (CVPRW)},
    year={2020}
}
```
