# Learning-Based Methods in Multi-View Stereo

This document collates a variety of learning-based methods employed in multi-view stereo (MVS), detailing each method's key attributes and contributions to the field.

## Table of Contents

- [Learning-Based Methods in Multi-View Stereo](#learning-based-methods-in-multi-view-stereo)
  - [Table of Contents](#table-of-contents)
    - [MVSNet: Depth Inference for Unstructured Multi-View Stereo (2018)](#mvsnet-depth-inference-for-unstructured-multi-view-stereo-2018)
    - [Cascade cost volume for high-resolution multi-view stereo and stereo matching (2020)](#cascade-cost-volume-for-high-resolution-multi-view-stereo-and-stereo-matching-2020)


<!-- ## Recent Methods -->

### MVSNet: Depth Inference for Unstructured Multi-View Stereo (2018)
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


### Cascade cost volume for high-resolution multi-view stereo and stereo matching (2020)
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
