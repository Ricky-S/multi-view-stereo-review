# Learning-Based Methods in Multi-View Stereo

This document collates a variety of learning-based methods employed in multi-view stereo (MVS), detailing each method's key attributes and contributions to the field.

## Table of Contents

- [Learning-Based Methods in Multi-View Stereo](#learning-based-methods-in-multi-view-stereo)
  - [Table of Contents](#table-of-contents)
    - [Learning stereo - introduction](#learning-stereo---introduction)
    - [MVSNet: Depth Inference for Unstructured Multi-View Stereo (ECCV\_2018)](#mvsnet-depth-inference-for-unstructured-multi-view-stereo-eccv_2018)
    - [Cascade cost volume for high-resolution multi-view stereo and stereo matching (CVPR\_2020)](#cascade-cost-volume-for-high-resolution-multi-view-stereo-and-stereo-matching-cvpr_2020)
    - [Normal Assisted Stereo Depth Estimation (CVPR\_2020)](#normal-assisted-stereo-depth-estimation-cvpr_2020)
    - [Rethinking Depth Estimation for Multi-View Stereo: A Unified Representation (CVPR\_2022)](#rethinking-depth-estimation-for-multi-view-stereo-a-unified-representation-cvpr_2022)
    - [TransMVSNet: Global Context-aware Multi-view Stereo Network with Transformers (CVPR\_2022)](#transmvsnet-global-context-aware-multi-view-stereo-network-with-transformers-cvpr_2022)
    - [Is-mvsnet: importance sampling-based mvsnet (ECCV\_2022)](#is-mvsnet-importance-sampling-based-mvsnet-eccv_2022)
    - [Multi-View Stereo Representation Revist: Region-Aware MVSNet (CVPR\_2023)](#multi-view-stereo-representation-revist-region-aware-mvsnet-cvpr_2023)
    - [NR-MVSNet: Learning Multi-View Stereo Based on Normal Consistency and Depth Refinement (TIP\_2023)](#nr-mvsnet-learning-multi-view-stereo-based-on-normal-consistency-and-depth-refinement-tip_2023)


<!-- ## Recent Methods -->

### Learning stereo - introduction
- **Link**: [Nail Ibrahimli - Doctoral Student, 3D Vision, July 27, 2022](https://3d.bk.tudelft.nl/nail/stereo/)
- **Link**: [Learning a Multi-View Stereo Machine Abhishek Kar, Sep 5, 2017](https://bair.berkeley.edu/blog/2017/09/05/unified-3d/)

### MVSNet: Depth Inference for Unstructured Multi-View Stereo (ECCV_2018)
- **Paper Link**: [ECCV_2018](https://openaccess.thecvf.com/content_ECCV_2018/papers/Yao_Yao_MVSNet_Depth_Inference_ECCV_2018_paper.pdf)
- code: [github MVSNet](https://github.com/YoYo000/MVSNet)
- [github MVSNet Pytorch](https://github.com/xy-guo/MVSNet_pytorch)
- **Method Name**: MVSNet
- **Description**: MVSNet is a novel deep learning architecture for multi-view stereo (MVS) problems. The method utilizes a convolutional neural network to infer depth maps from an input of multiple images. Unlike traditional MVS methods, MVSNet operates in a learned cost volume, demonstrating a differentiable approach to depth map inference and providing an end-to-end trainable framework for MVS.
- **Strengths**:
  - **End-to-End Trainability**: MVSNet's framework is end-to-end trainable, which facilitates learning from data and potentially improves the performance over traditional methods.
  - Utilization of **Deep Learning**: By employing deep learning, MVSNet can capture complex patterns and relationships in the data that may be difficult or impossible to model with traditional methods.
- **Weaknesses**:
  - **Computational Demand**: Deep learning methods like MVSNet tend to require significant computational resources, which might limit its applicability in resource-constrained environments.
  - **Dependency on Large Datasets**: The performance of MVSNet may be highly dependent on the availability of large, high-quality training datasets, which can be a limitation in scenarios where such data is scarce or unavailable.
- **Significance**: MVSNet represents a significant step towards employing deep learning in multi-view stereo, demonstrating the potential of learned cost volumes for depth inference. Its end-to-end trainable framework showcases the possibilities of integrating learning-based approaches in MVS, pushing the boundaries of what can be achieved in depth inference and 3D reconstruction from multiple views. This work lays a foundation for further explorations into deep learning-based MVS methods, inspiring subsequent research in this domain.


### Cascade cost volume for high-resolution multi-view stereo and stereo matching (CVPR_2020)
- **Paper Link**: [CVPR_2020](https://openaccess.thecvf.com/content_CVPR_2020/papers/Gu_Cascade_Cost_Volume_for_High-Resolution_Multi-View_Stereo_and_Stereo_Matching_CVPR_2020_paper.pdf)
- code: [github CasMVSNet](https://github.com/alibaba/cascade-stereo)
- **Method Name**: CasMVSNet
- **Description**: The Cascade Cost Volume method addresses the challenges faced by conventional deep multi-view stereo (MVS) and stereo matching approaches, which often struggle with high-resolution output due to the cubical increase in memory and time costs as volume resolution rises. Unlike these traditional approaches that construct 3D cost volumes to regularize and regress depth or disparity, this method introduces a memory and time-efficient cost volume formulation. It builds upon a feature pyramid, encoding geometry and context at gradually finer scales. By leveraging predictions from earlier stages, the method narrows the depth (or disparity) range at each stage, recovering the output in a coarser to finer manner, thus achieving high-resolution outputs efficiently.
- **Strengths**:
  - **Coarse-to-Fine Depth Recovery**: By employing a cascade structure, the method facilitates coarse-to-fine recovery of depth or disparity.
- **Weaknesses**:
  - **Complexity**: Deep learning methods like MVSNet tend to require significant computational resources, which might limit its applicability in resource-constrained environments.
  - **Dependency on Prior Stages**: The performance at each stage is dependent on the accuracy of predictions from prior stages, which could potentially propagate errors and affect the final output​1.
- **Results**:
  - **Benchmark Performance**:
    - **DTU Dataset**: 
    - **Tanks and Temples Benchmark**: 

| Metric       | Acc. (mm) | Comp. (mm) | Overall (mm) | GPU Mem (MB) | Run-time (s) |
|--------------|-----------|------------|--------------|--------------|--------------|
| Value        | 0.325     | 0.385      | 0.355        | 5345         | 0.492        |

| intermediate     | Mean | Family | Francis | Horse | Lighthouse | M60 | Panther | Playground | Train |
|--------------|------|--------|---------|-------|------------|-----|---------|------------|-------|
| Value        | 56.42|  76.36 |  58.45  | 46.20 |  55.53     |56.11|  54.02  |  58.17     | 46.56 |



### Normal Assisted Stereo Depth Estimation (CVPR_2020)
- **Paper Link**: [CVPR_2020](https://openaccess.thecvf.com/content_CVPR_2020/papers/Kusupati_Normal_Assisted_Stereo_Depth_Estimation_CVPR_2020_paper.pdf)
- code: [github PyTorch](https://github.com/udaykusupati/Normal-Assisted-Stereo)
- **Method Name**: 
- **Description**: Enforce the consistency between surface normal and depth at training time to improve performance. It introduces a multi-view normal estimation module and a multi-view depth estimation module, and proposes a novel consistency loss to train an independent consistency module that refines the depths from depth/normal pairs. The joint learning approach is highlighted to improve both the prediction of normal and depth, and further, the accuracy and smoothness are improved by enforcing the consistency. The joint learning approach and the proposed consistency loss present a robust method for refining depth estimates, improving accuracy and smoothness in depth prediction. 


### Rethinking Depth Estimation for Multi-View Stereo: A Unified Representation (CVPR_2022)
- **Paper Link**: [CVPR_2022](https://openaccess.thecvf.com/content/CVPR2022/papers/Peng_Rethinking_Depth_Estimation_for_Multi-View_Stereo_A_Unified_Representation_CVPR_2022_paper.pdf)
- code: [github](https://github.com/prstrive/UniMVSNet)
- **Method Name**: UniMVSNet
- **Description**: A new loss function called "Unified Focal Loss" is designed to address the challenges of sample imbalance. The paper introduces a coarse-to-fine framework termed UniMVSNet which employs the Unification representation and the Unified Focal Loss for optimization.
- **Weaknesses**:
  - **Complexity**:
- **Results**:
  - **Benchmark Performance**:
    - **DTU Dataset**: 
    - **Tanks and Temples Benchmark**: 

| Metric       | Acc. (mm) | Comp. (mm) | Overall (mm) |
|--------------|-----------|------------|--------------|
| Value        | 0.352     | 0.278      | 0.315        |

| Category    | int Mean | Fam. | Fra. | Hor. | Lig. | M60  | Pan. | Pla. | Tra. | adv Mean | Aud. | Bal. | Cou. | Mus. | Pal. | Tem. |
|-------------|------|------|------|------|------|------|------|------|------|------|------|------|------|------|------|------|
| Value       | **64.36**| 81.20| 66.43| 53.11| 63.46| 66.09| 64.84| 62.23| 57.53| **38.96**| 28.33| 44.36| 39.74| 52.89| 33.80| 34.63|


### TransMVSNet: Global Context-aware Multi-view Stereo Network with Transformers (CVPR_2022)
- **Paper Link**: [CVPR_2022](https://openaccess.thecvf.com/content/CVPR2022/papers/Ding_TransMVSNet_Global_Context-Aware_Multi-View_Stereo_Network_With_Transformers_CVPR_2022_paper.pdf)
- code: [github PyTorch](https://github.com/megvii-research/TransMVSNet)
- **Method Name**: TransMVSNet
- **Description**: Feature Matching Transformer (FMT) to leverage intra- (self-) and inter- (cross-) attention mechanisms to aggregate long-range context information within and across images. To facilitate better adaptation of the FMT, an Adaptive Receptive Field (ARF) module is employed to ensure a smooth transition in scopes of features, and different stages are bridged with a feature pathway to pass transformed features and gradients across different scales.
- **Weaknesses**:
  - **Complexity**:
- **Results**:
  - The batch size is 1 on 8 NVIDIA RTX
2080Ti GPUs and in total, the training phase takes about 16
hours and occupies 10GB memory of each GPU. 
  - **Benchmark Performance**:
    - **DTU Dataset**: 
    - **Tanks and Temples Benchmark**: 
  
| Metric       | Acc. (mm) | Comp. (mm) | Overall (mm) |
|--------------|-----------|------------|--------------|
| Value        | 0.321     | 0.289      | 0.305        |

| Category    | int Mean | Fam. | Fra. | Hor. | Lig. | M60  | Pan. | Pla. | Tra. | adv Mean | Aud. | Bal. | Cou. | Mus. | Pal. | Tem. |
|-------------|------|------|------|------|------|------|------|------|------|------|------|------|------|------|------|------|
value |**63.52**| 80.92| 65.83| 56.94| 62.54| 63.06| 60.00| 60.20| 58.67| **37.00**| 24.84| 44.59| 34.77| 46.49| 34.69| 36.62|



### Is-mvsnet: importance sampling-based mvsnet (ECCV_2022)
- **Paper Link**: [ECCV_2022](https://www.ecva.net/papers/eccv_2022/papers_ECCV/papers/136920663.pdf)
- code: [github](https://github.com/NoOneUST/IS-MVSNet)
- **Method Name**: IS-MVSNet
- **Description**: 
- **Weaknesses**:
  - **Complexity**:
- **Results**:
  - **Benchmark Performance**:
    - **DTU Dataset**: 
    - **Tanks and Temples Benchmark**:

| Metric       | Acc. (mm) | Comp. (mm) | Overall (mm) |
|--------------|-----------|------------|--------------|
| Value        | 0.351     | 0.359      | 0.355        |

| Category    | inter Mean | Fam. | Fra. | Hor. | Lig. | M60  | Pan. | Pla. | Tra. | adv Mean | Aud. | Bal. | Cou. | Mus. | Pal. | Tem. |
|-------------|------|------|------|------|------|------|------|------|------|------|------|------|------|------|------|------|
value |**62.82**| 79.92| 62.05| ..| ..|  |  | | | **34.87**| | | | | | |



### Multi-View Stereo Representation Revist: Region-Aware MVSNet (CVPR_2023)
- **Paper Link**: [CVPR_2023](https://openaccess.thecvf.com/content/CVPR2023/papers/Zhang_Multi-View_Stereo_Representation_Revist_Region-Aware_MVSNet_CVPR_2023_paper.pdf)
- code: [github not available]()
- **Method Name**: RA-MVSNet
- **Description**: 
- Introduce point-to-surface distance supervision of sampled points to expand the perception range predicted by the model, which achieves complete estimation in textureless areas and reduce outliers in object boundary regions.
- Tackle the challenge of lacking the ground-truth mesh, we compute the signed distance between point sets based on the triangulated mesh, which trades off
between accuracy and speed.
- **Weaknesses**:
  <!-- - **Complexity**: -->
- **Results**:
  - **Benchmark Performance**:
    - **DTU Dataset**: 
    - **Tanks and Temples Benchmark**:

| Metric       | Acc. (mm) | Comp. (mm) | Overall (mm) |
|--------------|-----------|------------|--------------|
| Value        | 0.326     | 0.268      | 0.297        |

| Method    | inter Mean | Fam. | Fra. | Hor. | Lig. | M60  | Pan. | Pla. | Tra. | adv Mean | Aud. | Bal. | Cou. | Mus. | Pal. | Tem. |
|-------------|------|------|------|------|------|------|------|------|------|------|------|------|------|------|------|------|
RA-MVSNet |**65.72**| | | ..| ..|  |  | | | **39.93**| | | | | | |



### NR-MVSNet: Learning Multi-View Stereo Based on Normal Consistency and Depth Refinement (TIP_2023)
- **Paper Link**: [IEEE Transactions on Image Processing](https://ieeexplore.ieee.org/abstract/document/10120723)
- code: [github](https://github.com/wdkyh/NR-MVSNet)
- **Method Name**: NR-MVSNet
<!-- - **Description**: 
- **Weaknesses**:
  - **Complexity**:
- **Results**:
  - **Benchmark Performance**:
    - **DTU Dataset**: 
    - **Tanks and Temples Benchmark**: -->


<!-- ### NR-MVSNet: Learning Multi-View Stereo Based on Normal Consistency and Depth Refinement
- **Paper Link**: [IEEE Transactions on Image Processing](https://ieeexplore.ieee.org/abstract/document/10120723)
- code: [github](https://github.com/wdkyh/NR-MVSNet)
- **Method Name**: NR-MVSNet -->



<!-- ### template (2020)
- **Paper Link**: [CVPR_2020]()
- code: [github]()
- **Method Name**: 
- **Description**: 
- **Weaknesses**:
  - **Complexity**:
- **Results**:
  - **Benchmark Performance**:
    - **DTU Dataset**: 
    - **Tanks and Temples Benchmark**:  -->