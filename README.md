<h1 align="center">Thippeswamy K.S.</h1>
<p align="center"><b>Computer Vision & ML Engineer</b> · Computer Vision · Machine Learning · Robotics Perception</p>
<p align="center">
  <a href="https://thippeswammy.github.io/"><img src="https://img.shields.io/badge/Portfolio-thippeswammy.github.io-6366f1?style=flat-square" alt="Portfolio"></a>
  <a href="https://www.linkedin.com/in/thippeswamy-k-s-448019260/"><img src="https://img.shields.io/badge/LinkedIn-Thippeswamy%20K.S.-0a66c2?style=flat-square&logo=linkedin" alt="LinkedIn"></a>
  <a href="mailto:thippeswamy636408@gmail.com"><img src="https://img.shields.io/badge/Email-thippeswamy636408%40gmail.com-06b6d4?style=flat-square&logo=gmail&logoColor=white" alt="Email"></a>
  <a href="https://thippeswammy.github.io/assets/THIPPESWAMY_KS_CV.pdf"><img src="https://img.shields.io/badge/Resume-PDF-a855f7?style=flat-square" alt="Resume"></a>
</p>

> I build perception systems that let vehicles and robots understand where they are and what is around them.

Computer Vision & ML engineer working on **detection, segmentation, tracking, monocular depth, visual odometry and SLAM** on real sensor data: camera, LiDAR, IMU and GPS. I take models from data and labeling, through training and evaluation, to real-time deployment with **PyTorch, TensorRT, C++ and ROS 2**. Author of an IEEE DISCOVER 2026 paper on vision-based odometry.

- **Junior Robotics Engineer** — Virya Autonomous Technologies · since Sep 2025
- **IEEE DISCOVER 2026** — Paper on vision-based odometry
- **B.Tech ECE · 8.55 CGPA** — GITAM University, Bengaluru · 2022–2026
- **Open to CV / ML roles** — Also robotics perception roles

## [Experience](https://thippeswammy.github.io/#experience)

**Junior Robotics Engineer** · Virya Autonomous Technologies · *Sep 2025 – Present*  
- Work on the software stack for autonomous mobile robots (AMRs).
- Areas: SLAM and localization, multi-sensor fusion (LiDAR, camera, IMU), sensor calibration, ROS 2 system tooling and perception data tooling.

<sub>Company projects are confidential, so they are not described here.</sub>

