# UnLoc: A Universal Localization Method for Autonomous Vehicles using LiDAR, Radar and/or Camera Input

This repository is for UnLoc, a novel unified neural modeling approach for localization with multi-sensor input introduced in the following paper

[Muhammad Ibrahim,  Naveed Akhtar,  Saeed Anwar and  Ajmal Mian, "[ UnLoc: A Universal Localization Method for Autonomous Vehicles using LiDAR, Radar and/or Camera Input
]", IEEE/RSJ International Conference on Intelligent Robots and Systems (IROS), 2023

## Contents
1. [Introduction](#introduction)
2. [Requirements](#requirements)
3. [Installation of packages for Unloc](#installation)
4. [Code and Trained Models](#Code)
5. [Datasets](#Datasets)
6. [Citation](#citation)
7. [Acknowledgements](#acknowledgements)

## Introduction
Localization is a fundamental task in robotics for autonomous navigation. Existing localization methods rely on a single input data modality or train several computational models to process different modalities. This leads to stringent computational requirements and sub-optimal results that fail to capitalize on the complementary information in other data streams. This paper proposes UnLoc, a novel unified neural modeling approach for localization with multi-sensor input in all weather conditions. Our multi-stream network can handle LiDAR, Camera and RADAR inputs for localization on demand, i.e., it can work with one or more input sensors, making it robust to sensor failure. UnLoc uses 3D sparse convolutions and cylindrical partitioning of the space to process LiDAR frames and implements ResNet blocks with a slot attention-based feature filtering module for the Radar and image modalities. We introduce a unique learnable modality encoding scheme to distinguish between the input sensor data. Our method is extensively evaluated on Oxford Radar RobotCar, ApolloSouthBay and Perth-WA datasets. The results ascertain the efficacy of our technique.


Architecture of the proposed UnLoc. Top: stream of layers of our network processes 3D point cloud data. It transforms the input into a cylindrical representation which is processed by sparse 3D convolution blocks,  CB and CBD, to extract point cloud features. These features are passed through 3DMax and 3DAvg layers to compute the feature vectors. Middle: stream of the network processes images to extract features with ResNet blocks, which are further processed by our fine tuning and a transformer based features filtering module. Bottom: stream processes Radar modality and has the same architecture as the middle stream, except with an additional 2D Conv layer. Feature vectors for each modality are encoded by our  learnable modality encoding scheme which passes the features to a Regression Module for 6DoF poses prediction.
<p align="center">
  <img width="1000" src="https://github.com/IbrahimUWA/UnLoc/blob/main/figs/PaperFig7.PNG">
</p>

Schematics for common ground-truth generation for the different types of input sensors namely, Radar, Camera and LiDAR which operate at 4, 16 and 20 frames per second, respectively.
<p align="center">
  <img width="900" src="https://github.com/IbrahimUWA/UnLoc/blob/main/figs/groundtruthgeneration4.PNG">
</p>
Radar sensor output in polar form (Left) and after transformation to Cartesian coordinates (Right).
<p align="center">
  <img width="500" src="https://github.com/IbrahimUWA/UnLoc/blob/main/figs/radarfig.PNG">
</p>

<p align="center">
  <img width="1000" src="https://github.com/IbrahimUWA/UnLoc/blob/main/figs/tables.PNG">
</p>


## Requirements
- PyTorch >= 1.8.0
- Tested on Ubuntu 18.04 
- torchvision=0.2.1
- SPCONV 1.2.1
- python 3.8.1
- CUDA 11.0
- pillow
- numba 0.58.1
- numpy 1.22.0                                       
- z
- scikit-learn 1.3.0
- scipy 1.8.1 
- tqdm 
- scikit-image
## Installation of packages for Unloc
### PyTorch >= 1.8.0
pip install torch==1.8.0+cu111 torchvision==0.9.0+cu111 torchaudio==0.8.0 -f https://download.pytorch.org/whl/torch_stable.html
### SPCONV 1.2.1
git clone https://github.com/traveller59/spconv.git --recursive -b v1.2.1 <br> cd spconv and sudo apt-get install libboost-all-dev <br> python setup.py bdist_wheel <br> cd dist and pip install spconv-1.2.1-cp38-cp38-linux_x86_64.whl
### torch-scatter
pip install --no-index torch-scatter -f https://pytorch-geometric.com/whl/torch-1.8.0+cu111.html

---

---
## Code and Trained Models
Download the trained models and code of our paper from [here](https://drive.google.com/file/d/1hc778vA2NTmGwKNHrklTi57zBr7GQVNk/view?usp=drive_link). Total size is 1.31 GB. 
### Important Note
Unloc is trained and tested under an Anaconda environment on Ubuntu 18.04 and using PyCharm. Therefore, it is highly recommended to use the Anaconda environment and PyCharm to run Unloc. Please install all the required packages using both pip and conda. A complete list of software packages installed to run Unloc is included in this GitHub package. Please check the file named 'List of installed packages for Unloc". Please use Unloc-Train.py for training and Unloc-Test1.py or Unloc-Test2.py for testing as shown in Figure below.

Using Pycharm with Anaconda environment to run Unloc for both training and testing.
<p align="center">
  <img width="800" src="https://github.com/IbrahimUWA/UnLoc/blob/main/figs/Unloc-Pycharm-Anaconda.PNG">
</p>

## Datasets
### Oxford Radar RobotCar Dataset
We utilize Oxford Radar Robotcar dataset for our proposed multiple modality localization method. The dataset includes three different modalities: RGB camera images, Radar data, and point clouds from six sensors: left, right, and rear cameras; a Navtech CTS350-XFMCW Radar scanner; and left and right Velodyne HDL-32E LiDAR. NovAtel SPAN-CPT ALIGN inertial (INS) and GPS navigation systems are used to collect the ground-truth poses for this dataset. It covers a total of 280km of urban area, including more than 30 sequences, each captured over 9km. This dataset is large and challenging for localization due to the presence of a variety of foreground objects, such as people and cars. We use the same training and test sequences as Radarloc for our experiments on this dataset.
The Oxford Radar RobotCar datasetcan be downloaded from [here](https://oxford-robotics-institute.github.io/radar-robotcar-dataset/datasets). Here is the structure of the subfolders for the Oxford Radar Robotcar dataset. Please download all these folders from the dataset. Each subfolder must contain the files and folders as depicted in the image below. <br>

The structure of the subfolders for the Oxford Radar Robotcar dataset.
<p align="center">
  <img width="500" src="https://github.com/IbrahimUWA/UnLoc/blob/main/figs/Oxford-Radar-Dataset-Structure.PNG">
</p>

Files and folders within each subfolder of the Oxford Radar Robotcar dataset.
<p align="center">
  <img width="500" src="https://github.com/IbrahimUWA/UnLoc/blob/main/figs/Folders-within-each-folder.PNG">
</p>

Please download all the utility files for Oxford Radar dataset from [here](https://drive.google.com/file/d/1plCxw_Ek-W8u8HqXd4yJWZmYLUkHRUfM/view?usp=drive_link) and place in the Oxford Radar dataset folder.

### Perth-WA dataset
Perth-WA dataset is captured in the Central Business District (CBD), Perth, Western Australia. The dataset comprises a LiDAR map of 4-kilometre square area with 6DoF ground-truth per frame. The scenes include commercial structures, residential areas, food streets, complex routes, hospital buildings etc. The data is collected in three different two-hour sessions under various weather conditions. The training set comprises 20K frames of sparse and dense point clouds, and another 2.2K frames are used as the test set. The dataset is available online on IEEE data portal along with Data loader coded in Pytorch: [Perth-WA dataset](https://ieee-dataport.org/documents/perth-wa-localization-dataset-3d-point-cloud-maps)

### ApolloSouthBay
It is a comprehensive localization dataset collected in San Francisco, USA, utilizing an IMU-based system to record the ground-truth poses for the LiDAR frames. The dataset is captured in residential, urban, downtown area and highways. The dataset includes six routes: BaylandsToSeafood, ColumbiaPark,  SanJoseDowntown, SunnyvaleBigLoop, Highway237 and MathildaAVE. All these routes provide separate training and test sets. The dataset can be downloader from [here](https://developer.apollo.auto/southbay.html)

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
```
## Acknowledgements
We thank the authors of the following open-source codes: [Cylinder3D](https://github.com/xinge008/Cylinder3D), [SPCONV](https://github.com/traveller59/spconv), and [Slot Attention](https://github.com/lucidrains/slot-attention).


