# Awesome Visual Dialog
A curated publication list on visual dialog.

This repository was built to facilitate navigating the mainstream on visual dialog.  
Please note that only **accepted** papers (for reliability) by **conferences** (for brevity) are contained here.

*Last updated: 2023/5/7 (not finished yet)*

##

## Table of Contents
- [Performance Tables](#performance-tables)
  - [Discriminative Methods](#discriminative-methods)
    - [VisDial v0.9 val](#dis-v0.9-val)
    - [VisDial v1.0 val](#dis-v1.0-val)
    - [VisDial v1.0 val (with dense labels)](#dis-v1.0-val-dense)
    - [VisDial v1.0 test-std](#dis-v1.0-test)
    - [VisDial v1.0 test-std (with dense labels)](#dis-v1.0-test-dense)
    - [MNIST Dialog](#mnist-dialog)
    - [GuessWhat ?!](#guesswhat)
  - [Generative Methods](#generative-methods)
    - [VisDial v0.9 val](#gen-v0.9-val)
    - [VisDial v1.0 val](#gen-v1.0-val)
- [Paper List](#paper-list)
- [Feedback](#feedback)

##

## Performance Tables
The visual dialog models for both generative and discriminative tasks have been evaluated by the retrieval-based evaluation metrics: mean reciprocal rank (**MRR**), recall@k (**R@k**), mean rank (**Mean**), and normalized discounted cumulative gain (**NDCG**). Specifically, all dialogs in VisDial contain a list of 100 answer candidates for each visual question, and there is one ground-truth answer in the answer candidates. The model sorts the answer candidates by the log-likelihood scores and then is evaluated by the four different metrics. MRR, R@k, and Mean consider the rank of the single ground-truth answer, while NDCG considers all relevant answers from the 100-answers list by using the densely annotated relevance scores for all answer candidates. The community regards **NDCG** as the primary evaluation metric.

In addition, links to the implementations are attached with their framework specification if available. 'o-' and 'u-' indicate the official and the unofficial implementations, respectively.

\[Note\] <br/>
*: re-implemented results <br/>
&dagger;: use of dense labels <br/>
&ddagger;: use of additional knowledge

##

### Discriminative Methods

#### VisDial v0.9 val <span id = "dis-v0.9-val">
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
| 10 | 2019 | CVPR   | [VGNN](#1009)  | 62.85 | 48.95 | 79.65 | 88.36 | 4.57 | [`[o-pytorch]`](https://github.com/zilongzheng/visdial-gnn)
| 11 | 2019 | CVPR   | [RvA](#1011)   | 66.34 | 52.71 | 82.97 | 90.73 | 3.93 |[`[o-pytorch]`](https://github.com/yuleiniu/rva)
| 12 | 2019 | CVPR   | [FGA](#1024)   | 65.25 | 51.43 | 82.08 | 89.56 | 4.35
| 13 | 2019 | IJCAI  | [DVAN](#1012)  | 66.67 | 53.62 | 82.85 | 90.72 | 3.93
| 14 | 2019 | EMNLP  | [DAN](#1013)   | 66.38 | 53.33 | 82.42 | 90.38 | 4.04 |[`[o-pytorch]`](https://github.com/gicheonkang/DAN-VisDial)
| 15 | 2019 | ICCV   | [HACAN](#1014) | 67.92 | 54.76 | 83.03 | 90.68 | 3.97
| 16 | 2020 | AAAI   | [DualVD](#1018)| 62.94 | 48.64 | 80.89 | 89.94 | 4.17 | [`[o-pytorch]`](https://github.com/JXZe/DualVD)
| 17 | 2020 | CVPR   | [CAG](#1020)   | 67.56 | 54.64 | 83.72 | 91.48 | 3.75
| 18 | 2020 | ACL    | [MVAN](#1026)  | 67.65 | 54.65 | 83.85 | 91.47 | 3.73 | [`[o-pytorch]`](https://github.com/taesunwhang/MVAN-VisDial)
| 19 | 2020 | EMNLP   | [VD-BERT](#1028) | 70.04 | 57.79 | 85.34 | 92.68 | 4.04 | [`[o-pytorch]`](https://github.com/salesforce/VD-BERT)
| 20 | 2022 | ICASSP   | [VU-BERT](#1031) | 63.33 | 48.71 | 81.03 | 89.10 | 4.19
| 21 | 2022 | MM       | [AlignVD](#1034) | **71.65** | **59.64** | **88.30** | **94.72** | **2.96**


#### VisDial v1.0 val <span id = "dis-v1.0-val">
| ID | Year | Venue |   Model<br/>(or Authors)   | NDCG |  MRR   |  R@1   |  R@5   |  R@10   |   MEAN&darr;   |  code  |
|:--:|:----:|:-----:|:--------------------------:|:----:|:------:|:------:|:------:|:-------:|:-------:|:------:|
| 1  | 2017 | CVPR    | [MN](#1001)*    | 55.13 | 60.42 | 46.09 | 78.14 | 88.05 | 4.63
| 2  | 2017 | NeurIPS | [HCIAE](#1003)* | 57.65 | 62.96 | 48.94 | 80.50 | 89.66 | 4.24
| 3  | 2018 | CVPR    | [CoAtt](#1005)* | 57.72 | 62.91 | 48.86 | 80.41 | 89.83 | 4.21
| 4  | 2019 | ACL     | [ReDan](#1015)  | 59.32 | 64.21 | 50.60 | 81.39 | 90.26 | 4.05
| 6  | 2020 | ECCV    | [VisDial-BERT](#1023)  | 64.94 | 69.10 | 55.88 | 85.50 | 93.29 | 3.25 | [`[o-pytorch]`](https://github.com/vmurahari3/visdial-bert)
| 8  | 2020 | ECCV    | [LTMI](#1025)   | 62.72 | 62.32 | 48.94 | 78.65 | 87.88 | 4.86
| 9  | 2020 | ACL     | [MVAN](#1026)   | 60.17 | 65.33 | 51.86 | 82.40 | 90.90 | 3.88 | [`[o-pytorch]`](https://github.com/taesunwhang/MVAN-VisDial)
| 10 | 2020 | ACL     | [MCA](#1027)    | 60.27 | 64.33 | 51.12 | 80.91 | 89.65 | 4.24 | [`[o-pytorch]`](https://github.com/shubhamagarwal92/visdial_conv)
| 12 | 2020 | EMNLP   | [VD-BERT](#1028)| 63.22 | 67.44 | 54.02 | 83.96 | 92.33 | 3.53
| 13 | 2021 | ICASSP  | [SGLKT](#1030)  | 63.41 | 63.34 | - | - | - | - |
| 14 | 2021 | ICASSP  | [SGLKT](#1030)&dagger; | 74.54 | 59.10 | - | - | - | - |
| 15 | 2022 | ICASSP  | [ICMU](#1032)   | 64.30 | 69.14 | 56.80 | 85.09 | 93.42 | 3.37
| 16 | 2022 | CVPR    | [UTC](#1033)    | 63.22 | 68.58 | 55.48 | 85.38 | 93.20 | 3.28
| 17 | 2022 | MM      | [AlignVD](#1034)| **67.22** | **70.45** | **57.64** | **87.06** | **94.20** | **3.05**

#### VisDial v1.0 val (with dense labels)  <span id = "dis-v1.0-val-dense">
| ID | Year | Venue |   Model<br/>(or Authors)   | NDCG |  MRR   |  R@1   |  R@5   |  R@10   |   MEAN&darr;   |  code  |
|:--:|:----:|:-----:|:--------------------------:|:----:|:------:|:------:|:------:|:-------:|:-------:|:------:|
| 1  | 2020 | CVPR    | [P1+P2](#1019)&dagger; | 73.63 | 50.56 | 37.99 | 63.98 | 77.95 | 7.26 | [`[o-pytorch]`](https://github.com/simpleshinobu/visdial-principles)
| 2  | 2020 | ECCV    | [VisDial-BERT](#1023)&dagger; | **75.24** | **52.22** | **39.92** | **65.05** | **80.63** | **6.17** | [`[o-pytorch]`](https://github.com/vmurahari3/visdial-bert)
| 3 | 2020 | ACL     | [MCA](#1027)&dagger;    | 72.18 | 46.92 | 32.09 | 63.85 | 78.06 | 7.37 | [`[o-pytorch]`](https://github.com/shubhamagarwal92/visdial_conv)


#### VisDial v1.0 test-std <span id = "dis-v1.0-test">
| ID | Year | Venue |   Model<br/>(or Authors)   | NDCG |  MRR   |  R@1   |  R@5   |  R@10   |   MEAN&darr;   |  code  |
|:--:|:----:|:-----:|:--------------------------:|:----:|:------:|:------:|:------:|:-------:|:-------:|:------:|
| 1 | 2017 | CVPR  | [LF](#1001)          | 45.21 | 55.42 | 40.95 | 72.45 | 82.83 | 5.95 |[`[o-torch]`](https://github.com/batra-mlp-lab/visdial)
| 2 | 2017 | CVPR  | [HRE](#1001)         | 45.46 | 54.16 | 39.93 | 70.45 | 81.50 | 6.41 |[`[o-torch]`](https://github.com/batra-mlp-lab/visdial)
| 3 | 2017 | CVPR  | [MN](#1001)          | 47.50 | 55.49 | 40.98 | 72.30 | 83.30 | 5.92 |[`[o-torch]`](https://github.com/batra-mlp-lab/visdial)
| 4 | 2018 | ECCV  | [CorefNMN](#1008)    | 54.70 | 61.50 | 47.55 | 78.10 | 88.80 | 4.40 
| 5 | 2019 | CVPR  | [VGNN](#1009)        | 52.82 | 61.37 | 47.33 | 77.98 | 87.83 | 4.57 | [`[o-pytorch]`](https://github.com/zilongzheng/visdial-gnn)
| 6 | 2019 | CVPR  | [Sync](#1010)        | 57.32 | 62.20 | 47.90 | 80.43 | 89.95 | 4.17 
| 7 | 2019 | CVPR  | [RvA](#1011)         | 55.59 | 63.03 | 49.03 | 80.40 | 89.83 | 4.18 | [`[o-pytorch]`](https://github.com/yuleiniu/rva)
| 8 | 2019 | CVPR   | [FGA](#1024)        | 52.10 | 63.70 | 49.58 | 80.97 | 88.55 | 4.51 
| 9 | 2019 | IJCAI | [DVAN](#1012)        | 54.70 | 62.58 | 48.90 | 79.35 | 89.03 | 4.36
| 10 | 2019 | EMNLP | [DAN](#1013)        | 57.59 | 63.20 | 49.63 | 79.75 | 89.35 | 4.30 | [`[o-pytorch]`](https://github.com/gicheonkang/DAN-VisDial)
| 11 | 2019 | ICCV  | [HACAN](#1014)      | 57.17 | 64.22 | 50.88 | 80.63 | 89.45 | 4.20 
| 12 | 2019 | ACL   | [ReDan](#1015)      | 61.86 | 53.13 | 41.38 | 66.07 | 74.50 | 8.91
| 13 | 2020 | AAAI  | [CDF](#1017)        | 59.49 | 64.40 | 50.90 | 81.18 | 90.40 | 3.99
| 14 | 2020 | AAAI  | [DualVD](#1018)     | 56.32 | 63.23 | 49.25 | 80.23 | 89.70 | 4.11 | [`[o-pytorch]`](https://github.com/JXZe/DualVD)
| 15 | 2020 | CVPR   | [CAG](#1020)       | 56.64 | 63.49 | 49.85 | 80.63 | 90.15 | 4.11 
| 16 | 2020 | MM     | [KBGN](#1022)      | 57.60 | 64.13 | 50.47 | 80.70 | 90.16 | 4.08
| 17 | 2020 | ECCV   | [VisDial-BERT](#1023) | 63.87 | 67.50 | 53.85 | 84.68 | 93.25 | 3.32 | [`[o-pytorch]`](https://github.com/vmurahari3/visdial-bert)
| 18 | 2020 | ECCV    | [LTMI](#1025)     | 60.92 | 60.65 | 47.00 | 77.03 | 87.75 | 4.90
| 19 | 2020 | ACL     | [MVAN](#1026)     | 59.37 | 64.84 | 51.45 | 81.12 | 90.65 | 3.97 | [`[o-pytorch]`](https://github.com/taesunwhang/MVAN-VisDial)
| 20 | 2020 | EMNLP   | [VD-BERT](#1028)  | 59.96 | 65.44 | 51.63 | 82.23 | 90.68 | 3.90 | [`[o-pytorch]`](https://github.com/salesforce/VD-BERT)
| 21 | 2021 | ICASSP  | [SGLKT](#1030)    | 61.97 | 62.28 | 48.15 | 79.65 | 89.10 | 4.34 
| 22 | 2022 | ICASSP  | [ICMU](#1032)     | 61.30 | 66.82 | 53.50 | 83.05 | 92.05 | 3.59 
| 23 | 2022 | CVPR    | [UTC](#1033)      | 64.60 | **68.70** | **55.73** | 84.93 | 93.08 | 3.32
| 24 | 2022 | MM      | [AlignVD](#1034)  | **67.23** | 68.17 | 54.57 | **85.65** | **93.38** | **3.23**
| 25 | 2023 | CVPR    | [GST](#1035)&ddagger; | 64.91 | 68.44 | 55.05 | 85.18 | 93.35 | **3.23** | [`[o-pytorch]`](https://github.com/gicheonkang/gst-visdial)


#### VisDial v1.0 test-std (with dense labels) <span id = "dis-v1.0-test-dense">
| ID | Year | Venue |   Model<br/>(or Authors)   | NDCG |  MRR   |  R@1   |  R@5   |  R@10   |   MEAN&darr;   |  code  |
|:--:|:----:|:-----:|:--------------------------:|:----:|:------:|:------:|:------:|:-------:|:-------:|:------:|
| 1 | 2020 | CVPR  | [P1+P2](#1019)&dagger;      | 71.60 | 48.58 | 35.98 | 62.08 | 77.23 | 7.48 | [`[o-pytorch]`](https://github.com/simpleshinobu/visdial-principles)
| 2 | 2020 | ECCV   | [VisDial-BERT](#1023)&dagger; | 74.47 | 50.74 | 37.95 | 64.13 | 80.00 | 6.28 | [`[o-pytorch]`](https://github.com/vmurahari3/visdial-bert)
| 3 | 2020 | ACL     | [MCA](#1027)&dagger; | 72.47 | 37.68 | 20.67 | 56.67 | 72.12 | 8.89 | [`[o-pytorch]`](https://github.com/shubhamagarwal92/visdial_conv)
| 4 | 2020 | EMNLP   | [VD-BERT](#1028)&dagger;  | 74.54 | 46.72 | 33.15 | 61.58 | 77.15 | 7.18 | [`[o-pytorch]`](https://github.com/salesforce/VD-BERT)
| 5 | 2021 | ICASSP  | [SGLKT](#1030)&dagger; | 72.60 | 58.01 | 46.20 | 71.01 | 83.20 | 5.85
| 6 | 2022 | ICASSP  | [VU-BERT](#1031)&dagger; | 72.87 | 49.09 | 33.60 | 67.20 | 81.60 | 6.12
| 7 | 2022 | MM      | [AlignVD](#1034)&dagger; | **78.70** | 45.75 | 29.50 | 65.70 | 82.45 | 6.64
| 8 | 2023 | CVPR    | [GST](#1035)&dagger;&ddagger; | 71.76 | **68.09** | **55.18** | **83.68** | **91.93** | **3.57** | [`[o-pytorch]`](https://github.com/gicheonkang/gst-visdial)


#### MNIST Dialog
| ID | Year | Venue |   Model<br/>(or Authors)   | Accuracy |  code  |
|:--:|:----:|:-----:|:--------------------------:|:--------:|:------:|
| 1 | 2017 | NeurIPS | [AMEM](#1004)     | 96.39 | 
| 2 | 2018 | ECCV    | [CorefNMN](#1008) | **99.30** |



### GuessWhat?! <span id = "guesswhat">
| ID | Year | Venue |   Model<br/>(or Authors)   | Train err | Val err | Test err | code |
|:--:|:----:|:-----:|:--------------------------:|:---------:|:-------:|:--------:|:----:|
| 1  | 2017 | CVPR   | [LSTM+VGG](#1002)  | **26.1** | 38.5 | 39.2 | [`[o-tensorflow]`](https://github.com/GuessWhatGame/guesswhat/)
| 2  | 2017 | CVPR   | [HRED+VGG](#1002)  | 27.4 | 38.4 | 39.6 | [`[o-tensorflow]`](https://github.com/GuessWhatGame/guesswhat/)
| 3  | 2017 | CVPR   | [A-ATT](#1007)     | 26.7 | 33.7 | 34.2 |
| 4  | 2019 | ICCV   | [HACAN](#1013)     | **26.1** | **32.3** | **33.2** |

### Generative Methods
#### VisDial v0.9 val <span id = "gen-v0.9-val">
| ID | Year | Venue |   Model<br/>(or Authors)   |  MRR   |  R@1   |  R@5   |  R@10   |   MEAN&darr;   |  code  |
|:--:|:----:|:-----:|:--------------------------:|:------:|:------:|:------:|:-------:|:-------:|:------:|
| 1  | 2017 | CVPR    | [LF](#1001)     | 51.99 | 41.83 | 61.78 | 67.59 | 17.07 | [`[o-torch]`](https://github.com/batra-mlp-lab/visdial)
| 2  | 2017 | CVPR    | [HRE](#1001)    | 52.37 | 42.29 | 62.18 | 67.92 | 17.07 | [`[o-torch]`](https://github.com/batra-mlp-lab/visdial)
| 3  | 2017 | CVPR    | [HREA](#1001)   | 52.42 | 42.28 | 62.33 | 68.17 | 16.79 | [`[o-torch]`](https://github.com/batra-mlp-lab/visdial)
| 4  | 2017 | CVPR    | [MN](#1001)     | 52.59 | 42.29 | 62.85 | 68.88 | 17.06 | [`[o-torch]`](https://github.com/batra-mlp-lab/visdial)
| 5  | 2017 | NeurIPS | [HCIAE](#1003)  | 53.86 | 44.06 | 63.55 | 69.24 | 16.01 | [`[o-pytorch]`](https://github.com/jiasenlu/visDial.pytorch)
| 6  | 2018 | CVPR    | [CoAtt](#1006)  | 55.78 | 46.10 | 65.69 | 71.74 | 14.43 | 
| 7  | 2018 | ECCV    | [CorefNMN](#1008) | 53.50 | 43.66 | 63.54 | 69.93 | 15.69 | 
| 8  | 2019 | CVPR    | [RvA](#1011)    | 55.43 | 45.37 | 65.27 | 72.97 | **10.71** | [`[o-pytorch]`](https://github.com/yuleiniu/rva)
| 9  | 2019 | IJCAI   | [DVAN](#1012)   | 55.94 | 46.58 | 65.50 | 71.25 | 14.79 |
| 10 | 2020 | AAAI    | [DMRM](#1016)   | 55.96 | 46.20 | 66.02 | 72.43 | 13.15 | [`[o-pytorch]`](https://github.com/phellonchen/DMRM)
| 11 | 2020 | ECCV    | [LTMI](#1025)*  | 55.85 | 46.07 | 65.97 | 72.44 | 14.17 |
| 12 | 2020 | EMNLP   | [VD-BERT](#1028)| 55.95 | 46.83 | 65.43 | 72.05 | 13.18 | [`[o-pytorch]`](https://github.com/salesforce/VD-BERT)
| 13 | 2021 | ACL     | [MITVG](#1029)  | 56.83 | 47.14 | 67.19 | 73.72 | 11.95 |
| 14 | 2022 | ICASSP  | [VU-BERT](#1031)| 54.04 | 44.50 | 62.60 | 71.70 | 12.49 |
| 15 | 2023 | CVPR    | [GST](#1035)&ddagger; | **60.03** | **50.40** | **70.74** | **77.15** | 12.13 | [`[o-pytorch]`](https://github.com/gicheonkang/gst-visdial)

#### VisDial v1.0 val <span id = "gen-v1.0-val">
| ID | Year | Venue |   Model<br/>(or Authors)   | NDCG |  MRR   |  R@1   |  R@5   |  R@10   |   MEAN&darr;   |  code  |
|:--:|:----:|:-----:|:--------------------------:|:----:|:------:|:------:|:------:|:-------:|:-------:|:------:|
| 1  | 2017 | CVPR    | [MN](#1001)*    | 56.99 | 47.83 | 38.01 | 57.49 | 64.08 | 18.76
| 2  | 2017 | NeurIPS | [HCIAE](#1003)* | 59.70 | 49.07 | 39.72 | 58.23 | 64.73 | 18.43
| 3  | 2018 | CVPR    | [CoAtt](#1005)* | 59.24 | 49.64 | 40.09 | 59.37 | 65.92 | 17.86
| 4  | 2019 | ACL     | [ReDan](#1015)  | 60.47 | 50.02 | 40.27 | 59.93 | 66.78 | 17.40
| 5  | 2020 | AAAI    | [DMRM](#1016)   | -     | 50.16 | 40.15 | 60.02 | 67.21 | 15.19 | [`[o-pytorch]`](https://github.com/phellonchen/DMRM)
| 6  | 2020 | IJCAI   | [DAM](#1021)    | 60.93 | 50.51 | 40.53 | 60.84 | 67.94 | 16.65 | [`[o-pytorch]`](https://github.com/JXZe/DAM)
| 7  | 2020 | MM      | [KBGN](#1022)   | 60.42 | 50.05 | 40.40 | 60.11 | 66.82 | 17.54 |
| 8  | 2020 | ECCV    | [LTMI](#1025)   | 63.58 | 50.74 | 40.44 | 61.61 | 69.71 | 14.93 |
| 9  | 2021 | ACL     | [MITVG](#1029)  | 61.47 | 51.14 | 41.03 | 61.25 | 68.49 | 14.37 |
| 10 | 2022 | CVPR    | [UTC](#1033)    | 63.86 | 52.22 | 42.56 | 62.40 | 69.51 | 15.67 |
| 11 | 2023 | CVPR    | [GST](#1035)&ddagger; | **65.47** | **53.19** | **43.08** | **64.09** | **71.51** | **14.34** | [`[o-pytorch]`](https://github.com/gicheonkang/gst-visdial)


## Paper List

1. <span id = "1001">**[VisDial]**</span> | **CVPR'17** | Visual Dialog | [`[pdf]`](https://arxiv.org/pdf/1611.08669.pdf) | [`[o-torch]`](https://github.com/batra-mlp-lab/visdial)
2. <span id = "1002">**[GuessWhat]**</span> | **CVPR'17** | GuessWhat?! Visual object discovery through multi-modal dialogue | [`[pdf]`](https://arxiv.org/pdf/1611.08481.pdf) | [`[o-tensorflow]`](https://github.com/GuessWhatGame/guesswhat/)
3. <span id = "1003">**[HCIAE]**</span> | **NIPS'17** | Best of Both Worlds: Transferring Knowledge from Discriminative Learning to a Generative Visual Dialog Model | [`[pdf]`](https://arxiv.org/pdf/1706.01554.pdf) | [`[o-pytorch]`](https://github.com/jiasenlu/visDial.pytorch)
4. <span id = '1004'>**[AMEM]**</span> | **NIPS'17** | Visual Reference Resolution using Attention Memory for Visual Dialog | [`[pdf]`](https://proceedings.neurips.cc/paper_files/paper/2017/file/654ad60ebd1ae29cedc37da04b6b0672-Paper.pdf)
5. <span id = "1005">**[CoAtt]**</span> | **CVPR'18** | Are You Talking to Me? Reasoned Visual Dialog Generation through Adversarial Learning | [`[pdf]`](https://arxiv.org/pdf/1711.07613.pdf)
6. <span id = "1006">**[SF]**</span> | **CVPR'18** | Two Can Play This Game: Visual Dialog With Discriminative Question Generation and Answering | [`[pdf]`](https://arxiv.org/pdf/1803.11186.pdf)
7. <span id = "1007">**[A-ATT]**</span> | **CVPR'18** | Visual grounding via accumulated attention | [`[pdf]`](https://openaccess.thecvf.com/content_cvpr_2018/papers/Deng_Visual_Grounding_via_CVPR_2018_paper.pdf)
8. <span id = "1008">**[CorefNMN]**</span> | **ECCV'18** | Visual Coreference Resolution in Visual Dialog using Neural Module Networks | [`[pdf]`](https://arxiv.org/pdf/1809.01816.pdf)
9. <span id = "1009">**[VGNN]**</span> | **CVPR'19** | Reasoning Visual Dialogs with Structural and Partial Observations | [`[pdf]`](https://arxiv.org/pdf/1904.05548.pdf) | [`[o-pytorch]`](https://github.com/zilongzheng/visdial-gnn)
10. <span id = "1010">**[Sync]**</span> | **CVPR'19** | Image-Question-Answer Synergistic Network for Visual Dialog | [`[pdf]`](https://arxiv.org/pdf/1902.09774.pdf)
11. <span id = "1011">**[RvA]**</span> | **CVPR'19** | Recursive Visual Attention in Visual Dialog | [`[pdf]`](https://arxiv.org/pdf/1812.02664.pdf) | [`[o-pytorch]`](https://github.com/yuleiniu/rva)
12. <span id = "1024">**[FGA]**</span> | **CVPR'19** | Factor graph attention | [`[pdf]`](https://arxiv.org/pdf/1904.05880.pdf)
13. <span id = "1012">**[DVAN]**</span> | **IJCAI'19** | Dual Visual Attention Network for Visual Dialog | [`[pdf]`](https://www.ijcai.org/Proceedings/2019/0693.pdf)
14. <span id = "1013">**[DAN]**</span> | **EMNLP'19** | Dual Attention Networks for Visual Reference Resolution in Visual Dialog |[`[pdf]`](https://arxiv.org/pdf/1902.09368.pdf) | [`[o-pytorch]`](https://github.com/gicheonkang/DAN-VisDial)
15. <span id = "1014">**[HACAN]**</span> | **ICCV'19** | Making History Matter: History-Advantage Sequence Training for Visual Dialog | [`[pdf]`](https://arxiv.org/pdf/1902.09326.pdf)
16. <span id = "1015">**[ReDan]**</span> | **ACL'19** | Multi-step Reasoning via Recurrent Dual Attention for Visual Dialog | [`[pdf]`](https://arxiv.org/abs/1902.00579)
17. <span id = "1016">**[DMRM]**</span> | **AAAI'20** | DMRM: A Dual-channel Multi-hop Reasoning Model for Visual Dialog | [`[pdf]`](https://arxiv.org/pdf/1912.08360.pdf) | [`[o-pytorch]`](https://github.com/phellonchen/DMRM)
18. <span id = "1017">**[CDF]**</span> | **AAAI'20** | Modality-Balanced Models for Visual Dialogue | [`[pdf]`](https://arxiv.org/pdf/2001.06354.pdf)
19. <span id = "1018">**[DualVD]**</span> | **AAAI'20** | DualVD: An Adaptive Dual Encoding Model for Deep Visual Understanding in Visual Dialogue | [`[pdf]`](https://arxiv.org/pdf/1911.07251.pdf) | [`[o-pytorch]`](https://github.com/JXZe/DualVD)
20. <span id = "1019">**[P1+P2]**</span> | **CVPR'20** | Two Causal Principles for Improving Visual Dialog | [`[pdf]`](https://arxiv.org/pdf/1911.10496.pdf) | [`[o-pytorch]`](https://github.com/simpleshinobu/visdial-principles)
21. <span id = "1020">**[CAG]**</span> | **CVPR'20** | Iterative Context-Aware Graph Inference for Visual Dialog | [`[pdf]`](https://arxiv.org/pdf/2004.02194.pdf) |
22. <span id = "1021">**[DAM]**</span> | **IJCAI'20** | DAM: Deliberation, Abandon and Memory Networks for Generating Detailed and Non-repetitive Responses in Visual Dialogue | [`[pdf]`](https://arxiv.org/pdf/2007.03310.pdf) | [`[o-pytorch]`](https://github.com/JXZe/DAM)
23. <span id = "1022">**[KBGN]**</span> | **MM'20** | KBGN: Knowledge-Bridge Graph Network for Adaptive Vision-Text Reasoning in Visual Dialogue] | [`[pdf]`](https://arxiv.org/pdf/2008.04858.pdf)
24. <span id = "1023">**[Visdial-Bert]**</span> | **ECCV'20** | Large-scale Pretraining for Visual Dialog: A Simple State-of-the-Art Baseline] | [`[pdf]`](https://arxiv.org/pdf/1912.02379.pdf) | [`[o-pytorch]`](https://github.com/vmurahari3/visdial-bert)
25. <span id = "1025">**[LTMI]**</span> | **ECCV'20** | Efficient attention mechanism for visual dialog that can handle all the interactions between multiple inputs | [`[pdf]`](https://arxiv.org/pdf/1911.11390.pdf) | [`[o-pytorch]`](https://github.com/davidnvq/visdial)
26. <span id = "1026">**[MVAN]**</span> | **ACL'20** | Multi-View Attention Network for Visual Dialog | [`[pdf]`](https://arxiv.org/pdf/2004.14025.pdf) | [`[o-pytorch]`](https://github.com/taesunwhang/MVAN-VisDial)
27. <span id = "1027">**[MCA]**</span> | **ACL'20** | History for Visual Dialog: Do we really need it? | [`[pdf]`](https://aclanthology.org/2020.acl-main.728.pdf) |  [`[o-pytorch]`](https://github.com/shubhamagarwal92/visdial_conv)
28. <span id = "1028">**[VD-BERT]**</span> | **EMNLP'20** | VD-BERT: A Unified Vision and Dialog Transformer with BERT | [`[pdf]`](https://arxiv.org/pdf/2004.13278.pdf) |  [`[o-pytorch]`](https://github.com/salesforce/VD-BERT)
29.  <span id = "1029">**[MITVG]**</span> | **ACL'21** | Multimodal Incremental Transformer with Visual Grounding for Visual Dialogue Generation | [`[pdf]`](https://arxiv.org/pdf/2109.08478.pdf) 
30. <span id = "1030">**[SGLKT]**</span> | **EMNLP'21** | Reasoning Visual Dialog with Sparse Graph Learning and Knowledge Transfer | [`[pdf]`](https://arxiv.org/pdf/2004.06698.pdf) 
31. <span id = "1031">**[VU-BERT]**</span> | **ICASSP'22** | VU-BERT: A Unified framework for Visual Dialog | [`[pdf]`](https://arxiv.org/pdf/2202.10787.pdf)
32. <span id = "1032">**[ICMU]**</span> | **ICASSP'22** | Improving Cross-Modal Understanding in Visual Dialog via Contrastive Learning | [`[pdf]`](https://arxiv.org/pdf/2204.07302.pdf)
33. <span id = "1033">**[UTC]**</span> | **CVPR'22** | UTC: A Unified Transformer with Inter-Task Contrastive Learning for Visual Dialog | [`[pdf]`](https://arxiv.org/pdf/2205.00423.pdf)
34. <span id = "1034">**[AlignVD]**</span> | **MM'22** | Unsupervised and Pseudo-Supervised Vision-Language Alignment in Visual Dialog | [`[pdf]`](https://dl.acm.org/doi/pdf/10.1145/3503161.3547776)
35. <span id = "1035">**[GST]**</span> | **CVPR'23** | The Dialog Must Go On: Improving Visual Dialog via Generative Self-Training | [`[pdf]`](https://arxiv.org/pdf/2205.12502.pdf) | [`[o-pytorch]`](https://github.com/gicheonkang/gst-visdial)


## Feedback

If you have any suggestions or find missing papers, please feel free to contact me.

- [e-mail](mailto:chenmengyuan2021@ia.ac.cn)
- [pull request](https://github.com/MengyuanChen21/Awesome-Visual-Dialog/pulls)

