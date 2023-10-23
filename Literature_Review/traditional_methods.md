
# Traditional Methods in Multi-View Stereo

Generally, traditional methods can be classified into four groups: voxel-based, surface-based, patch-based, and depth map-based methods.

## Table of Contents

- [Traditional Methods in Multi-View Stereo](#traditional-methods-in-multi-view-stereo)
  - [Table of Contents](#table-of-contents)
  - [](#)
    - [Massively parallel multiview stereopsis by surface normal diffusion (2015)](#massively-parallel-multiview-stereopsis-by-surface-normal-diffusion-2015)
    - [Structure-from-motion revisited (2016)](#structure-from-motion-revisited-2016)
    - [Multi-Scale Geometric Consistency Guided Multi-View Stereo (2019)](#multi-scale-geometric-consistency-guided-multi-view-stereo-2019)


## 



### Massively parallel multiview stereopsis by surface normal diffusion (2015) 
- **Paper Link**: [iccv_2015](https://www.cv-foundation.org/openaccess/content_iccv_2015/papers/Galliani_Massively_Parallel_Multiview_ICCV_2015_paper.pdf)

<!-- - **Method Name**: Methodology Name -->
- **Significance**: This paper introduced a parallel algorithm that significantly improved the results of MVS. (Patch-based)
- **Strengths**:
  - **Efficiency**: The massively parallel nature of the method allows for quick processing of multiple views, which is especially beneficial when dealing with large datasets.
  - **High-Quality Matching**: By iteratively refining the 3D planes, the method strives for high-quality multiview matching which is crucial for accurate 3D reconstruction.
  - **No Fronto-Parallel Bias**: The use of a slanted support window helps in avoiding fronto-parallel bias, which can be a common issue in stereo vision tasks.
- **Weaknesses**:
  - **Dependency on Initial Random Planes**: The method's performance might be affected by the initial random planes generated, which could lead to varying results.
  - **Complexity**: The iterative propagation and refinement process, although effective, might introduce complexity which could be a barrier for real-time applications.


### Structure-from-motion revisited (2016) 
- **Link**: [cvpr_2016](https://openaccess.thecvf.com/content_cvpr_2016/papers/Schonberger_Structure-From-Motion_Revisited_CVPR_2016_paper.pdf)
- **code**: [github colmap](https://github.com/colmap/colmap)
- **Strengths**:
    - (Patch-based)
    - consider the surface as a collection of patches
- **Weaknesses**:
    - The patch-based approach is sensitive to the choice of the patch size. The **patch size** should be large enough to contain sufficient texture information for matching, but small enough to ensure that the surface is locally planar.
    - **Incremental Strategy**: The technique relies on an incremental strategy which, while prevalent, may have inherent limitations when dealing with large or complex datasets.


### Multi-Scale Geometric Consistency Guided Multi-View Stereo (2019)
- **Link**: [CVPR_2019](https://openaccess.thecvf.com/content_CVPR_2019/papers/Xu_Multi-Scale_Geometric_Consistency_Guided_Multi-View_Stereo_CVPR_2019_paper.pdf)
- code: [github ACMM](https://github.com/GhiXu/ACMM)
- **Strengths**:
    - (Patch-based)
    - **Accurate Depth Map Estimation**: The method strives for accurate and complete depth map estimation, tackling challenges associated with low-textured areas through a multi-scale geometric consistency guidance approach
    - **Efficient Processing**: The Adaptive Checkerboard sampling and Multi-Hypothesis joint view selection mechanism is noted for leveraging structured region information, which optimizes candidate hypotheses sampling for propagation.
    - 
- **Weaknesses**:
    - **Complexity**: The method introduces multiple complex mechanisms like adaptive checkerboard sampling, multi-hypothesis joint view selection, and multi-scale geometric consistency guidance, which could potentially increase the complexity and computational demands of the method
    - **Error Propagation**: The method acknowledges the potential for error propagation from coarser to finer scales, necessitating the introduction of a detail restorer to mitigate this issue. This suggests that there could be a risk of error accumulation if not properly addressed​


























