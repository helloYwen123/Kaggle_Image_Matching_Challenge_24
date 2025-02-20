# 👉 	Kaggle_Image_Matching_Challenge_24

This repository contains our solution for the [_"Image Matching Challenge 2024 - Hexathlon"_](https://www.kaggle.com/competitions/image-matching-challenge-2024) Kaggle competition, where we achieved a 🚀**silver medal**.

## 🤠Algorithm Overview

![Overall of algorithm.](https://github.com/helloYwen123/Kaggle_Image_Matching_Challenge_24/blob/main/files/output.png)
## 🧐Algorithm Details
![Algorithm Details](https://raw.githubusercontent.com/helloYwen123/Kaggle_Image_Matching_Challenge_24/main/files/Selection_020.png)

![Algorithm Details 2](https://raw.githubusercontent.com/helloYwen123/Kaggle_Image_Matching_Challenge_24/main/files/Selection_021.png)

### 🧐Our approach consists of three main stages:

### 1. Image Retrieval
We retrieve images from various 3D scene datasets using pre-trained EfficientNet-B6 & B7 models from ImageNet to extract image features. The cosine distance metric is used to rank images based on similarity, selecting the top **n** images for each scene.

### 2. Feature Extraction and Matching
For the retrieved images, we employ two parallel pipelines to extract and match keypoints:
- **Corner Detection with AdaLAM**: We use Kornia's **CornerGFTT** feature detector to extract keypoints and apply the **AdaLAM** algorithm for robust feature matching. Successful match pairs are stored.
- **SuperPoint & SuperGlue**: We extract keypoints using **SuperPoint** and perform feature matching with **SuperGlue**, retaining the valid match pairs.

### 3. 3D Pose Estimation
We merge the successful match pairs from both pipelines, remove duplicates, and use **PyCOLMAP** to compute the final 3D spatial relationships, including camera positions and pose estimation.

## Model References
- [SuperPoint & SuperGlue (source code and paper)](https://github.com/magicleap/SuperGluePretrainedNetwork)
- [GFTT Algorithm Explanation](https://cvexplained.wordpress.com/2020/07/23/10-10-3-gftt/)
- [Kornia Documentation](https://kornia.readthedocs.io/en/latest/)

## Citation
If you find our work helpful, please consider citing:

```
@inproceedings{sarlin20superglue,
  author    = {Paul-Edouard Sarlin and
               Daniel DeTone and
               Tomasz Malisiewicz and
               Andrew Rabinovich},
  title     = {{SuperGlue}: Learning Feature Matching with Graph Neural Networks},
  booktitle = {CVPR},
  year      = {2020},
  url       = {https://arxiv.org/abs/1911.11763}
}
```

Appreciate your interest in our work!

