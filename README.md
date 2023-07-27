# UnLoc: A Universal Localization Method for Autonomous Vehicles using LiDAR, Radar and/or Camera Input

This repository is for UnLoc, a novel unified neural modeling approach for localization with multi-sensor input introduced in the following paper

[Muhammad Ibrahim,  Naveed Akhtar,  Saeed Anwar and  Ajmal Mian, "[ UnLoc: A Universal Localization Method for Autonomous Vehicles using LiDAR, Radar and/or Camera Input
]", IEEE/RSJ International Conference on Intelligent Robots and Systems (IROS), 2023

## Contents
1. [Introduction](#introduction)
2. [Requirements](#requirements)
3. [Citation](#citation)
4. [Acknowledgements](#acknowledgements)

## Introduction
Localization is a fundamental task in robotics for autonomous navigation. Existing localization methods rely on a single input data modality or train several computational models to process different modalities. This leads to stringent computational requirements and sub-optimal results that fail to capitalize on the complementary information in other data streams. This paper proposes UnLoc, a novel unified neural modeling approach for localization with multi-sensor input in all weather conditions. Our multi-stream network can handle LiDAR, Camera and RADAR inputs for localization on demand, i.e., it can work with one or more input sensors, making it robust to sensor failure. UnLoc uses 3D sparse convolutions and cylindrical partitioning of the space to process LiDAR frames and implements ResNet blocks with a slot attention-based feature filtering module for the Radar and image modalities. We introduce a unique learnable modality encoding scheme to distinguish between the input sensor data. Our method is extensively evaluated on Oxford Radar RobotCar, ApolloSouthBay and Perth-WA datasets. The results ascertain the efficacy of our technique.

## Requirements
- PyTorch >= 1.2
- Tested on Ubuntu 18.04 environment 
- torchvision=0.2.1
- SPCONV 1.2.1
- python 3.8
- CUDA 10.2
- pillow
- torch-scatter
- tqdm 
- scikit-image

---

---

## Citation
If you find the code helpful in your resarch or work, please cite the following papers.
```
@article{ibrahim2023unloc,
  title={UnLoc: A Universal Localization Method for Autonomous Vehicles using LiDAR, Radar and/or Camera Input},
  author={Ibrahim, Muhammad and Akhtar, Naveed and Anwar, Saeed and Mian, Ajmal},
  journal={arXiv preprint arXiv:2307.00741},
  year={2023}
}

@ARTICLE{10046141,
  author={Ibrahim, Muhammad and Akhtar, Naveed and Anwar, Saeed and Mian, Ajmal},
  journal={IEEE Transactions on Intelligent Transportation Systems}, 
  title={SAT3D: Slot Attention Transformer for 3D Point Cloud Semantic Segmentation}, 
  year={2023},
  volume={24},
  number={5},
  pages={5456-5466},
  doi={10.1109/TITS.2023.3243643}}

@article{ibrahim2023slice,
  title={Slice Transformer and Self-supervised Learning for 6DoF Localization in 3D Point Cloud Maps},
  author={Ibrahim, Muhammad and Akhtar, Naveed and Anwar, Saeed and Wise, Michael and Mian, Ajmal},
  journal={arXiv preprint arXiv:2301.08957},
  year={2023}
}
}

@article{Anwar2020IERD,
  author = {Anwar, Saeed and Huynh, Cong P. and Porikli, Fatih },
    title = {Identity Enhanced Image Denoising},
    journal={IEEE Computer Vision and Pattern Recognition Workshops (CVPRW)},
    year={2020}
}
```
