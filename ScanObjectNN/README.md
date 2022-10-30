# ScanObjectNN-Real-World_Dataset_of_3D_Objects

### Paper: [Revisiting Point Cloud Classification: A New Benchmark Dataset and Classification Model on Real-World Data](https://arxiv.org/pdf/1908.04616v2.pdf)
### DagsHub Repository: [ScanObjectNN-Real-World_Dataset_of_3D_Objects](https://dagshub.com/Rutam21/ScanObjectNN-Real-World_Dataset_of_3D_Objects)

![DagsHub Hacktoberfest Cover](https://user-images.githubusercontent.com/66431403/192983164-b3d6d556-ac69-4fb8-8aef-726a4386406a.png)

## About
This work revisits the problem of point cloud classification but on real world scans as opposed to synthetic models such as ModelNet40 that were studied in other recent works. We introduce ScanObjectNN, a new benchmark dataset containing ~15,000 object that are categorized into 15 categories with 2902 unique object instances. The raw objects are represented by a list of points with global and local coordinates, normals, colors attributes and semantic labels. We also provide part annotations, which to the best of our knowledge is the first on real-world data. From our comprehensive benchmark, we show that our dataset poses great challenges to existing point cloud classification techniques as objects from real-world scans are often cluttered with background and/or are partial due to occlusions.

## ScanObjectNN Dataset
We provide different variants of our scan dataset namely: OBJ_BG, PB_T25, PB_T25_R, PB_T50_R and PB_T50_RS as described in our paper. We released both the processed .h5 files and the raw .bin objects as described below.

### h5 files
- Download the h5_files.zipped to obtained all the h5 files. Main split was used for the experiments in the main paper, while splits 1-4 are the additional training/test splits reported in our supplementary material.
- The pre-processed h5 files can be directly used by deep learning frameworks, containing fields:
    - data: Nx3 point cloud
    - label: class label
    - mask: indicator whether each point is part of the object instance or the background.
- Each object contained 2048 points, where each point is represented by its x, y, z coordinates.
- We first ensured that a data sample had at least 2048 object instance points (excluding the background) before 2048 points were randomly selected (including the background points) and included into the h5 file. For the *_nobg h5 files, background points were first filtered out before the random selection.
- Naming convention: Prefixes are training_* and test_* for training set and test set, respectively.
    - OBJ_BG / OBJ_ONLY: *objectdataset.h5
    - PB_T25: *objectdataset_augmented25_norot.h5
    - PB_T25_R: *objectdataset_augmented25rot.h5
    - PB_T50_R: *objectdataset_augmentedrot.h5
    - PB_T50_RS: *objectdataset_augmentedrot_scale75.h5

### Raw files

We release all the raw object files of our ScanObjectNN dataset including all its variants.

- To obtain the files, download the zipped files of each corresponding variant. object_dataset.zip refers to the unaugmented variant (OBJ_BG).
- The list of all objects can be found at training_data/object_labels.txt. The format per line is (separated by '\t'):
```
scene_folder    object_id    object_class    object_instance_label
```
- The object .bin files are located at [object_class]/[scene_folder]_[object_id].bin in the dataset folder.
- Each .bin file is a series of float32. The first float represents the total number of points in the object instance. Then every succeeding set of 11 floats represent the attributes of each point. (ie if there are m points in the point cloud, then there are (11m + 1) floats in the .bin file)
- The attributes of each point are listed in the following order:
```
x    y    z    nx    ny    nz    r    g    b    instance_label    semantic_label
```
- We generated training and test split files located in training_data/, where 't' in each line of the text file indicates that the object is part of the test split.

**Parts:**

- V0 of the raw files with complete parts can be found in object_dataset_complete_with_parts.zip **[This Object Dataset has been already added in this repository.]**. Corresponding part labels can be found in the xml files located in training_data/part_labels/.

## Citation
```
@inproceedings{uy-scanobjectnn-iccv19,
      title = {Revisiting Point Cloud Classification: A New Benchmark Dataset and Classification Model on Real-World Data},
      author = {Mikaela Angelina Uy and Quang-Hieu Pham and Binh-Son Hua and Duc Thanh Nguyen and Sai-Kit Yeung},
      booktitle = {International Conference on Computer Vision (ICCV)},
      year = {2019}
  }
 ```

## Acknowledgements

We would like to sincerely thank Tan Sang Ha, Fan Wai Shan, Xu Ting Ting, Loh Pei Huan, Luong Van An, Ng Shi Xian Bryden, Li Jingxin and Chiz Huang for helping in the part annotations.

This research project is partially supported by an internal grant from HKUST (R9429).
