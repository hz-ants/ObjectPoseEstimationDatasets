# ObjectPoseEstimationDatasets
A repo to summarize **datasets** used for object pose estimation and 
**rendering methods** used to generate synthetic training data.

In the following tables, 3D CAD model is noted as **model** and 
2D pictured object is noted as **object**.

Papers resuming some related datesets 
can be found [here](http://openaccess.thecvf.com/content_CVPRW_2019/papers/WiCV/Jalal_SIDOD_A_Synthetic_Image_Dataset_for_3D_Object_Pose_Recognition_CVPRW_2019_paper.pdf)
and [here](https://arxiv.org/abs/1903.04229)
 

## Table of Content
* [Challenges](#challenges)
* [Objects in the controlled environments](#objects-in-the-controlled-environments)
* [Objects in the wild](#objects-in-the-wild)
* [3D model datasets](#3d-model-datasets)
* [Rendering Methods](#rendering-methods)


## Challenges :space_invader:
* [ICCV 2015: Occluded Object Challenge](https://hci.iwr.uni-heidelberg.de/vislearn/iccv2015-occlusion-challenge/)
* [ICCV 2015: Recovering Object Pose](https://labicvl.github.io/3DPose-2015.html)
* [ECCV 2016: Recovering Object Pose](https://labicvl.github.io/R6D)
* [ICCV 2017: Recovering Object Pose](http://cmp.felk.cvut.cz/sixd/workshop_2017/)
* [ECCV 2018: Recovering Object Pose](http://cmp.felk.cvut.cz/sixd/workshop_2018/)
* [ICCV 2019: Recovering Object Pose](http://cmp.felk.cvut.cz/sixd/workshop_2019/)
* [IROS 2019: Object Pose Estimation for Bin-Picking](http://www.bin-picking.ai/en/competition.html)


## Objects in the controlled environments :movie_camera:
This table lists the datasets commonly known as **BOP: Benchmark 6D Object Pose Estimation**, 
which provide accurate 3D object models and precise 2D-3D alignment.

You can download all the BOP datasets [here](https://bop.felk.cvut.cz/datasets/) and
use the [toolkit](https://github.com/thodan/bop_toolkit) provided by the organizers.

After downloading the data, 
you can use our code ```ply2obj.py``` to convert original **.ply** files to **.obj** files,
and run ```create_annotation.py``` to create a single annotation file for all the scenes in a dataset.

Datasets format can be found [here](https://github.com/thodan/bop_toolkit/blob/master/docs/bop_datasets_format.md),
we use **instance id** in our annotation to indicate different instances pictured in the same image.

| Dataset | Sample image | Annotation | Statistics | Reference |
| :-----: | :-----: | :-----: | :-----: | :-----: |
| [HomebrewedDB](https://bop.felk.cvut.cz/datasets/) | ![](https://github.com/YoungXIAO13/6DPoseEstimationDatasets/blob/master/img/HomebrewedDB.png) | 6D pose + Depth + BoundingBox| **33** models in **13** videos with **17,420** frames| [Preprint 2019](https://arxiv.org/abs/1904.03167)| 
| [YCB-Video](https://bop.felk.cvut.cz/datasets/) | ![](https://github.com/YoungXIAO13/6DPoseEstimationDatasets/blob/master/img/YCB-Video.png) | 6D Pose + Depth + Mask | **21** models in **92** videos with **133,827** frames| [RSS 2018](https://arxiv.org/abs/1711.00199) |
| [T-LESS](https://bop.felk.cvut.cz/datasets/)| ![](https://github.com/YoungXIAO13/6DPoseEstimationDatasets/blob/master/img/T-LESS.png) | 6D Pose + Depth | **30** models in **20** videos with **~49K** frames | [WACV 2017](http://cmp.felk.cvut.cz/t-less/)|
| [Doumanoglou](https://bop.felk.cvut.cz/datasets/)| ![](https://github.com/YoungXIAO13/6DPoseEstimationDatasets/blob/master/img/Doumanoglou.png)| 6D Pose + Depth | **2** models in **3** videos with **183** frames| [CVPR 2016](http://rkouskou.gitlab.io/research/6D_NBV.html)|
| [Tejani](https://bop.felk.cvut.cz/datasets/) | ![](https://github.com/YoungXIAO13/6DPoseEstimationDatasets/blob/master/img/Tejani.png) | 6D Pose + Depth | **6** models in **6** videos with **2,067** frames | [ECCV 2014](http://rkouskou.gitlab.io/research/LCHF.html)|
| [Occluded-LINEMOD](https://bop.felk.cvut.cz/datasets/) | ![](https://github.com/YoungXIAO13/6DPoseEstimationDatasets/blob/master/img/LINEMOD-O.jpg) | 6D Pose + Depth | **8** models in **1,214** frames with **8,992** objects | [ECCV 2014](http://wwwpub.zih.tu-dresden.de/~cvweb/publications/papers/2014/PoseEstimationECCV2014.pdf) | 
| [LINEMOD](https://bop.felk.cvut.cz/datasets/) | ![](https://github.com/YoungXIAO13/6DPoseEstimationDatasets/blob/master/img/LINEMOD.jpg) | 6D pose + Depth for one object | **15** models in **15** videos with **18,273** frames | [ACCV 2012](http://www.stefan-hinterstoisser.com/papers/hinterstoisser2012accv.pdf) |


## Objects in the wild :camera:
In this table, **Pix3D** and **ScanNet** provide precise 2D-3D alignment 
while others only provide a coarse alignment.

**PASCAL3D+** is the de facto benchmark used for viewpoint estimation.

**ScanNet** is usually used to evaluate scene reconstruction and segmentation.

| Dataset | Sample image | Annotation | Statistics | Reference |
| :-----: | :-----: | :-----: | :-----: | :-----: |
| [ApolloCar3D](http://apolloscape.auto/car_instance.html) | ![](https://github.com/YoungXIAO13/6DPoseEstimationDatasets/blob/master/img/ApolloCar3D.png) | 6D Pose + Mask | **34** car models with **60K+** objects in **5,277** images | [CVPR 2019](https://arxiv.org/abs/1811.12222) |
| [Pix3D](http://pix3d.csail.mit.edu/) | ![](https://github.com/YoungXIAO13/6DPoseEstimationDatasets/blob/master/img/Pix3D.png) | 6D Pose + Mask | **9** categories containing **395 models** in **10,069** images | [CVPR 2018](http://pix3d.csail.mit.edu/papers/pix3d_cvpr.pdf) |
| [ScanNet](http://www.scan-net.org/) | ![](https://github.com/YoungXIAO13/6DPoseEstimationDatasets/blob/master/img/ScanNet.png) | 6D Pose + Segmentation + Depth | **2.5M** RGB-D frames in **1,515** scenes | [CVPR 2017](https://arxiv.org/abs/1702.04405) |
| [ObjectNet3D](http://cvgl.stanford.edu/projects/objectnet3d/) | ![](https://github.com/YoungXIAO13/6DPoseEstimationDatasets/blob/master/img/ObjectNet3D.png) | Euler Angles + BoundingBox | **100** categories with **201,888** objects in **90,127** images | [ECCV 2016](http://cvgl.stanford.edu/papers/xiang_eccv16.pdf) |
| [PASCAL3D+](http://cvgl.stanford.edu/projects/pascal3d.html) | ![](https://github.com/YoungXIAO13/6DPoseEstimationDatasets/blob/master/img/Pascal3D.png) | Euler Angles + BoundingBox | **12** categories with **36,292** objects in **30,889** images | [WACV 2014](https://www-cs.stanford.edu/~roozbeh/papers/wacv14.pdf) |
| [KITTI](http://www.cvlibs.net/datasets/kitti/eval_object.php) | ![](https://github.com/YoungXIAO13/6DPoseEstimationDatasets/blob/master/img/KITTI.png) | 3D BoundingBox | **80,256** objects in **14,999** images | [CVPR 2012](http://www.cvlibs.net/publications/Geiger2012CVPR.pdf) |


## 3D model datasets :bike:
In order to testify the network **generalization** ability 
(tested on images containing **unseen** 3D models from the training set),
the following dataset could be used to generate synthetic training data.

Notice that **ABC** contains generic and arbitrary industrial CAD models 
while **ShapeNetCore** and **ModelNet** contain common category objects such as cars and chairs.   

| Dataset | Categories | Models in total | Reference |
| :-----: | :-----: | :-----: | :-----: |
| [ABC](https://deep-geometry.github.io/abc-dataset/) | - | 1 million | [CVPR 2019](https://arxiv.org/pdf/1812.06216.pdf) |
| [ShapeNetCore](https://www.shapenet.org/download/shapenetcore) | 55 | ~51,300 | [ArXiv 2015](https://arxiv.org/abs/1512.03012) | 
| [ModelNet-40](http://modelnet.cs.princeton.edu/) | 40 | 26,960 | [CVPR 2015](https://3dshapenets.cs.princeton.edu/paper.pdf) |


## Rendering methods :bicyclist:

### Differentiable Renderer
* [Neural 3D Mesh Renderer](http://hiroharu-kato.com/projects_en/neural_renderer.html): Kato el al. CVPR 2018
 
* [RenderNet](https://github.com/thunguyenphuoc/RenderNet): Thu et al. NIPS 2018

### Blender Render :mountain_bicyclist:
In this repo, we provide python code to generate rendering images from 3D models using
blender as a python module that is easy to install and generate photo-realistic images : )

In order to generate synthetic data, we first need to simulate a set of poses where the
camera is uniformly distributed on the upper semi-sphere around the table plane.

```./blender_render/table_poses.npz``` contains the poses obtained in LINEMOD-Occlusion dataset
with the distribution listed below:
    
    * Range of object distances: 346 - 1500 mm (only 3 instances below 400 mm)
    * Azimuth range: 0 - 360 deg
    * Elevation range: -14 - 89 deg (only a few instances below 0 deg)
    
You can download CAD models of the [ABC](https://deep-geometry.github.io/abc-dataset/) dataset 
and retrieve .obj files into the target directory using ```retrieve_files.py```. 

Then generate synthetic images of different models with various lightness and textures 
under random poses by running ```./blender_render/render_random_pose.py```

* Other works using blender can be found 
[here](https://github.com/weiaicunzai/blender_shapenet_render) that generates one model at a time.

### Physical Simulator

[PyBullet](https://github.com/bulletphysics/bullet3/tree/master/examples/pybullet): 
a very popular one in the Robotics community.


### Others
* [Glumpy](https://github.com/glumpy/glumpy): does not support headless rendering (failed on ssh mode)

* [UnrealCV](https://github.com/unrealcv/unrealcv): extension of Unreal Engine 4, 
helps interact with virtual world and communicate with external program.

* [SyntheticComputerVision](https://github.com/unrealcv/synthetic-computer-vision): 
resuming a lot of techniques used to generate synthetic image 

**Attention**: 3D models should be aligned in the same way through **meshlab** to 
ensure the consistent orientation while wandering across the different datasets.