**Computer Vision & Robotics Intern** · MURTI (SDV), GITAM University · *2024 – 2025*  
- Ran proof-of-concept experiments on visual odometry and SLAM methods, including deep-learning models, to track a vehicle's motion without GPS, with and without LiDAR. This led to the [IEEE DISCOVER 2026 paper](https://thippeswammy.github.io/#publication).
- Built a drivable-region detector for Indian roads that finds the road and free space ahead of an autonomous vehicle ([project](https://thippeswammy.github.io/#adas-indian-roads)).

## Projects · [Computer Vision & Machine Learning](https://thippeswammy.github.io/#cv-ml)

Perception models trained on real data, evaluated against ground truth and run in real time. This is the work I want to keep doing.

### [InfraStructer: Road-Infrastructure Audit from a Single Camera](https://thippeswammy.github.io/#infrastructer)
🔒 *Private repo · in active development*  
Turns dashcam or phone footage plus phone GPS into a map of road signs, checked against OpenStreetMap, with no LiDAR and no RTK.

- An end-to-end perception pipeline: object and traffic-sign **detection** → multi-object **tracking** with appearance re-identification → **monocular metric depth** → **visual odometry** → OpenStreetMap **map matching** → landmark map.
- Rewrote the original ROS 2 / Python prototype as a C++ pipeline (v2.0). It runs **live at 10 Hz on a single laptop GPU** without dropping frames.
- Deployed models as TorchScript, ONNX and TensorRT FP16 engines: YOLOv8 sign detectors trained on GTSDB and CCTSDB2021, and Depth Anything 3 metric depth. Pose graph and trajectory correction use GTSAM.
- Every code change runs a regression benchmark on 33 real drives from **KITTI, Oxford RobotCar and nuScenes**. Each run is stored as a baseline so the next change can be compared against it, run by run.

**10 Hz** live on a laptop GPU · **33 drives** 3 public datasets · **3.2 m** median trajectory error (ATE), camera + start/end GPS fixes only · **~75%** live map-matching rate

`C++17` `LibTorch` `TensorRT` `YOLOv8` `Depth Anything 3` `Multi-object tracking` `Visual odometry` `GTSAM` `OpenStreetMap` `Qt / VTK`

### [AutoSegmentor: Video-to-Dataset Auto-Labeling](https://thippeswammy.github.io/#autosegmentor)
🌐 *Open source · on PyPI*  
Annotate one frame and get detection, segmentation and pose labels for the whole video.

- Combines **SAM2** mask propagation with **CoTracker3** keypoint tracking. Clicks or boxes on one frame carry masks and keypoints across long, complex videos.
- A single export produces **YOLO datasets for object detection, instance segmentation and pose estimation** at the same time, with built-in augmentation and dataset versioning.
- Generates semi-synthetic training data from real footage using the exact masks, so models train robustly from very little hand-labeled data.
- A PyQt5 desktop app with multi-class point and box annotation, a precision zoom and an async GPU engine that keeps the UI responsive. Released as a pip package with a documentation site.

`SAM2` `CoTracker3` `PyTorch` `YOLO` `Pose estimation` `Data engineering` `PyQt5`

[GitHub](https://github.com/thippeswammy/AutoSegmentor) · [PyPI](https://pypi.org/project/autosegmentor/) · [Docs](https://thippeswammy.github.io/AutoSegmentor/) · [Demo video](https://drive.google.com/file/d/1Y19lwf_IIuzwVe-3j9vX0uicV_iWbrHZ/view?usp=sharing)

### [Drivable-Region & Object Perception for Indian Roads](https://thippeswammy.github.io/#adas-indian-roads)
🌐 *Open source*  
Road segmentation and object detection for unstructured Indian traffic, built during my MURTI research internship.

- Trained **YOLOv8-Seg** for road and drivable-space segmentation, object detection and instance segmentation, so the vehicle knows where it can travel.
- Built a dataset of **45,000+ annotated images from 40 videos** of Indian roads, covering different weather, lighting and road types.
- Refined road masks with SLIC superpixels and tuned inference for real-time use at 854×480.

**45k+** annotated images · **40** source videos

`YOLOv8-Seg` `Semantic segmentation` `Object detection` `Dataset curation` `OpenCV`

[GitHub](https://github.com/thippeswammy/ADAS-for-Indian-Road-Vehicle)

<details>
<summary><b>More Computer Vision & Deep Learning</b> — Lane perception, face recognition, segmentation training, stereo depth and coursework.</summary>

| Repository | What it is |
|---|---|
| [LaneLinesDetection](https://github.com/thippeswammy/LaneLinesDetection) | Classical CV and deep-learning lane and road detection compared side by side: HybridNets multitask inference in ONNX, U-Net road segmentation and curved-lane tracking. <sub>`ONNX · U-Net · OpenCV`</sub> |
| [FaceRecognition](https://github.com/thippeswammy/FaceRecognition) | Face recognition with two engines: one-shot auto-tagging with depth sensing, and a YOLOv8 detect-and-classify model trained on a custom augmented dataset. Deployed on a Raspberry Pi. <sub>`YOLOv8 · one-shot learning`</sub> |
| Yolov_models 🔒 | Workspace for training and evaluating YOLO segmentation models: road extraction from video, plus IoU and ROC test scripts. <sub>`YOLO11-seg · evaluation`</sub> |
| [ZED2i](https://github.com/thippeswammy/ZED2i) | Stereo data capture for the ZED 2i camera: synchronized left-right images, depth and positional tracking, using threaded, memory-bounded queues. <sub>`Stereo vision · depth`</sub> |
| [ImageProcessingCourse](https://github.com/thippeswammy/ImageProcessingCourse) | Implementations of core image and video processing topics: filtering, transforms and analysis. <sub>`Python · OpenCV`</sub> |
| [Deep-Learning-Specialization](https://github.com/thippeswammy/Deep-Learning-Specialization) | Notes and assignments from the Deep Learning Specialization: neural networks, CNNs, sequence models and optimization. <sub>`Coursework`</sub> |

</details>

## Projects · [Robotics, SLAM & Localization](https://thippeswammy.github.io/#robotics)

Knowing where the vehicle is, and placing what the camera sees in 3D: visual odometry, SLAM, sensor fusion and ROS 2.

### [Visual Odometry Benchmark for Low-Compute Vehicles](https://thippeswammy.github.io/#vo-benchmark)
📄 *IEEE DISCOVER 2026*  
How well do feature-based, optical-flow and deep-learning visual odometry methods work on an embedded computer, outside the benchmark?

- Compared **five monocular VO approaches** (feature-based, optical-flow-based and deep-learning-based) on KITTI and on a new **campus-scale GITAM dataset**. The dataset was recorded on an autonomous ground vehicle with camera, LiDAR and GNSS.
- Validated trajectories against RTK-GNSS. Measured accuracy, drift and compute cost on an **NVIDIA Jetson Xavier NX**.
- Integrated, extended and evaluated DROID-SLAM, DPVO, ORB-SLAM2/3, stereo SOFT and dense optical-flow VO. This included Jetson (ARM64) builds, ROS 2 wrappers and resource monitoring.

`Visual odometry` `SLAM` `DROID-SLAM` `DPVO` `ORB-SLAM3` `Jetson` `KITTI`

[Paper details](https://thippeswammy.github.io/#publication) · [DROID-SLAM](https://github.com/thippeswammy/DROID_slam) · [DPVO](https://github.com/thippeswammy/DPVO) · [ORB-SLAM3](https://github.com/thippeswammy/ORB_SLAM3)

### [Semantic Robot Perception: Camera–LiDAR Fusion & Semantic Mapping](https://thippeswammy.github.io/#semantic-robot-perception)
🔒 *Private repo*  
A mobile robot that detects objects, places them in 3D and builds a persistent semantic map (ROS 2 Humble + Gazebo).

- **Open-vocabulary detection with YOLO-World** plus a centroid tracker, so the target classes are set from a config file without retraining.
- **Camera–LiDAR fusion** back-projects each tracked detection through the pinhole model and fuses it with LiDAR range to give a 3D object position.
- A semantic map manager registers objects in a database and publishes persistent RViz markers. The pipeline runs as modular ROS 2 packages with custom message interfaces.

`YOLO-World` `Sensor fusion` `Tracking` `ROS 2` `Gazebo` `Nav2`

<details>
<summary><b>Visual Odometry & SLAM</b> — Classical and deep visual SLAM, VO benchmarking, camera-plus-GPS data collection.</summary>

| Repository | What it is |
|---|---|
| [DROID_slam](https://github.com/thippeswammy/DROID_slam) | Deep visual SLAM extended for monocular, stereo and RGB-D setups, with multi-GPU inference, ARM64 (Jetson) support, and trajectory reconstruction and evaluation. <sub>`PyTorch · CUDA`</sub> |
| [DPVO](https://github.com/thippeswammy/DPVO) | Re-implementation of Deep Patch Visual Odometry, evaluated on KITTI and custom sequences. <sub>`Deep VO`</sub> |
| [ORB_SLAM3](https://github.com/thippeswammy/ORB_SLAM3) · [ROS2 wrapper](https://github.com/thippeswammy/ORB_SLAM3_ROS2) · [ORB_SLAM2](https://github.com/thippeswammy/ORB_SLAM2) | Extended ORB-SLAM with ROS 2 support for mono, stereo, RGB-D and stereo-inertial modes, KITTI and ROS bag tooling, RealSense input, Jetson builds, resource monitoring and trajectory evaluation. <sub>`C++ · ROS 2`</sub> |
| MultipleVo 🔒 | Bench for running several VO methods on the same data, including stereo SOFT, monocular feature-based and dense optical-flow VO, with stored results for comparison. <sub>`Python · OpenCV`</sub> |
| VO2MAP 🔒 | Monocular VO on KITTI and calibrated dashcam footage, aligned with road-map routes (OpenRouteService) to place visual trajectories on a map. <sub>`Camera calibration · map integration`</sub> |
| [RoadTagByCameraGps](https://github.com/thippeswammy/RoadTagByCameraGps) | Android app that records GPS position, device orientation and trajectory alongside the camera, for collecting road data. <sub>`Kotlin · Android sensors`</sub> |

</details>

<details>
<summary><b>ROS 2, Navigation & Autonomous Driving</b> — Mobile-robot simulation, navigation, route-network tools, driving simulation.</summary>

| Repository | What it is |
|---|---|
| [LaneMappingTool](https://github.com/thippeswammy/LaneMappingTool) | Builds the road network an autonomous vehicle follows from noisy recorded paths: spline smoothing, junction logic and bidirectional lanes, exported as a graph for path planning, with editing and analysis views. <sub>`Python · ROS`</sub> |
| [my_bot](https://github.com/thippeswammy/my_bot) · my_bot_2d 🔒 | Differential-drive robot in ROS 2 Humble and Gazebo: URDF with camera and LiDAR, SLAM mapping, Nav2/AMCL navigation, tuned physics and one-command launchers. <sub>`ROS 2 · Nav2 · Gazebo`</sub> |
| [sdf_to_nav_mesh](https://github.com/thippeswammy/sdf_to_nav_mesh) · [3d_robot](https://github.com/thippeswammy/3d_robot) | Converts Gazebo SDF worlds into navigation meshes (.ply, .dae, .h5) with terrain metadata, for 3D mesh-based navigation over uneven terrain. <sub>`ROS 2 · mesh navigation`</sub> |
| [Carla](https://github.com/thippeswammy/Carla) | CARLA simulator scripts for traffic generation, scenario control and vehicle-behaviour experiments. <sub>`CARLA · Python`</sub> |
| [ros2_learning](https://github.com/thippeswammy/ros2_learning) | ROS 2 practice workspace. <sub>`ROS 2`</sub> |

</details>

## [Publication](https://thippeswammy.github.io/#publication)

📄 **Vision-Based Odometry: Comparative Analysis on Standard and Custom Datasets for Resource-Limited Vehicle Platforms**  
N Sai Pranay Kumar, **Thippeswamy K S**, Dr. Prithvi Sekhar Pagala · *2026 IEEE DISCOVER, Puttur*

Introduces the Custom GITAM Dataset, a campus-scale visual odometry benchmark recorded on an autonomous ground vehicle with camera, LiDAR and GNSS. The paper compares five monocular VO approaches (feature-based, optical-flow and deep-learning) on KITTI and on this dataset. It measures trajectory accuracy, drift and compute cost on an NVIDIA Jetson Xavier NX, using RTK-GNSS as the reference.

## [Skills](https://thippeswammy.github.io/#skills)

| Area | Skills |
|---|---|
| **Computer Vision & ML** | Object detection, Segmentation, Multi-object tracking, Monocular depth, Pose estimation, Open-vocabulary detection, Auto-labeling & dataset engineering, Model evaluation |
| **3D Vision, SLAM & Robotics** | Visual odometry, Visual / LiDAR SLAM, Sensor fusion, LiDAR–camera calibration, Point-cloud registration (ICP / GICP), Map matching, Navigation (Nav2) |
| **Frameworks & Deployment** | PyTorch, TensorRT, ONNX, CUDA, OpenCV, YOLO, SAM2, CoTracker3, ROS 2, RTAB-Map, GTSAM, Open3D, Jetson |
| **Languages, Tools & Sensors** | Python, C++, Java, Kotlin, MATLAB / Simulink, Git, Linux, CMake, LiDAR, RealSense, Stereo (ZED), IMU / GNSS |

## [Education](https://thippeswammy.github.io/#education)

- **B.Tech, Electronics & Communication Engineering** — GITAM (Deemed to be University), Bengaluru · CGPA 8.55 / 10 · *2022 – 2026*
- **Pre-University** — Sri Chaitanya PU College, Ballari · 70% · *2019 – 2021*

## [More work](https://thippeswammy.github.io/#more-work)

Work outside my current focus, kept here because it shows how I got here: embedded and automotive systems, apps, and the projects I learned to program with.

<details>
<summary><b>Embedded & Automotive Systems</b> — Model-based design, HIL/SIL, CAN, microcontrollers.</summary>

| Repository | What it is |
|---|---|
| [MBD-dSPACE](https://github.com/thippeswammy/MBD-dSPACE) | Vehicle control logic on dSPACE SCALEXIO, built in MATLAB/Simulink and validated with SIL and HIL workflows by comparing simulated and hardware responses. <sub>`Simulink · HIL / SIL`</sub> |
| [MatlabModels](https://github.com/thippeswammy/MatlabModels) | Simulink models for automotive behavioural modelling, sensor interfacing and real-time control on Arduino, Raspberry Pi and STM32. <sub>`MATLAB · Simulink`</sub> |
| [Arduino](https://github.com/thippeswammy/Arduino) | Embedded projects: CAN communication with MCP2515, camera face tracking, obstacle-avoiding car, traffic control and IoT water management. <sub>`C++ · CAN`</sub> |
| [EceProject](https://github.com/thippeswammy/EceProject) | ECE coursework and lab projects: stereo camera processing, ESP8266 and Raspberry Pi IoT, and control systems. <sub>`Embedded · IoT`</sub> |

</details>

<details>
<summary><b>Software, Apps & Games</b> — AI desktop agent, Android and AR apps, DSA practice, early Java projects.</summary>

| Repository | What it is |
|---|---|
| [JarvisControlSystem](https://github.com/thippeswammy/JarvisControlSystem) | AI desktop agent for Windows that controls apps, windows and system settings from typed, spoken or Telegram commands. It checks its own actions, learns macros and supports pluggable LLM backends (Ollama, OpenAI). <sub>`Python · LLM agents`</sub> |
| connect2park 🔒 | Smart parking app with live slot availability, booking and Google Maps navigation, on a Firebase backend. <sub>`Android · Firebase`</sub> |
| [SpeechCalculator](https://github.com/thippeswammy/SpeechCalculator) | Android calculator that evaluates spoken expressions with a custom parser. <sub>`Java · speech recognition`</sub> |
| [AR-Cube-Drop](https://github.com/thippeswammy/AR-Cube-Drop) · [3D Car Racing](https://github.com/thippeswammy/3D-Car-racing-game) | Unity projects: an ARFoundation object-placement app and a 3D racing game. <sub>`Unity · C#`</sub> |
| [NeetCodeProblems](https://github.com/thippeswammy/NeetCodeProblems) | Data-structures and algorithms practice in Java and Kotlin. <sub>`DSA`</sub> |
| [Early Java projects (~20)](https://github.com/thippeswammy?tab=repositories&language=java) | The games and desktop apps I learned to program with: Swing and Greenfoot games (Snake, Maze, Chain Reaction, Tic-Tac-Toe with AI), plus login, launcher and calculator apps. <sub>`Java · OOP`</sub> |

</details>

---

<sub>🔒 = private repository, code available on request. This README is generated from the same data as [thippeswammy.github.io](https://thippeswammy.github.io/).</sub>
