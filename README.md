# Grasping Assuming Symmetry

## 1. Introduction

The "Grasping Assuming Symmetry" project utilizes symmetry in objects to optimize grasping points. By leveraging depth-sensing technology and innovative algorithms, this project aims to enhance robotic manipulation for stable and efficient interactions with various objects in real-world scenarios.

## 2. Implementation

### Step 1: Downsampling and Major Plane Removal

- The point cloud data is downsampled using a voxel grid for computational efficiency.
- RANSAC plane segmentation removes the plane, leaving only the object of interest in the point cloud.

![1](https://github.com/upasana099/Grasping-Assuming-Symmtery/assets/89516193/f067acc1-8f0f-47a5-a177-642fa322acc1)


### Step 2: Point Cloud Completion

- A symmetry-based approach is employed to complete the point cloud by identifying the optimal symmetry plane considering visibility constraints.
- The algorithm generates all possible planes and selects the one with the highest score, resulting in a comprehensive point cloud.

![2](https://github.com/upasana099/Grasping-Assuming-Symmtery/assets/89516193/855a57db-f55f-4720-9800-1c5380c349d5)


### Step 3: Normal Estimation

- Normals are calculated using pcl::NormalEstimation class, based on the local neighborhood of each point.
- KDTree ensures efficient spatial neighbor searching.
-  Normals are visualized as arrows emanating from points in the point cloud.

![WhatsApp Image 2023-10-13 at 5 43 53 PM](https://github.com/upasana099/Grasping-Assuming-Symmtery/assets/89516193/37744769-99e7-4a4f-97f0-e2f5f8ee5103)


### Step 4: Grasp Detection

- Grasp contacts are calculated for the robot based on the completed 3D point cloud.
- Steps include input parameters, nearest point search, angle calculation, and determining the best grasp.
![WhatsApp Image 2023-10-13 at 5 46 48 PM](https://github.com/upasana099/Grasping-Assuming-Symmtery/assets/89516193/07bf0a69-006c-47be-9570-787537ddc7fe)


## 3. scenarios of Point Cloud Completion

- **Case 1:** Coke can
- **Case 2:** Beer can
- **Case 3:** Cricket ball
- **Case 4:** Hammer (requires tuning for proper functionality)

## 4. Learning Outcome

- The project represents a significant advancement in robotic manipulation by harnessing object symmetry and integrating depth-sensing technology.
- The systematic approach from downsampling to grasp detection optimizes interaction with 3D point cloud data.
- Tested objects range from simple cans to complex shapes like a cricket ball, showcasing the versatility of the methodology.

## 5. How to Run the Code?

1. Build the code and source the workspace.
2. **Terminal 1:** `ros2 launch vbm_project_env simulation.launch.py`
3. **Terminal 2:** `ros2 run vbm_project_env sample_object`
4. **Terminal 3:** `rviz2` (to observe the point cloud by adding Topics)

### KINDLY REFER TO THE REPORT TO REFER THE RESULTS
