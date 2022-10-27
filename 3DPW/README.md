# 3D POSES IN THE WILD DATASET
### Paper: [Recovering Accurate 3D Human Pose in The Wild Using IMUs and a Moving Camera](http://openaccess.thecvf.com/content_ECCV_2018/papers/Timo_von_Marcard_Recovering_Accurate_3D_ECCV_2018_paper.pdf)
### DagsHub Repository: [3DPW-3D_Pose_Data](https://dagshub.com/Rutam21/3DPW-3D_Pose_Data)

![DagsHub Hacktoberfest Cover](https://user-images.githubusercontent.com/66431403/192983164-b3d6d556-ac69-4fb8-8aef-726a4386406a.png)


The 3D Poses in the Wild dataset is the first dataset in the wild with accurate 3D poses for evaluation. While other datasets outdoors exist, they are all restricted to a small recording volume. 3DPW is the first one that includes video footage taken from a moving phone camera.


The dataset includes:

- 60 video sequences.
- 2D pose annotations.
- 3D poses obtained with the method introduced in the paper.
- Camera poses for every frame in the sequences.
- 3D body scans and 3D people models (re-poseable and re-shapeable). Each sequence contains its corresponding models.
- 18 3D models in different clothing variations.

## 3DPW Dataset

The 3DPW dataset contains several motion sequences, which are organized into two folders: imageFiles and sequenceFiles.
The folder imageFiles contains the RGB-images for every sequence. 
The folder sequenceFiles provides synchronized motion data and SMPL model parameters in the form of .pkl-files. For each sequence, the .pkl-file contains a dictionary with the following fields:
- sequence: String containing the sequence name
- betas: SMPL shape parameters for each actor which has been used for tracking (List of 10x1 SMPL beta parameters)
- poses: SMPL body poses for each actor aligned with image data (List of Nx72 SMPL joint angles, N = #frames)
- trans: tranlations for each actor aligned with image data (List of Nx3 root translations)
- poses_60Hz: SMPL body poses for each actor at 60Hz (List of Nx72 SMPL joint angles, N = #frames)
- trans_60Hz: tranlations for each actor at 60Hz (List of Nx3 root translations)
- betas_clothed: SMPL shape parameters for each clothed actor (List of 10x1 SMPL beta parameters)
- v_template_clothed: 
- gender: actor genders (List of strings, either 'm' or 'f')
- texture_maps: texture maps for each actor
- poses2D: 2D joint detections in Coco-Format for each actor (only provided if at least 6 joints were detected correctly)
- jointPositions: 3D joint positions of each actor (List of Nx(24*3) XYZ coordinates of each SMPL joint)
- img_frame_ids: an index-array to down-sample 60 Hz 3D poses to corresponding image frame ids
- cam_poses: camera extrinsics for each image frame (Ix4x4 array, I frames times 4x4 homegenous rigid body motion matrices)
- campose_valid: a boolean index array indicating which camera pose has been aligned to the image
- cam_intrinsics: camera intrinsics (K = [f_x 0 c_x;0 f_y c_y; 0 0 1])

Each sequence has either one or two models, which corresponds to the list size of the model specific fields (e.g. betas, poses, trans, v_template, gender, texture_maps, jointPositions, poses2D). 
SMPL poses and translations are provided at 30 Hz. They are aligned to image dependent data (e.g. 2D poses, camera poses). In addition we provide 'poses_60Hz' and 'trans_60Hz' which corresponds to the recording frequency of 60Hz of the IMUs . You could use the 'img_frame_ids' to downsample and align 60Hz 3D and image dependent data, wich has been done to compute SMPL 'poses' and 'trans' variables. 
Please refer to the demo.py-file for loading a sequence, setup smpl-Models and camera, and to visualize an example frame.

## Evaluation
This dataset may be used for different tasks. If you use the dataset to evaluate human pose and shape estimation, please look at the protocols and metrics below.

## Protocols
The data in sequenceFiles.zip contains the sequences separated in three folders: train/, validation/, test/. In order to be able to compare different methods, we define the following evaluation protocols.
- **All-Test-mode**: All the dataset is used as test (including the test/, train/, validation/ folders).
- **Train-Test-mode**: In this mode, methods can train on the train/, validate on the validation/, and report results on the test/.
- **Validation-mode**: In this mode, the sequences in validation/ can be used for validation (NOT TRAINING). The data in folders (train/, test/) can be used for testing.
- **All-Train-mode**: Obviously, the dataset can be used exclusively for training if methods are tested on other data.

Please, when you report results, indicate which of the above protocols you use.

## Metrics
We strongly encourage you to report some or all of the following metrics in your report:

- **Joint error metric**: mean Euclidean distance between predicted joints and the joints of SMPL.
- **Mesh error metric**: mean Euclidean distance between predicted 3D mesh and SMPL ground truth mesh (with clothing and/or without clothing). This metric should be used for methods estimating shape as well as pose.
- **Mesh error metric unposed**: mean Euclidean distance between predicted 3D mesh and SMPL ground truth mesh in the zero pose space, that is setting the pose of SMPL to zero (with clothing or/and without clothing). This metric allows to evaluate shape accuracy independently of pose accuracy.
- **Orientation error metric**: mean geodesic distance between predicted part rotations and ground truth part rotations. See von Marcard et al. 2017, 2018.

**PROCRUSTES**: Many methods do procrustes alignment before computing the error. We recommend reporting the result using Procrustes alignment (root orientatio, translation and scale) and without.

## Requirements
To run the example scripts, you will need the following:

- Numpy & Scipy
- Chumpy
- OpenCV (2)
- OpenDR
- SMPL


