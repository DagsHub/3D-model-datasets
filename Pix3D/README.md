# Pix3D
## [The DagsHub repo](https://dagshub.com/prabhanjan-jadhav/Pix3D)

### [Homepage](http://pix3d.csail.mit.edu/)

![Figure 1: Pix3D offers large-scale, diverse, well-aligned image-shape pairs.](https://camo.githubusercontent.com/1b3396c88a20bde462635b767fd601a17bc92d2b3d83499602f7c3ae67710d94/687474703a2f2f70697833642e637361696c2e6d69742e6564752f696d616765732f73706f746c696768745f70697833642e6a7067)
Source : https://github.com/xingyuansun/pix3d 

Figure: Pix3D offers large-scale, diverse, well-aligned image-shape pairs.


Study 3D shape modeling from a single image and make contributions to it in three aspects. Pix3D is a large-scale benchmark of diverse image-shape pairs with pixel-level 2D-3D alignment. Pix3D has wide applications in shape-related tasks including reconstruction, retrieval, viewpoint estimation, etc. Building such a large-scale dataset, however, is highly challenging.

The Pix3D dataset is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by/4.0/">Creative Commons Attribution 4.0 International License</a>.

## Dataset

For each instance in Pix3D, the following information is provided (stored in `pix3d.json`):
- `img`: path to the image
- `category`: category of the object in the image
- `img_size`: size of the image, in the format of [`width`, `height`]
- `2d_keypoints`: array of size `N` x `M` x 2, where `N` is the number of annotators and `M` is the number of 2D keypoints, indicating the positions of 2D keypoints on the image (origin: top left corner; `+x`: rightward; `+y`: downward); [-1.0, -1.0] if an annotator marked this keypoint hard to label (e.g., invisible)
- `mask`: path to the object mask
- `img_source`: source of the image: "ikea" / "internet" / "self-taken"
- `model`: 3D model of the object (`+x`: leftward, `+y`: upward, `+z`: inward, in canonical view)
- `model_raw`: raw 3D model of the object (for raw, scanned 3D models, only available in the full Pix3D dataset)
- `model_source`: source of the 3D model: "ikea" / "self-scanned"
- `3d_keypoints`: path to saved 3D keypoints (a text file)
- `voxel`: voxelized 3D model (`+x`: leftward, `+y`: outward, `+z`: upward, in canonical view)
- `rot_mat`: rotation matrix of the object (used in rendering)
- `trans_mat`: translation matrix of the object (used in rendering)
- `focal_length`: estimated focal length (in mm, and the width of the sensor is fixed to 32mm; used in rendering)
- `cam_position`: estimated camera position assuming the object is at the origin, and the camera is looking at the object center. The coordinates are defined in 3d model's reference frame, not voxel's. The camera's up vector is `+y`. (used in the evaluation)
- `inplane_rotation`: estimated inplane camera rotation assuming the object is at the origin, and the camera is looking at the object. (positive value: clockwise rotation, unit: radian; used in the evaluation).
- `truncated`: whether the object is truncated: "true" or "false"
- `occluded`: whether the object is occluded: "true" or "false"
- `slightly_occluded`: whether the object is slightly occluded: "true" or "false" (an object will not be both `occluded` and `slightly_occluded`)
- `bbox`: bounding box of the object, in the format of [`width_from`, `height_from`, `width_to`, `height_to`]

You can load `pix3d.json` into Python with
```python
import json
json.load(open('pix3d.json'))
```
## Reference
```
@inproceedings{pix3d,
  title={Pix3D: Dataset and Methods for Single-Image 3D Shape Modeling},
  author={Sun, Xingyuan and Wu, Jiajun and Zhang, Xiuming and Zhang, Zhoutong and Zhang, Chengkai and Xue, Tianfan and Tenenbaum, Joshua B and Freeman, William T},
  booktitle={IEEE Conference on Computer Vision and Pattern Recognition (CVPR)},
  year={2018}
}
```
