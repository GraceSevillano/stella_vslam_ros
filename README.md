# stella_vslam_ros

[stella_vslam](https://github.com/stella-cv/stella_vslam)'s ROS package.

## Install instruction

stella_vslam_ros uses submodules. Clone it with `git clone --recursive` or download submodules with `git submodule update --init --recursive`.

## Subscribed topics

### monocular setup

- `camera/image_raw`

### stereo setup

- `camera/left/image_raw`
- `camera/right/image_raw`

### RGBD setup

- `camera/color/image_raw`
- `camera/depth/image_raw`

## Published topics

- `~/camera_pose`
- `~/pointcloud`
- `/tf`

## Parameters

- `odom_frame`
- `map_frame`
- `robot_base_frame`
- `camera_frame`
- `publish_tf`
- `publish_pointcloud`
- `transform_tolerance`
- `use_exact_time` (stereo, RGBD only)

## Usage Example

To run `stella_vslam_ros`, you can execute the following command directly using `rosrun`:

```bash
rosrun stella_vslam_ros run_slam \
    -v /path to/orb_vocab.fbow \
    -c /path to/file.yaml \
    --mask /path to/mask.png \
    --map-db-out /path to/map.msg \
    --eval-log-dir /path to save your SLAM/Evaluation \
    --use-rosbag-timestamps

    
Parameters in the command:

    '-v' : Specifies the path to the vocabulary file for ORB-SLAM.
    `-c`: The configuration file for the camera.
    `--mask`: Path to the mask image for the camera.
    `--map-db-out`: Specifies the output file where the map database will be saved.
    `--eval-log-dir`: Directory to store evaluation logs.
    `--use-rosbag-timestamps`: Ensures that the timestamps from the rosbag are used for synchronization.



