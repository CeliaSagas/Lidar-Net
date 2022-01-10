![Banner](https://github.com/CeliaSagas/Lidar-Net/blob/394ca201bff3ef4ecdc1b805da835338b488298e/img/Lidar-Net.jpeg)



# Lidar-Net
3D Object Detection with point-cloud LiDAR for Autonomous Driving Vehicles




**Question/Need:**

1. What is the question behind your analysis? What is the purpose of the model/system you plan to build?

      - Autonomous driving vehicles require consistent object detection methods in order to make decisions in real time in response to environmental variables. Light Detection and Ranging (LiDAR) is a remote sensing method for determining variable distance using eye-safe laser beams which can provide consistent images for object detection, regardless of environmental factors like weather or light conditions.

        My goal for this project is to develop a deep learning model that can consistently detect objects pertinent for autonomous driving from 25 second LiDAR recordings provided by NuScenes.




2. Who benefits from exploring this question or building this model/system?

    - Autonomous vehicles can be a huge benefit for people with different abilities, like those who are blind, or those who live with epilepsy. These vehicles can also enhance ride-sharing capabilities and therefore reduce carbon emissions, reduce costs of personal transportation, provide mobility, and reduce traffic deaths.

      Developing consistent and dependable deep learning models that can identify objects, predict motion, and aid in decision making is crucial to the development of these vehicles.



**Data Description:**

1. What dataset(s) do you plan to use, and how will you obtain the data?

    - The dataset I will be using comes from the [nuScenes-lidarseg](https://www.nuscenes.org/nuscenes) and includes over 55,000 human labeled 3D annotated frames, a drivable surface map, and an HD spatial semantic map to contextualize the data.

2. What is an individual sample/unit of analysis in this project?

    - A single unit of analysis is a single annotated key frame of a scene where the time stamps of data from all sensors align with the time stamp of the sample it points to.

3. What characteristics/features do you expect to work with?

    - I expect to work with Lidar point-cloud images, camera images, and object annotations with bounding boxes per keyframe.

4. If modeling, what will you predict as your target?

    - My target will be the object classes annotated in the dataset, namely vehicle types, and pedestrians.



**Tools:**

1. How do you intend to meet the tools requirement of the project?

    - I plan to use Google Collab, Lyft Dataset SDK, Nuscenes, Keras, and Tensorflow.

2. Are you planning in advance to need or use additional tools beyond those required?

    - Yes, I believe Nuscenes, Google Collab, and Lyft Dataset SDK are additional tools above what is required.



**MVP Goal:**

1. What would a minimum viable product (MVP) look like for this project?

    - My MVP will be a baseline deep learning model for object detection using LiDAR.
