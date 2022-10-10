# BuildingNet-3D_Building_Models_Dataset

### Paper: [BuildingNet: Learning to Label 3D Buildings](https://arxiv.org/pdf/2110.04955v1.pdf)
### DagsHub Repository: [BuildingNet-3D_Building_Models_Dataset](https://dagshub.com/Rutam21/BuildingNet-3D_Building_Models_Dataset)

![DagsHub Hacktoberfest Cover](https://user-images.githubusercontent.com/66431403/192983164-b3d6d556-ac69-4fb8-8aef-726a4386406a.png)

## About

BuildingNet is a large-scale dataset of 3D building models whose exteriors are consistently labeled. The dataset consists on 513K annotated mesh primitives, grouped into 292K semantic part components across 2K building models. The dataset covers several building categories, such as houses, churches, skyscrapers, town halls, libraries, and castles.

## Dataset Structure

The folder contains the BuildingNet v0.1. The folder structure is the following:


- BuildingNet-3D_Building_Models_Dataset (base folder): **[Everything uploaded to this repository.]**
----------------------------------------

-- **OBJ_MODELS:** 
	This zip file contains all the OBJ models of 3D buildings used in our dataset including textures. 
	The models are derivations of models publicly available on the 3D Warehouse after substantial modifications
	described in our paper & supplementary material. Each OBJ file structure contains elements and grouping.
	Each group is a part/component whose part labels are available in the "model_data/obj" folder. The links
	containing the original models & credits are available in the 3D_Warehouse_IDs folder.

-- **POINT_CLOUDS:** 
	This zip file includes the point clouds (in PLY format) of buildings generated from the OBJ models as
	described in the paper. Each PLY file consists of 100,000 points, where each row is in the following format:

		(<3D coordinates> <point normal> <RGBA value>) -> (<x y z> <nx ny nz> <red green blue alpha>)
		

-- **3D_Warehouse_IDs/:**
	This folder includes links containing the original models & credits, along with their 3DWarehouse IDs.

-- **splits/:**
	This folder includes a list of building model names belonging to training (train_split.txt), validation
	(val_split.txt), and test (test_split.txt) splits (same splits are used in the mesh and point cloud track).

-- **model_data/:** 
	This folder includes several model information (e.g., face and component part labels, point
	labels, graph representation data used for training Building GNN). The structure of this folder
	is the following:

	++ model_data/GNN/:
		This folder includes all data for each graph representation of all buildings included in this dataset:

		** adjacency.zip: 
			This zip file includes the adjacency edges per pair of components, as described in the paper
			- (1%, 2.5%, 5%, 10%, 25%, 50%, 100% ) surface proximity with respect to average bounding box
			diagonal distance, in JSON format:
                (<key>: (<key>: <value>)) ->
                (component_ID_i: (component_ID_j: [proximity_threshold_0,.., proximity_threshold_6]))

		** containment.zip: 
			This zip file includes the containment edges per pair of components, as described in the paper, in
			JSON format:
			    (<key>: (<key>: <value>)) -> (component_ID_i: (component_ID_j: [volume_amount, volume_IoU]))

		** label.zip: 
			This zip file includes the part labels per component for each building, in JSON format:
				(<key>: <value>) -> (component_ID: part_label_ID)

		** node.zip:
			This zip file includes the graph node representation of each component, as described in the paper, in
			JSON format (note: these are combined with the pretrained_avgpool_minkownormal_features to get the final
			graph node representation):
			    (<key>: <value>) ->
			    (component_ID: [3D_barycenter_position, 3D_coordinates_of_opposite_corners_of_OBB, surface_area] \in R^10)

		** pretrained_avgpool_minkownormal_features.zip:
			This zip file includes the pre-trained MinkNet features per component, as described in the paper, in
			.pth.tar format:
			    torch.Tensor(<torch.float64>) \in R^(n_comps x 31), where n_comps is the number of components of each
			    building

		** similarity.zip:
			This zip file includes the similarity edges per pair of components, as described in the paper, in
			JSON format:
			    (<key>: (<key>: <value>)) -> (component_ID_i: (component_ID_j: 1-d_{ij}))

		** support.zip:
			This zip file includes the support edges per pair of components, as described in the paper -
			(1%, 2.5%, 5% 10%, 25% 50%, 100%) bounding box overlap area in Y-Axis with respect to average
			bounding box height distance, in JSON format:
                (<key>: (<key>: <value>)) ->
                (component_ID_i: (component_ID_j: [height_threshold_0,.., height_threshold_6]))

		** surfacearea.zip:
			This zip file includes the surface area per component of each building, in JSON format:
				(<key>: <value>) -> (component_ID: surface_area)
			

	++ model_data/obj:
		This folder includes several information for all OBJ models of buildings in this dataset:

		** component_labels.zip:
			This zip file includes the part labels per component for each building, in JSON format:
				(<key>: <value>) -> (component_ID: part_label_ID)

		** faceindex_componentID.zip:
			This zip file includes the face IDs per component for each building, in JSON format:
				(<key>: (<key>: <value>)) -> (start_face_ID: (end_face_ID: component_ID))

		** face_labels.zip:
			This zip file includes the part labels per face for each building, in JSON format:
				(<key>: <value>) -> (face_ID: part_label_ID)

	
	++ model_data/point_cloud:
		This folder includes several information for all point clouds of buildings in this dataset:

		** point_faceindex.zip:
			This zip file includes the face indices (IDs) per point for each building, in TXT format:
				<#row> face_ID

		** point_labels.zip:
			This zip file includes the part labels per point for each building, in JSON format:
				(<key>: <value>) -> (point_ID: part_label_ID)
                
## Citation

```
Pratheba Selvaraju, Mohamed Nabail, Marios Loizou, Maria Maslioukova, Melinos Averkiou, Andreas Andreou, Siddhartha Chaudhuri, Evangelos Kalogerakis, "BuildingNet: Learning to Label 3D Buildings", Proceedings of the IEEE/CVF International Conference on Computer Vision (ICCV), 2021
```

## Bibtex

```
@inproceedings{Selvaraju:2021:BuildingNet, 
  author = {Pratheba Selvaraju and Mohamed Nabail and Marios Loizou and Maria Maslioukova and
            Melinos Averkiou and Andreas Andreou and Siddhartha Chaudhuri and Evangelos Kalogerakis},
  title = {BuildingNet: Learning to Label 3D Buildings},   
  booktitle = {IEEE/CVF International Conference on Computer Vision (ICCV)},
  year = {2021}   
}   
```
