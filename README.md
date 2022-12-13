<p align="center">
  <h1 align="center">Clothes Segmentation using DeepLabV3+</h1>
  <p align="center">
    Train the DeepLabV3+ model on Colab with Tensorflow API.
    <br />
  </p>
</p>

<p align="center">
    <img alt="tf" src="https://img.shields.io/badge/TensorFlow-%23FF6F00.svg?style=for-the-badge&logo=TensorFlow&logoColor=white"/>
    <br/>
  </p>
</p>

<h3>
  <strong>Table of Contents</strong>
</h3>

> * [Introduction](#introduction)
> * [Training Details](#training-details)
> * [Jupyter Notebook](#jupyter-notebook) 
> * [Data](#data)
> * [Test Results](#test-results)
> * [References](#references)


# Introduction

Recently, the fashion industry has undergone a digital transformation by expanding on online platforms. Especially after the pandemic, online platforms have grown considerably commercially and as an area where data scientists can develop applications and provide benefits. This growth allows the development of compelling use cases of artificial intelligence in the fashion industry. For example, extracting clothing products and their related features from pictures can improve consumers' shopping experience and improve work efficiency for fashion workers. Therefore, the automatic labelling and visual analysis of clothing images in this area have attracted increasing attention. 

<div align="center">
    <img src="/images/result1.png" alt="example-result"/>
</div>


# Training Details

<div align="center">
    <img src="/images/deeplabv3+.png" width="50%" alt="example-result"/>
</div>


The DeepLab architecture has proven to be quite successful. This study used a pre-trained inceptionresnetv2 backbone network to parse clothing images into five main categories. 13520 images from iMaterialists (Fashion) 2020 FGVC7 for training have been resized to 256x256.  In the study, to reduce the complex structure of the data set, 46 different categories were converted into 5 main categories ( 'upper-body', 'lower-body', 'whole-body', 'feet' and 'accessories'). The Adam optimization method and categorical cross-entropy loss were used for model optimization.

This project uses DeepLabV3 as a deep learning model. However, instead of having 1 channel output from DeepLabV3 for the typical noticeable semantic segmentation task, it outputs 5 channels of output, each representing 5 main categories.



<!-- ABOUT THE PROJECT -->
# Jupyter Notebook
You can train the DeepLabV3+ model. Click the button below to open it on Colab.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://githubtocolab.com/mberkay0/regnet/blob/main/RegNet_(Self_Regulated_Network).ipynb)

<div align="center">
    <img src="/images/model_eval.png" width="60%" alt="example-result"/>
</div>


# Data

**Dataset Taxonomy**
```
+---------+-----------------------------------------+----------------+
| ClassId |                   Name                  | SuperCategory  |
+---------+-----------------------------------------+----------------+
|    0    |              shirt, blouse              |   upperbody    |
|    1    |         top, t-shirt, sweatshirt        |   upperbody    |
|    2    |                 sweater                 |   upperbody    |
|    3    |                 cardigan                |   upperbody    |
|    4    |                  jacket                 |   upperbody    |
|    5    |                   vest                  |   upperbody    |
|    6    |                  pants                  |   lowerbody    |
|    7    |                  shorts                 |   lowerbody    |
|    8    |                  skirt                  |   lowerbody    |
|    9    |                   coat                  |   wholebody    |
|    10   |                  dress                  |   wholebody    |
|    11   |                 jumpsuit                |   wholebody    |
|    12   |                   cape                  |   wholebody    |
|    13   |                 glasses                 |      head      |
|    14   |                   hat                   |      head      |
|    15   | headband, head covering, hair accessory |      head      |
|    16   |                   tie                   |      neck      |
|    17   |                  glove                  | arms and hands |
|    18   |                  watch                  | arms and hands |
|    19   |                   belt                  |     waist      |
|    20   |                leg warmer               | legs and feet  |
|    21   |            tights, stockings            | legs and feet  |
|    22   |                   sock                  | legs and feet  |
|    23   |                   shoe                  | legs and feet  |
|    24   |               bag, wallet               |     others     |
|    25   |                  scarf                  |     others     |
|    26   |                 umbrella                |     others     |
|    27   |                   hood                  | garment parts  |
|    28   |                  collar                 | garment parts  |
|    29   |                  lapel                  | garment parts  |
|    30   |                epaulette                | garment parts  |
|    31   |                  sleeve                 | garment parts  |
|    32   |                  pocket                 | garment parts  |
|    33   |                 neckline                | garment parts  |
|    34   |                  buckle                 |    closures    |
|    35   |                  zipper                 |    closures    |
|    36   |                 applique                |  decorations   |
|    37   |                   bead                  |  decorations   |
|    38   |                   bow                   |  decorations   |
|    39   |                  flower                 |  decorations   |
|    40   |                  fringe                 |  decorations   |
|    41   |                  ribbon                 |  decorations   |
|    42   |                  rivet                  |  decorations   |
|    43   |                  ruffle                 |  decorations   |
|    44   |                  sequin                 |  decorations   |
|    45   |                  tassel                 |  decorations   |
+---------+-----------------------------------------+----------------+
```
More detailed explanation [here](https://www.kaggle.com/c/imaterialist-fashion-2020-fgvc7/overview/evaluation)


<!-- RESULTS -->
## Test Results

Here are some visual and numerical results from the iMaterialist test dataset. Reasonably good results have been achieved in this dataset, which is complex, and labels are inconsistent.


| loss | Avg. IoU (%) | F1-Score (%) |  
|:---:|:---:|:---:|
| 0.3414 | 54.69 | 61.92 | 


### Visual Results
<div align="center">
    <img src="/images/result2.png" alt="example-result"/>
    <img src="/images/result3.png" alt="example-result"/>
    <img src="/images/result4.png" alt="example-result"/>
    <img src="/images/result5.png" alt="example-result"/>
    <img src="/images/result6.png" alt="example-result"/>
</div>


# References

* [iMaterialist (Fashion) 2020 at FGVC7](https://kaggle.com/competitions/imaterialist-fashion-2020-fgvc7)
* [Based tensorflow repo model](https://github.com/tensorflow/models/tree/master/research/deeplab)
* [DeepLabV3+](https://arxiv.org/pdf/1802.02611.pdf)
* [Tensorflow](https://www.tensorflow.org/)


