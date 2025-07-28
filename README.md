# Group-3: Crowd Counting Models: Research Report 📊

A comprehensive study of modern crowd counting approaches from traditional methods to state-of-the-art deep learning models.

##  What is Crowd Counting?

Crowd counting estimates the number of people in images/video frames - critical for public safety, urban planning, event management, and surveillance applications.

**Why specialized methods?** Traditional object detection (like YOLO) fails in dense crowds due to occlusion and scale variations:

| Method | ShanghaiTech A (MAE) | ShanghaiTech B (MAE) |
|--------|---------------------|---------------------|
| YOLOv8 | 428.2 | 102.4 |
| Specialized Models | ~50-60 | ~6-15 |

## Evolution Timeline

### 1. Pre-Deep Learning (2000-2015)
- **Detection-Based**: Haar Wavelets + SVM, HOG + SVM
- **Regression-Based**: Ridge Regression, Random Forest

### 2. Early Deep Learning (2015-2018)
- **CNN Density Estimation**: MCNN, CSRNet

### 3. Modern Approaches (2019-Present)
- **Attention & Transformers**: SANet, CCTrans, CrowdCLIP
- **Density Matching**: DM-Count, CHSNet
- **Advanced Supervision**: MPS, Crowd-Diff

##  Team Members & Contributions

| Member | Affiliation | Models Studied | Key Contributions |
|--------|-------------|----------------|-------------------|
| **Harshit Singh Mehta** | IIIT Hyderabad | DM-Count | Implemented distribution matching approach, cross-dataset evaluation |
| **Vibhu Nimalan Bharti** | IIIT Hyderabad | CCTrans | Transformer-based architecture analysis, global context modeling |
| **Abhinav Venkata Kota** | IIIT Hyderabad | MPS, CrowdCLIP | Multitask supervision & unsupervised learning implementation |
| **Vidvathama** | IIIT Hyderabad | CrowdDiff | Diffusion model implementation, multi-hypothesis estimation |

##  Models Studied

### 1. DM-Count: Distribution Matching
**By Harshit Singh Mehta**

- **Innovation**: Replaces Gaussian smoothing with Optimal Transport (OT)
- **Performance**: 16% MAE improvement on UCF-QNRF and NWPU
- **Key Feature**: Stabilized by Total Variation (TV) loss

**Results:**
| Dataset | MAE | MSE |
|---------|-----|-----|
| ShanghaiTech A | 59.7 | 95.7 |
| ShanghaiTech B | 7.4 | 11.8 |

### 2. CCTrans: Transformer-Based Counting  
**By Vibhu Nimalan Bharti**

- **Innovation**: First to use transformer for global context in crowd counting
- **Architecture**: Pyramid Vision Transformer + Feature Aggregation + Regression Head
- **Advantage**: Captures both local and global features

**Results:**
| Dataset | MAE | MSE |
|---------|-----|-----|
| ShanghaiTech A | 52.3 | 84.9 |
| ShanghaiTech B | 6.2 | 9.9 |
| UCF-QNRF | 82.8 | 142.3 |

### 3. MPS: Multitask Point Supervision
**By Abhinav Venkata Kota**

- **Innovation**: Simultaneous counting and localization using point annotations
- **Advantage**: No density map overhead, direct point learning
- **Features**: Multi-scale fusion, dual task heads

**Results:**
| Dataset | MAE | MSE | AP@5px |
|---------|-----|-----|--------|
| ShanghaiTech A | 110.7 | 157.3 | 0.71 |
| ShanghaiTech B | 15.0 | 21.4 | 0.75 |

### 4. CrowdCLIP: Unsupervised Learning
**By Abhinav Venkata Kota**

- **Innovation**: Zero-annotation crowd counting using CLIP vision-language model
- **Method**: Progressive patch filtering + count estimation
- **Breakthrough**: 35.2% improvement over previous unsupervised methods

**Results:**
| Dataset | MAE | Supervision |
|---------|-----|-------------|
| UCF-QNRF | 283.3 | Unsupervised |
| ShanghaiTech A | 146.1 | Unsupervised |

### 5. CrowdDiff: Diffusion-Based Approach
**By Vidvathama**

- **Innovation**: First diffusion model for crowd counting
- **Features**: Multi-hypothesis density estimation, narrow-kernel compatibility
- **Advantage**: Superior fine-grained spatial statistics

**Results:**
| Dataset | MAE | MSE |
|---------|-----|-----|
| ShanghaiTech A | 47.4 | 75.0 |
| ShanghaiTech B | 5.7 | 8.2 |
| UCF-QNRF | 68.9 | 125.6 |
| NWPU | 57.8 | 221.2 |

##  Performance Summary

| Model | Best Dataset Performance | Key Innovation |
|-------|-------------------------|----------------|
| **CrowdDiff** | 47.4 MAE (SHA) | Diffusion-based generation |
| **CCTrans** | 52.3 MAE (SHA) | Transformer global context |
| **DM-Count** | 59.7 MAE (SHA) | Optimal transport matching |
| **CrowdCLIP** | 146.1 MAE (SHA) | Unsupervised learning |
