# PointCloud-C
## [DagsHub repo](https://dagshub.com/prabhanjan-jadhav/PointCloud-C)
- Benchmarking and Analyzing Point Cloud Robustness under Corruptions.

Overview

3D perception, especially point cloud classification and part segmentation, has achieved substantial progress. However, in real-world deployment, point cloud corruptions are inevitable due to the scene complexity, sensor inaccuracy, and processing imprecision. In this work, we contribute ModelNet-C and ShapeNet-C, aiming at rigorously benchmarking and analyzing point cloud robustness under various real-world corruptions.

Scale & Features

The very first test-suite for point cloud robustness analysis under corruptions.
Two sets: ModelNet-C for point cloud classification and ShapeNet-C for part segmentation.
Real-world corruption sources, ranging from object-, senor-, and processing-levels.
Seven types of corruptions, each with five severity levels.

Taxonomy

The corruption taxonomy unified into seven fundamental atomic corruptions: “Add Global”, “Add Local”, “Drop Global”, “Drop Local”, “Rotate”, “Scale” and “Jitter”. Consequently, each real-world corruption is broken down into a combination of the atomic corruptions. In addition, there are five severity levels for each corruption, based on which random sampling is done from the atomic operations to form a composite corruption test set. The detailed description and implementation can be found in
the research papers.

## Dataset Structure
```
root
 └─── modelnet_c
         └───── add_global_0.h5
         └───── ...
         └───── add_local_0.h5
         └───── ...
         └───── dropout_global_0.h5
         └───── ...
         └───── dropout_local_0.h5
         └───── ...
         └───── jitter_0.h5
         └───── ...
         └───── rotate_0.h5
         └───── ...
         └───── scale_0.h5
         └───── ...
         └───── clean.h5
 └─── README.txt
```
 
```
 root
 └─── shapenet_c
         └───── add_global_0.h5
         └───── ...
         └───── add_local_0.h5
         └───── ...
         └───── dropout_global_0.h5
         └───── ...
         └───── dropout_local_0.h5
         └───── ...
         └───── jitter_0.h5
         └───── ...
         └───── rotate_0.h5
         └───── ...
         └───── scale_0.h5
         └───── ...
         └───── clean.h5
 └─── README.txt
```
 
 ## Citations:
 
 ```
@ARTICLE{ren2022pointcloud-c,
  title={Benchmarking and Analyzing Point Cloud Robustness under Corruptions},
  author={Jiawei Ren and Lingdong Kong and Liang Pan and Ziwei Liu},
  journal={arXiv:220x.xxxxx},
  year={2022}
}
```
```
@ARTICLE{ren2022modelnet-c,
  title={Benchmarking and Analyzing Point Cloud Classification under Corruptions},
  author={Jiawei Ren and Liang Pan and Ziwei Liu},
  journal={International Conference on Machine Learning (ICML)},
  year={2022}
}
```
 
## License : https://creativecommons.org/licenses/by-nc-sa/4.0/legalcode
This benchmark is made freely available to academic and non-academic entities for non-commercial purposes such as academic research, teaching, scientific publications, or personal experimentation. Permission is granted to use the data given that you agree:

That the benchmark comes “AS IS”, without express or implied warranty. Although every effort has been made to ensure accuracy, we do not accept any responsibility for errors or omissions.
That you may not use the benchmark or any derivative work for commercial purposes as, for example, licensing or selling the data, or using the data with a purpose to procure a commercial gain.
That you include a reference to PointCloud-C (including ModelNet-C, ShapeNet-C, and the specially generated data for academic challenges) in any work that makes use of the benchmark. For research papers, please cite our preferred publications as listed on our webpage.
