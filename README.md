# Edge_Inference_three-step_framework
This code is for the [paper](https://arxiv.org/abs/2006.02166): "communication-computation tradeoffs in resource-constrained edge inference".


## Implementation

The three-step framework is implemented based on the ResNet18. The network is splitted at the end of each building block.

### Dependency

```
Pytorch 1.6.0
Torchvision 0.7.0
Numpy 1.6.12
```

### Dataset

```
CIFAR-10
```
### How to Run

0. Pretrain a ResNet model from the scratch or download from [here](https://github.com/shaojiawei07/some_model)
1. `model_pruning.py` uses magnitude-based pruning method to compress the on-device model with parameter `-sp1`, `-sp2`, `-sp3`, `-sp4`, and `-sp5` to denote the SParsity ratios in different building blocks. A pruned model is achieved named `sp1_xx_sp2_xx_sp3_xx_sp4_xx_test_acc_xxxx`.
2. `feature_compression.py` compresses the intermediate feature, which loads the pruned model by `-load`, and select the split point by `-split`.


## Citation

```
@article{shao2020communication,
  title={Communication-Computation Trade-Off in Resource-Constrained Edge Inference},
  author={Shao, Jiawei and Zhang, Jun},
  journal={arXiv preprint arXiv:2006.02166},
  year={2020}
}
```






