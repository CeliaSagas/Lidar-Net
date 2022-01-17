![Banner](https://github.com/CeliaSagas/Lidar-Net/blob/394ca201bff3ef4ecdc1b805da835338b488298e/img/Lidar-Net.jpeg)



# Lidar-Net
3D Object Detection with point-cloud LiDAR for Autonomous Driving Vehicles



<br><br>
The goal of this project is to identify cars, pedestrians, and cyclists using the lidar data from the Nuscenes dataset.

# Cleaning

<br><br>
Lidar point clouds are represent 3d space by returning depth and light information for objects within the lidar field. Dimensionality reduction is necessary for such large format data. My current approach is to reduce the 3d point cloud to a 2d range image which can be used as the input for a U-Net.


# Visualization

<br><br>

Thanks to the Nuscenes Devkit and the work of Gustavo Salazar-Gomez et. al in "High Level camera-LiDAR fusion for 3D object detection with machine learning", I have been able to render the bounding box for objects in the dataset:

![3D Bounding Box ](https://github.com/CeliaSagas/Toxic-Rank/blob/5cfdd40f8d814b721ee9dce6eaef922ac6ae9ec9/img/Count_Vectorize.png)

Compute the 2D bounding box:

![2D Bounding Box ](https://github.com/CeliaSagas/Toxic-Rank/blob/5cfdd40f8d814b721ee9dce6eaef922ac6ae9ec9/img/Count_Vectorize.png)

And compute the point cloud for the segmented field

![Segmented Point Cloud ](https://github.com/CeliaSagas/Toxic-Rank/blob/5cfdd40f8d814b721ee9dce6eaef922ac6ae9ec9/img/Count_Vectorize.png)


My next steps are to reduce the segmented point clouds to a Range Images, and then use them as a training set for a U-Net. 
