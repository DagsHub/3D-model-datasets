# HUMAN4D

**[HUMAN4D](https://ieee-dataport.org/open-access/human4d-human-centric-multimodal-dataset-motions-immersive-media): A HUMAN-CENTRIC MULTIMODAL DATASET FOR MOTIONS & IMMERSIVE MEDIA**

![](https://user-images.githubusercontent.com/66431403/192983164-b3d6d556-ac69-4fb8-8aef-726a4386406a.png)


A large and multimodal 4D dataset that contains a variety of human activities simultaneously captured by a professional marker-based MoCap, a volumetric capture and an audio recording system. By capturing 2 female and 2 male professional actors performing various full-body movements and expressions, HUMAN4D provides a diverse set of motions and poses encountered as part of single- and multi-person daily, physical and social activities (jumping, dancing, etc.), along with multi-RGBD (mRGBD), volumetric and audio data. Despite the existence of multi-view color datasets captured with the use of hardware (HW) synchronization, to the best of our knowledge, HUMAN4D is the first and only public resource that provides volumetric depth maps with high synchronization precision due to the use of intra- and inter-sensor HW-SYNC. Moreover, a spatio-temporally aligned scanned and rigged 3D character complements HUMAN4D to enable joint research on time-varying and high-quality dynamic meshes. We provide evaluation baselines by benchmarking HUMAN4D with state-of-the-art human pose estimation and 3D compression methods. For the former, we apply 2D and 3D pose estimation algorithms both on single- and multi-view data cues. For the latter, we benchmark open-source 3D codecs on volumetric data respecting online volumetric video encoding and steady bit-rates. Furthermore, qualitative and quantitative visual comparison between mesh-based volumetric data reconstructed in different qualities showcases the available options with respect to 4D representations. HUMAN4D is introduced to the computer vision and graphics research communities to enable joint research on spatio-temporally aligned pose, volumetric, mRGBD and audio data cues.The dataset and its code are available online.


<p align="center">
  <img src="https://user-images.githubusercontent.com/66431403/192986782-2b93a6c6-f59d-47aa-9eef-cbb2195744d5.gif" alt="animated" />
</p>



The dataset includes multi-view RGBD, 3D/2D pose, volumetric (mesh/point-cloud/3D character) and audio data along with metadata for spatiotemporal alignment.

The full dataset is splitted per subject and per activity per modality.

There are also two benchmarking subsets, H4D1 for single-person and H4D2 for two-person sequences, respectively.

The fornats are:

- mRGBD: *.png
- 3D/2D poses: *.npy
- volumetric (mesh/point-cloud/): *.ply
- 3D character: *.fbx
- metadata: *.txt, *.json