# ModelNet40-3D_Volumetric_Shapes_Dataset

### Paper: [3D ShapeNets: A Deep Representation for Volumetric Shapes](https://arxiv.org/pdf/1406.5670v3.pdf)
### DagsHub Repository: [ModelNet40-3D_Volumetric_Shapes_Dataset](https://dagshub.com/Rutam21/ModelNet40-3D_Volumetric_Shapes_Dataset)

![DagsHub Hacktoberfest Cover](https://user-images.githubusercontent.com/66431403/192983164-b3d6d556-ac69-4fb8-8aef-726a4386406a.png)

## About

The ModelNet40 dataset contains synthetic object point clouds. As the most widely used benchmark for point cloud analysis, ModelNet40 is popular because of its various categories, clean shapes, well-constructed dataset, etc. The original ModelNet40 consists of 12,311 CAD-generated meshes in 40 categories (such as airplane, car, plant, lamp), of which 9,843 are used for training while the rest 2,468 are reserved for testing. The corresponding point cloud data points are uniformly sampled from the mesh surfaces, and then further preprocessed by moving to the origin and scaling into a unit sphere.

3D shape is a crucial but heavily underutilized cue in object recognition, mostly due to the lack of a good generic shape representation. With the recent boost of inexpensive 2.5D depth sensors (e.g. Microsoft Kinect), it is even more urgent to have a useful 3D shape model in an object recognition pipeline. Furthermore, when the recognition has low confidence, it is important to have a fail-safe mode for object recognition systems to intelligently choose the best view to obtain extra observation from another viewpoint, in order to reduce the uncertainty as much as possible. To this end, it is proposed to represent a geometric 3D shape as a probability distribution of binary variables on a 3D voxel grid, using a Convolutional Deep Belief Network. The model naturally supports object recognition from 2.5D depth map, and view planning for object recognition.

![ModelNet Cover](https://vision.princeton.edu/projects/2014/3DShapeNets/teaser.jpg)

## Available Datasets

### Download 10-Class Orientation-aligned Subset

[ModelNet10.zip](http://3dvision.princeton.edu/projects/2014/3DShapeNets/ModelNet10.zip): This ZIP file contains CAD models from the 10 categories used to train the deep network in our 3D deep learning project. Training and testing split is included in the file. The CAD models are completely cleaned inhouse, and the orientations of the models (not scale) are manually aligned by ourselves.

### Download 40-Class Subset

[ModelNet40.zip](http://modelnet.cs.princeton.edu/ModelNet40.zip): This ZIP file contains CAD models from the 40 categories used to train the deep network in our 3D deep learning project. Training and testing split is included in the file. The CAD models are completely cleaned inhouse by ourselves. **[This Dataset is already added here in this repository.]**

### Download Aligned 40-Class Subset

[Aligned 40-Class](https://github.com/lmb-freiburg/orion): This data is provided by N. Sedaghat, M. Zolfaghari, E. Amiri and T. Brox authors of Orientation-boosted Voxel Nets for 3D Object Recognition.The CAD models are in Object File Format (OFF).

## Citation

If you find this dataset useful, please cite the following paper:

```	
Z. Wu, S. Song, A. Khosla, F. Yu, L. Zhang, X. Tang and J. Xiao
3D ShapeNets: A Deep Representation for Volumetric Shapes
Proceedings of 28th IEEE Conference on Computer Vision and Pattern Recognition (CVPR2015)
Oral Presentation ·  3D Deep Learning Project Webpage
```

## Copyright

All CAD models are downloaded from the Internet and the original authors hold the copyright of the CAD models. The label of the data was obtained by us via Amazon Mechanical Turk service and it is provided freely. This dataset is provided for the convenience of academic research only.
