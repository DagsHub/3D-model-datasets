# Thingi10K-3D_Printing_Models_Dataset

### Paper: [Thingi10K: A Dataset of 10,000 3D-Printing Models](https://arxiv.org/abs/1605.04797) / [Mesh Arrangements for Solid Geometry](http://www.cs.columbia.edu/cg/mesh-arrangements/)
### DagsHub Repository: [Thingi10K-3D_Printing_Models_Dataset](https://dagshub.com/Rutam21/Thingi10K-3D_Printing_Models_Dataset)

![DagsHub Hacktoberfest Cover](https://user-images.githubusercontent.com/66431403/192983164-b3d6d556-ac69-4fb8-8aef-726a4386406a.png)

## About

Thingi10K is a dataset of 3D-Printing Models. Specifically there are 10,000 models from featured “things” on thingiverse.com, suitable for testing 3D printing techniques such as structural analysis , shape optimization, or solid geometry operations.

In a nutshell, Thingi10K containsthe following.

- 10,000 models
- 4,892 tags
- 2,011 things
- 1,083 designers
- 72 categories
- 10 open source licenses
- 7+ years span
- 99.6% .stl files
- 50% non-solid
- 45% with self-intersections
- 31% with coplanar self-intersections
- 26% with multiple components
- 22% non-manifold
- 16% with degenerate faces
- 14% non-PWN
- 11% topologically open
- 10% non-oriented

## Dataset Summary

Total number of files: 10,000

- STL files: 9956
- OBJ files: 42
- PLY files: 1
- OFF files: 1


## Errors

The following models are known to be "corrupt." However, they are still included in the dataset in order to faithfully reflect mesh qualities on Thingiverse.

- Model 49911 is truncated (ASCII STL).
- Model 74463 is empty.
- Model 286163 is empty.
- Model 81313 contains NURBS curves and surfaces instead of polygonal faces, which may not be supported by many OBJ parsers.
- Model 77942 is corrupt (binary STL). Here is a potential replacement model created by a different user.

## Acknowledgement

We thank Marcel Campen, Chelsea Tymms, and Julian Panetta for early feedback and proofreading. This project is funded in part by NSF grants CMMI-11-29917, IIS-14-09286, and IIS-17257.

We also thank Neil Dickson for pointing out corrupt models, and Nick Sharp for pointing out bugs in download script.

## Citation

Please use the following bibtex to cite Thingi10K:

```
@article{Thingi10K,
  title={Thingi10K: A Dataset of 10,000 3D-Printing Models},
  author={Zhou, Qingnan and Jacobson, Alec},
  journal={arXiv preprint arXiv:1605.04797},
  year={2016}
}
``` 
