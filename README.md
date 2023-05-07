# Awesome Visual Dialog
A curated publication list on visual dialog.

This repository was built to facilitate navigating the mainstream on visual dialog.  
Please note that only **accepted** papers (for reliability) by **conferences** (for brevity) are contained here.

*Last updated: 2023/5/7 (Not finished yet)*

##

## Table of Contents
- [Performance Tables](#performance-tables)
  - [Discriminative Methods](#discriminative-methods)
    - [VisDial v0.9 (val)](#dis-v0.9-val)
    - [VisDial v1.0 (val)](#dis-v1.0-val)
    - [VisDial v1.0 (test-std)](#dis-v1.0-test)
    - [MNIST Dialog](#mnist-dialog)
    - [GuessWhat ?!](#guess-what)
  - [Generative Methods](#generative-methods)
    - [VisDial v0.9 (val)](#gen-v0.9-val)
    - [VisDial v1.0 (val)](#gen-v1.0-val)
    - [VisDial v1.0 (test-std)](#gen-v1.0-test)
- [Public Datasets](#public-datasets)
- [Paper List](#paper-list)
- [Feedback](#feedback)

##

## Performance Tables
The mean average precisions (mAPs) under the standard intersection over union (IoU) thresholds are reported.

In addition, links to the implementations are attached with their framework specification if available. 'o-' and 'u-' indicate the official and the unofficial implementations, respectively.

\[Note\] <br/>
*: re-implemented results <br/>
&dagger;: use of additional unlabeled images

##

### Discriminative Methods

#### VisDial v0.9 (val)
| ID | Year | Venue |   Model<br/>(or Authors)   |  MRR   |  R@1   |  R@5   |  R@10   |   MEAN&darr;   |  code  |
|:--:|:----:|:-----:|:--------------------------:|:------:|:------:|:------:|:-------:|:-------:|:------:|
| 1 | 2017 | CVPR    | [LF](#1001)    | 58.07 | 43.82 | 74.68 | 84.07 | 5.78 |[`[o-torch]`](https://github.com/batra-mlp-lab/visdial)
| 2 | 2017 | CVPR    | [HRE](#1001)   | 58.46 | 44.67 | 74.50 | 84.22 | 5.72 |[`[o-torch]`](https://github.com/batra-mlp-lab/visdial)
| 3 | 2017 | CVPR    | [HREA](#1001)  | 58.68 | 44.82 | 74.81 | 84.36 | 5.66 |[`[o-torch]`](https://github.com/batra-mlp-lab/visdial)
| 4 | 2017 | CVPR    | [MN](#1001)    | 59.65 | 45.55 | 76.22 | 85.37 | 5.46 |[`[o-torch]`](https://github.com/batra-mlp-lab/visdial)
| 5 | 2017 | NeurIPS | [HCIAE](#1003) | 62.22 | 48.48 | 78.75 | 87.59 | 4.81 |[`[o-pytorch]`](https://github.com/jiasenlu/visDial.pytorch)
| 6 | 2017 | NeurIPS | [AMEM](#1004)  | 62.27 | 48.53 | 78.66 | 87.43 | 4.86 | 
| 7 | 2018 | CVPR    | [CoAtt](#1005) | 63.98 | 50.29 | 80.71 | 88.81 | 4.47 | 
| 8 | 2018 | CVPR    | [SF](#1006)    | 62.42 | 48.55 | 78.96 | 87.75 | 4.70 | 
| 9 | 2018 | ECCV    | [CorefNMN](#1008) | 64.10 | 50.92 | 80.18 | 88.81 | 4.45 | 
| 10 | 2019 | CVPR   | [GNN](#1009)   | 62.85 | 48.95 | 79.65 | 88.36 | 4.57 | [`[o-pytorch]`](https://github.com/zilongzheng/visdial-gnn)
| 11 | 2019 | CVPR   | [RvA](#1011)   | 66.34 | 52.71 | 82.97 | 90.73 | 3.93 |[`[o-pytorch]`](https://github.com/yuleiniu/rva)
| 12 | 2019 | IJCAI  | [DVAN](#1012)  | 66.67 | 53.62 | 82.85 | 90.72 | 3.93
| 13 | 2019 | EMNLP  | [DAN](#1013)   | 66.38 | 53.33 | 82.42 | 90.38 | 4.04 |[`[o-pytorch]`](https://github.com/gicheonkang/DAN-VisDial)
| 14 | 2019 | ICCV   | [HACAN](#1014) | 67.92 | 54.76 | 83.03 | 90.68 | 3.97


#### VisDial v1.0 (val)
| ID | Year | Venue |   Model<br/>(or Authors)   | NDCG |  MRR   |  R@1   |  R@5   |  R@10   |   MEAN&darr;   |  code  |
|:--:|:----:|:-----:|:--------------------------:|:----:|:------:|:------:|:------:|:-------:|:-------:|:------:|
| 1 | 2017 | CVPR    | [MN*](#1001)    | 55.13 | 60.42 | 46.09 | 78.14 | 88.05 | 4.63
| 2 | 2017 | NeurIPS | [HCIAE*](#1003) | 57.65 | 62.96 | 48.94 | 80.50 | 89.66 | 4.24
| 3 | 2018 | CVPR    | [CoAtt*](#1005) | 57.72 | 62.91 | 48.86 | 80.41 | 89.83 | 4.21
| 4 | 2019 | ACL     | [ReDan](#1015)  | 59.32 | 64.21 | 50.60 | 81.39 | 90.26 | 4.05



#### VisDial v1.0 (test-std)
| ID | Year | Venue |   Model<br/>(or Authors)   | NDCG |  MRR   |  R@1   |  R@5   |  R@10   |   MEAN&darr;   |  code  |
|:--:|:----:|:-----:|:--------------------------:|:----:|:------:|:------:|:------:|:-------:|:-------:|:------:|
| 1 | 2017 | CVPR  | [LF](#1001)          | 45.21 | 55.42 | 40.95 | 72.45 | 82.83 | 5.95 |[`[o-torch]`](https://github.com/batra-mlp-lab/visdial)
| 2 | 2017 | CVPR  | [HRE](#1001)         | 45.46 | 54.16 | 39.93 | 70.45 | 81.50 | 6.41 |[`[o-torch]`](https://github.com/batra-mlp-lab/visdial)
| 3 | 2017 | CVPR  | [MN](#1001)          | 47.50 | 55.49 | 40.98 | 72.30 | 83.30 | 5.92 |[`[o-torch]`](https://github.com/batra-mlp-lab/visdial)
| 4 | 2018 | ECCV  | [CorefNMN](#1008)    | 54.70 | 61.50 | 47.55 | 78.10 | 88.80 | 4.40 
| 5 | 2019 | CVPR  | [GNN](#1009)         | 52.82 | 61.37 | 47.33 | 77.98 | 87.83 | 4.57 | [`[o-pytorch]`](https://github.com/zilongzheng/visdial-gnn)
| 6 | 2019 | CVPR  | [Sync](#1010)        | 57.32 | 62.20 | 47.90 | 80.43 | 89.95 | 4.17 
| 7 | 2019 | CVPR  | [RvA](#1011)         | 55.59 | 63.03 | 49.03 | 80.40 | 89.83 | 4.18 |[`[o-pytorch]`](https://github.com/yuleiniu/rva)
| 8 | 2019 | IJCAI | [DVAN](#1012)        | 54.70 | 62.58 | 48.90 | 79.35 | 89.03 | 4.36
| 9 | 2019 | EMNLP | [DAN](#1013)         | 57.59 | 63.20 | 49.63 | 79.75 | 89.35 | 4.30 |[`[o-pytorch]`](https://github.com/gicheonkang/DAN-VisDial)
| 10 | 2019 | ICCV  | [HACAN](#1014)      | 57.17 | 64.22 | 50.88 | 80.63 | 89.45 | 4.20 
| 11 | 2019 | ACL   | [ReDan](#1015)      | 61.86 | 53.13 | 41.38 | 66.07 | 74.50 | 8.91



#### MNIST Dialog
| ID | Year | Venue |   Model<br/>(or Authors)   | Accuracy |  code  |
|:--:|:----:|:-----:|:--------------------------:|:--------:|:------:|
| 1 | 2017 | NeurIPS | [AMEM](#1004)     | 96.39 | 
| 2 | 2018 | ECCV    | [CorefNMN](#1008) | 99.30 |



### GuessWhat?!
| ID | Year | Venue |   Model<br/>(or Authors)   | Train err | Val err | Test err | code |
|:--:|:----:|:-----:|:--------------------------:|:---------:|:-------:|:---------|:----:|
| 1  | 2017 | CVPR   | [LSTM+VGG](#1002)  | 26.1 | 38.5 | 39.2 | [`[o-tensorflow]`](https://github.com/GuessWhatGame/guesswhat/)
| 2  | 2017 | CVPR   | [HRED+VGG](#1002)  | 27.4 | 38.4 | 39.6 | [`[o-tensorflow]`](https://github.com/GuessWhatGame/guesswhat/)
| 3  | 2017 | CVPR   | [A-ATT](#1007)     | 26.7 | 33.7 | 34.2 |
| 4  | 2019 | ICCV   | [HACAN](#1013)     | 26.1 | 32.3 | 33.2 |

### Generative Methods
#### VisDial v0.9 (val)
| ID | Year | Venue |   Model<br/>(or Authors)   |  MRR   |  R@1   |  R@5   |  R@10   |   MEAN&darr;   |  code  |
|:--:|:----:|:-----:|:--------------------------:|:------:|:------:|:------:|:-------:|:-------:|:------:|
| 1 | 2017 | CVPR    | [LF](#1001)     | 51.99 | 41.83 | 61.78 | 67.59 | 17.07 |[`[o-torch]`](https://github.com/batra-mlp-lab/visdial)
| 2 | 2017 | CVPR    | [HRE](#1001)    | 52.37 | 42.29 | 62.18 | 67.92 | 17.07 |[`[o-torch]`](https://github.com/batra-mlp-lab/visdial)
| 3 | 2017 | CVPR    | [HREA](#1001)   | 52.42 | 42.28 | 62.33 | 68.17 | 16.79 |[`[o-torch]`](https://github.com/batra-mlp-lab/visdial)
| 4 | 2017 | CVPR    | [MN](#1001)     | 52.59 | 42.29 | 62.85 | 68.88 | 17.06 |[`[o-torch]`](https://github.com/batra-mlp-lab/visdial)
| 5 | 2017 | NeurIPS | [HCIAE](#1003)  | 53.86 | 44.06 | 63.55 | 69.24 | 16.01 |[`[o-pytorch]`](https://github.com/jiasenlu/visDial.pytorch)
| 6 | 2018 | CVPR    | [CoAtt](#1006)  | 55.78 | 46.10 | 65.69 | 71.74 | 14.43 | 
| 7 | 2018 | ECCV    | [CorefNMN](#1008) | 53.50 | 43.66 | 63.54 | 69.93 | 15.69 | 
| 8 | 2019 | CVPR    | [RvA](#1011)    | 55.43 | 45.37 | 65.27 | 72.97 | 10.71 |[`[o-pytorch]`](https://github.com/yuleiniu/rva)
| 9 | 2019 | IJCAI   | [DVAN](#1012)   | 55.94 | 46.58 | 65.50 | 71.25 | 14.79 |



#### VisDial v1.0 (val)
| ID | Year | Venue |   Model<br/>(or Authors)   | NDCG |  MRR   |  R@1   |  R@5   |  R@10   |   MEAN&darr;   |  code  |
|:--:|:----:|:-----:|:--------------------------:|:----:|:------:|:------:|:------:|:-------:|:-------:|:------:|
| 1 | 2017 | CVPR    | [MN*](#1001)    | 56.99 | 47.83 | 38.01 | 57.49 | 64.08 | 18.76
| 2 | 2017 | NeurIPS | [HCIAE*](#1003) | 59.70 | 49.07 | 39.72 | 58.23 | 64.73 | 18.43
| 3 | 2018 | CVPR    | [CoAtt*](#1005) | 59.24 | 49.64 | 40.09 | 59.37 | 65.92 | 17.86
| 4 | 2019 | ACL     | [ReDan](#1015)  | 60.47 | 50.02 | 40.27 | 59.93 | 66.78 | 17.40



#### VisDial v1.0 (test)
| ID | Year | Venue |   Model<br/>(or Authors)   | NDCG |  MRR   |  R@1   |  R@5   |  R@10   |   MEAN&darr;   |  code  |
|:--:|:----:|:-----:|:--------------------------:|:----:|:------:|:------:|:------:|:-------:|:-------:|:------:|



##

## Paper List

1. <span id = "1001">**[VisDial]**</span> | **CVPR'17** | Visual Dialog | [`[pdf]`](https://arxiv.org/pdf/1611.08669.pdf) | [`[o-torch]`](https://github.com/batra-mlp-lab/visdial)
2. <span id = "1002">**[GuessWhat]**</span> | **CVPR'17** | GuessWhat?! Visual object discovery through multi-modal dialogue | [`[pdf]`](https://arxiv.org/pdf/1611.08481.pdf) | [`[o-tensorflow]`](https://github.com/GuessWhatGame/guesswhat/)
2. <span id = "1003">**[HCIAE]**</span> | **NIPS'17** | Best of Both Worlds: Transferring Knowledge from Discriminative Learning to a Generative Visual Dialog Model | [`[pdf]`](https://arxiv.org/pdf/1706.01554.pdf) | [`[o-pytorch]`](https://github.com/jiasenlu/visDial.pytorch)
3. <span id = '1004'>**[AMEM]**</span> | **NIPS'17** | Visual Reference Resolution using Attention Memory for Visual Dialog | [`[pdf]`](https://proceedings.neurips.cc/paper_files/paper/2017/file/654ad60ebd1ae29cedc37da04b6b0672-Paper.pdf)
4. <span id = "1005">**[CoAtt]**</span> | **CVPR'18** | Are You Talking to Me? Reasoned Visual Dialog Generation through Adversarial Learning | [`[pdf]`](https://arxiv.org/pdf/1711.07613.pdf)
5. <span id = "1006">**[SF]**</span> | **CVPR'18** | Two Can Play This Game: Visual Dialog With Discriminative Question Generation and Answering | [`[pdf]`](https://arxiv.org/pdf/1803.11186.pdf)
6. <span id = "1007">**[A-ATT]**</span> | **CVPR'18** | Visual grounding via accumulated attention | [`[pdf]`](https://openaccess.thecvf.com/content_cvpr_2018/papers/Deng_Visual_Grounding_via_CVPR_2018_paper.pdf)
7. <span id = "1008">**[CorefNMN]**</span> | **ECCV'18** | Visual Coreference Resolution in Visual Dialog using Neural Module Networks | [`[pdf]`](https://arxiv.org/pdf/1809.01816.pdf)
8. <span id = "1009">**[GNN]**</span> | **CVPR'19** | Reasoning Visual Dialogs with Structural and Partial Observations | [`[pdf]`](https://arxiv.org/pdf/1904.05548.pdf) | [`[o-pytorch]`](https://github.com/zilongzheng/visdial-gnn)
9. <span id = "1010">**[Sync]**</span> | **CVPR'19** | Image-Question-Answer Synergistic Network for Visual Dialog | [`[pdf]`](https://arxiv.org/pdf/1902.09774.pdf)
10. <span id = "1011">**[RvA]**</span> | **CVPR'19** | Recursive Visual Attention in Visual Dialog | [`[pdf]`](https://arxiv.org/pdf/1812.02664.pdf) | [`[o-pytorch]`](https://github.com/yuleiniu/rva)
11. <span id = "1012">**[DVAN]**</span> | **IJCAI'19** | Dual Visual Attention Network for Visual Dialog | [`[pdf]`](https://www.ijcai.org/Proceedings/2019/0693.pdf)
12. <span id = "1013">**[DAN]**</span> | **EMNLP'19** | Dual Attention Networks for Visual Reference Resolution in Visual Dialog |[`[pdf]`](https://arxiv.org/pdf/1902.09368.pdf) | [`[o-pytorch]`](https://github.com/gicheonkang/DAN-VisDial)
13. <span id = "1014">**[HACAN]**</span> | **ICCV'19** | Making History Matter: History-Advantage Sequence Training for Visual Dialog | [`[pdf]`](https://arxiv.org/pdf/1902.09326.pdf)
14. <span id = "1015">**[ReDan]**</span> | **ACL'19** | Multi-step Reasoning via Recurrent Dual Attention for Visual Dialog | [`[pdf]`](https://arxiv.org/abs/1902.00579)

##

## Feedback

If you have any suggestions or find missing papers, please feel free to contact me.

- [e-mail](mailto:chenmengyuan2021@ia.ac.cn)
- [pull request](https://github.com/MengyuanChen21/Awesome-Visual-Dialog/pulls)

