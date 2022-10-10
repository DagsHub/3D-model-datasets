# PanoContext: A whole room 3D context model 

### DagsHub Repository: [PanoContext-A-Whole-room-3D-Context-Model](https://dagshub.com/arnavr.neo/PanoContext-A-Whole-room-3D-Context-Model) 

The PanoContext dataset contains 500 annotated cuboid layouts of indoor environments such as bedrooms and living rooms. <br/> 

<center><img align="center" src="https://panocontext.cs.princeton.edu/teaser.jpg"></img></center> <br/> 

## Abstract 

The field-of-view of standard cameras is very small, which is one of the main reasons that contextual information is not as useful as it should be for object detection. To overcome this limitation, we advocate the use of 360◦ full-view panoramas in scene understanding, and propose a whole-room context model in 3D. For an input panorama, our method outputs 3D bounding boxes of the room and all major objects inside, together with their semantic categories. Our method generates 3D hypotheses based on contextual constraints and ranks the hypotheses holistically, combining both bottom-up and top-down context information. To train our model, we construct an annotated panorama dataset and reconstruct the 3D model from single-view using manual annotation. Experiments show that solely based on 3D context without any image region category classifier, we can achieve a comparable performance with the state-of-the-art object detector. This demonstrates that when the FOV is large, context is as powerful as object appearance. All data and source code are available online. ## About dataset The dataset contains 2D and 3D annotation on bedroom and living room panoramas. 

## Paper

- Y. Zhang, S. Song, P. Tan, and J. Xiao. <br/> [PanoContext: A Whole-room 3D Context Model for Panoramic Scene Understanding](https://panocontext.cs.princeton.edu/paper.pdf). Proceedings of the 13th European Conference on Computer Vision (ECCV2014) Oral Presentation 

------------------------------------------------------------------------------------------------------------------------ 

### *This open source contribution is part of [DagsHub x Hacktoberfest](https://dagshub.com/blog/dagshub-x-hacktoberfest-2022/)*.
