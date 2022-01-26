![Banner](https://github.com/CeliaSagas/Lidar-Net/blob/394ca201bff3ef4ecdc1b805da835338b488298e/img/Lidar-Net.jpeg)




# Lidar-Net
3D Object Detection with point-cloud LiDAR for Autonomous Driving Vehicles

**Abstract**

Autonomous driving vehicles require consistent object detection methods in order to make decisions in real time in response to environmental variables. Light Detection and Ranging (LiDAR) is a remote sensing method for determining variable using eye-safe laser beams which can provide consistent images for object detection, regardless of environmental factors like weather or light conditions. The goal for this project is to develop a deep learning model that can consistently detect vehicles in point clouds recorded from LiDAR scans.

**Design**

This project is inspired by current trends in autonomous driving research. The data is provided by [Nuscenes](https://www.nuscenes.org), a large-scale autonomous driving dataset with 3d object annotations. The challenge is to train a CNN to distinguish vehicles from a dataset containing all objects annotated within the Nuscenes Mini Dataset.


**Data**

The data is provided by [Nuscenes](https://www.nuscenes.org), a large-scale autonomous driving dataset with 3d object annotations. The Mini Lidarseg Dataset contains 10 scenes with 1,700+ annotated 3d objects recorded in both video camera and lidar point cloud format.

**Algorithms**

The dataset was created by accessing each annotated object within a scene, flattening the 3D bounding box to 2D, extracting the associated point cloud for that bounding box, using DB Scan to identify the largest cluster within that bounding box, and saving the annotation and refined point cloud for further analysis.

**Feature Engineering**

The following transformations were performed on the data in order to support further analysis:

  1.	Identified all annotated objects within a scene
  2.	Flattened 3D Bounding Box to 2D
  3.	Extracted the associated Point Cloud for each bounding box
  4.	Performed DB Scan Cluster Analysis to save the largest cluster within the Bounding Box
  5. Saved the refined point clouds and object labels as json file
  6. Reshaped and padded point cloud vectors to 844 points in length for analysis using Keras pad sequences
  7. Encoded Categories to Numerical classes using SKLearn Label Encoder
  8. Recoded classes to binary: (0: 'Noise', 1: Vehicle_car)



**Models**

DB Scan was used to perform cluster analysis of point clouds for feature engineering, while the PointNet Deep Learning Neural Network in Keras was utilized for direct object detection within point clouds.

PointNet is a fully connected CNN with each convolutional and fully-connected layer consisting of a convolutional dense layer with kernel size = 1, batch normalization, and ReLU Activation.

PointNet consists of two core components: the primary MLP network, and the transformer network, called the T-net. The T-net learns an affine transformation matrix by its own mini network.

**Model Evaluation and Selection**

Different approaches for point cloud classification were considered, including utilizing range-depth images, voxelization, and other methods of dimensionality reduction for CNNs. Ultimately, the PointNet model, which can directly intake 3D point clouds, was chosen for its simplicity and computational efficiency.

**PoinNet Final Scores**

  -	Validation Accuracy: 78.9%
  -	Validation AUC : 86.5



**Tools**

  -	Pandas, Numpy, cv2, Open3D, Os, Keras, Nuscenes SDK, Collections, json
  -	Google Colab, PyTorch, Tensorflow


**Communication**

Data Visualization and write-up will be shared on Medium, Celiasagastume.com, and in class through PowerPoint presentation.




**Resources**


Dataset creation and instance segmentation adapted from:

@misc{salazargomez2021highlevel,
      title={High-level camera-LiDAR fusion for 3D object detection with machine learning},
      author={Gustavo A. Salazar-Gomez and Miguel A. Saavedra-Ruiz and Victor A. Romero-Cano},
      year={2021},
      eprint={2105.11060},
      archivePrefix={arXiv},
      primaryClass={cs.CV}
}
