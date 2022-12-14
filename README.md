## Integrative Solution for Catastrophic Forgetting in Data-Free Class Incremental Learning
**Integrative Solution for Catastrophic Forgetting in Data-Free Class Incremental Learning**\
Yujin Kim, Minsoo Kang, **_Junsu Kim_**, Suhyun Kim


<p align="center">
<img src="ISCF_arch.png" width="100%">
</p>

## Abstract
Data-Free Class Incremental Learning (DFCIL) scenario en- ables the model to continually learn without accessing old data, which prevents the training process from violating data privacy. However, we observe that previous DFCIL ap- proaches still severely suffer from catastrophic forgetting caused by the class imbalance problem. To overcome catas- trophic forgetting from class imbalance, we introduce Inte- grative Solution for Catastrophic Forgetting (ISCF), a novel DFCIL framework consisting of Weight Equalizer (WEQ) and the combined knowledge distillation approach. We firstly propose Weight Equalizer (WEQ) to solve the class imbal- ance issue by correcting biased weights toward new classes in the classification head. WEQ makes the weight norms of the current linear head follow the average of weight norms in the previous training step. Furthermore, we suggest exploiting Similarity Preserving Knowledge Distillation (SPKD) with Logit Knowledge Distillation (LKD) that distills the features of intermediate layers and representations of the previous lin- ear head to gain more stability (i.e., not to forget previous knowledge). Extensive experiments on CIFAR-100 and Tiny- ImageNet demonstrate significant accuracy improvement of our proposed method over previous works. We also show that our proposed method largely remains the previously learned knowledge compared to the existing methods

## Installation

### Prerequisites
* python == 3.8
* torch == 1.8.2
* torchvision == 0.9.2

### Setup
 * `conda env create -f ISCF.yaml`

## Training
```bash
sh experiments/cifar100-fivetask.sh
sh experiments/cifar100-tentask.sh
sh experiments/cifar100-twentytask.sh
```
## Results

### CIFAR-100 (no coreset)
tasks | 5 | 10 | 20
--- | --- | --- | ---
UB | 69.9 ± 0.2 | 69.9 ± 0.2 | 69.9 ± 0.2
Base | 16.4 ± 0.4 | 8.8 ± 0.1 | 4.4 ± 0.3
LwF | 17.0 ± 0.1 | 9.2 ± 0.0 | 4.7 ± 0.1
DGR | 14.4 ± 0.4 | 8.1 ± 0.1 | 4.1 ± 0.3
DI | 18.8 ± 0.3 | 10.9 ± 0.6 | 5.7 ± 0.3
ABD | 43.9 ± 0.9 | 33.7 ± 1.2 | 20.0 ± 1.4
Ours | 47.56 ± 0.15 | 39.01 ± 0.08 | 21.24 ± 1.84