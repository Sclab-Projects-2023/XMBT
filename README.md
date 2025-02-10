# Multimodal Learning inspired by Multitask learning in Video Emotion Recognition

## Introduction

This is my on-going project. I use the idea of Multitask learning for Multimodal learning. In our proposed methods, we utilize the idea of multitask learning for multimodal learning. In multitask learning, a prediction of a task can improve the accuracy of the prediction of another task. For multimodal learning, we aim to use a prediction generated from a specific modal to enhance the prediction obtained from another modal or a prediction of the late-fusion production.

![frameworks](./img/frameworks.jpg)


## Dataset

We conducted the experiments on the reorganized IEMOCAP and CMU-MOSEI provided by [Dai](https://aclanthology.org/2021.naacl-main.417/), and the [CH-SIMS dataset](https://aclanthology.org/2020.acl-main.343/). The preprocessed IEMOCAP and CMU-MOSEI can be downloaded [here](https://github.com/wenliangdai/Multimodal-End2end-Sparse). The CH-SIMS and its baseline can be found [here](https://github.com/thuiar/MMSA). For all datasets, we used the MTCNN to extract facial images and resized to 260x260.

## Environment

* timm 0.4.5

## Results

Test results on IEMOCAP

| Model | Ang_Ac | Ang_F1 | Exc_Ac | Exc_F1 | Fru_Ac | Fru_F1 | Hap_Ac | Hap_F1 | Neu_Ac | Neu_F1 | Sad_Ac | Sad_F1 | Avg_Ac | Avg_F1 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Audio | 82.1 | 46.2 | 55.0 | 30.3 | 45.4 | 42.4 | 12.8 | 17.2 | 48.6 | 41.4 | 77.9 | 48.8 | 53.6 | 37.7 |
| Visual | 80.9 | 53.8 | 84.3 | 56.3 | 68.3 | 53.9 | 90.1 | 43.7 | 75.1 | 55.3 | 86.6 | 55.8 | 80.9 | 53.1 |
| Text | 86.0 | 57.9 | 86.8 | 56.8 | 70.1 | 54.7 | 90.1 | 40.5 | 73.5 | 49.0 | 87.0 | 58.0 | 82.2 | 52.8 |
| LF-LSTM | 71.2 | 49.4 | 79.3 | 57.2 | 68.2 | 51.5 | 67.2 | 37.6 | 66.5 | 47.0 | 78.2 | 54.0 | 71.8 | 49.5 |
| LF-Trans | 81.9 | 50.7 | 85.3 | 57.3 | 60.5 | 49.3 | 85.2 | 37.6 | 72.4 | 49.7 | 87.4 | 57.4 | 78.8 | 50.3 |
| EmoEmbs | 65.9 | 48.9 | 73.5 | 58.3 | 68.5 | 52.0 | 69.6 | 38.3 | 73.6 | 48.7 | 80.8 | 53.0 | 72.0 | 49.8 |
| MulT | 77.9 | 60.7 | 76.9 | 58.0 | 72.4 | 57.0 | 80.0 | 46.8 | 74.9 | 53.7 | 83.5 | 65.4 | 77.6 | 56.9 |
| BIMHA | 77.2 | 57.6 | 78.3 | 56.1 | 73.9 | 54.2 | 83.4 | 43.2 | 76.4 | 50.9 | 83.8 | 63.7 | 78.8 | 54.3 |
| CMHA | 88.6 | 61.1 | 87.9 | 60.5 | 75.1 | 56.3 | 89.0 | 45.8 | 76.5 | 51.2 | 88.3 | 61.6 | 84.3 | 56.1 |
| MESE | 88.2 | 62.8 | 88.3 | 61.2 | 74.9 | 58.4 | 89.5 | 47.3 | 77.0 | 52.0 | 88.6 | 62.2 | 84.4 | 57.4 |
| FE2E | 88.7 | 63.9 | 89.1 | 61.9 | 71.2 | 57.8 | 90.0 | 44.8 | 79.1 | 58.4 | 89.1 | 65.7 | 85.7 | 57.1 |
| Le et al | **90.1** | 66.8 | 88.5 | 66.8 | 77.7 | 57.0 | **90.5** | 48.5 | 78.1 | 56.6 | 90.7 | 69.6 | 85.9 | 60.9 |
| Ours | 89.5 | **67.8** | **90.8** | **70.7** | **78.9** | **59.9** | 89.9 | **55.5** | **79.1** | **60.6** | **91.4** | **72.9** | **86.6** | **64.6** |

Test results on MOSEI

| Model | Ang_Wa | Ang_F1 | Dis_Wa | Dis_F1 | Fea_Wa | Fea_F1 | Hap_Wa | Hap_F1 | Sad_Wa | Sad_F1 | Sur_Wa | Sur_F1 | Sur_Wa | Sur_F1 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Audio | 53.9  | 40.5  | 61.0  | 35.7  | 59.0  | 19.6  | 50.0  | 69.3  | 61.2  | 45.8  | 58.4  | 21.7  | 57.2  | 38.8 |
| Visual | 58.9  | 38.2  | 63.2  | 37.6  | 59.1  | 21.8  | 55.7  | 70.3  | 56.2  | 42.8  | 53.0  | 17.9  | 57.7  | 38.1 |
| Text | 65.9  | 48.4  | 74.0  | 56.0  | 62.8  | 27.0  | 62.3  | 72.0  | 60.2  | 45.3  | 60.9  | 26.0  | 64.3  | 45.8 |
| LF-LSTM | 64.5  | 47.1  | 70.5  | 49.8  | 61.7  | 22.2  | 61.3  | 73.2  | 63.4  | 47.2  | 57.1  | 20.6  | 63.1  | 43.3 |
| LF-Trans | 65.3  | 47.7  | 74.4  | 51.9  | 62.1  | 24.0  | 60.6  | 72.9  | 60.1  | 45.5  | 62.1  | 24.2  | 64.1  | 44.4 |
| EmoEmbs | 66.8  | 49.4  | 69.6  | 48.7  | 63.8  | 23.4  | 61.2  | 71.9  | 60.5  | 47.5  | 63.3  | 24.0  | 64.2  | 44.2 |
| MulT] | 64.9  | 47.5  | 71.6  | 49.3  | 62.9  | 25.3  | 67.2  | 75.4  | 64.0  | 48.3  | 61.4  | 25.6  | 65.4  | 45.2 |
| BIMHA | 65.3  | 47.4  | 70.5  | 48.9  | 61.8  | 24.7  | 65.8  | 72.1  | 62.6  | 47.9  | 62.5  | 24.9  | 64.8  | 44.3 |
| CMHA | 65.9  | 49.1  | 73.6  | 53.2  | 63.4  | 27.3  | 65.2  | 72.1  | 64.2  | 46.7  | 64.5  | 26.6  | 66.1  | 45.8 |
| MESE | 66.8  | 49.3  | 75.6  | 56.4  | 65.8  | 28.9  | 64.1  | 72.3  | 63.0  | 46.6  | 65.7  | 27.2  | 66.8  | 46.8 |
| FE2E | 66.9  | 49.5  | 75.4  | 57.2  | 63.8  | 27.1  | 61.9  | 72.3  | **65.6**  | 49.3  | 61.5  | 26.9  | 65.8  | 47.0 |
| Le et al | 67.5  | 50.2  | 76.3  | 57.0  | 69.0  | 29.0  | 63.0  | 72.6  | 65.5  | 49.2  | 65.7  | 27.6  | 67.8  | 47.6 |
| Ours | **71.4**  | **52.6**  | **81.4**  | **57.4**  | **80.5**  | **30.2**  | **68.5**  | **75.4**  | 63.9  | **51.6**  | **80.3**  | **30.3**  | **74.3**  | **49.6** |

Test results on CH-SIMS

| Model | Annotation | Acc2 | F1 | MAE | Corr |
| --- | --- | --- | --- | --- | --- |
| EF-LSTM | M | 69.37  | 81.91  | 59.34  | -4.39 |
| MFN | M | 77.86  | 78.22  | 45.19  | 55.18 |
| MulT | M | 77.94  | 79.10  | 48.45  | 55.94 |
| LF-DNN | M | 79.87  | 80.20  | 42.01  | 61.23 |
| MLF-DNN | M, A, T, V | 82.28  | 82.52  | 40.64  | 67.47 |
| LMF | M | 79.34  | 79.96  | 43.99  | 60.00 |
| MLMF | M, A, T, V | 82.32  | 82.66  | 42.03  | 63.13 |
| TFN | M | 80.66  | 81.62  | 42.52  | 61.18 |
| MTFN | M, A, T, V | 82.45  | 82.56  | 40.66  | 66.98 |
| Self-MM | M, A, T, V | 80.74 | 80.78 | 41.90 | 61.60|
| Human-MM | M, A, T, V | 81.32 | 81.73 | 40.80 | 64.70|
| Ours | M, A, T, V | **83.37** | **83.15** | **37.61** | **68.04** |


## Citation
- It will be updated.



