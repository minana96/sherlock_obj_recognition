# *sherki* ROS package

This repository represents the *sherlock_obj_recognition* ROS pacakge, the package that configures and launches object recognition task via [find_object_2d](http://wiki.ros.org/find_object_2d) ROS package. The *sherlock_obj_recognition* package is intended for ROS Melodic. The repository needs to be cloned to the catkin workspace on both robot and the PC, and compiled with following commands:
```bash
cd <catkin_ws_dir>/src
git clone git@github.com:minana96/sherlock_obj_recognition.git
cd ..
catkin_make
```

## Dependencies

The package is dependent on *find_object_2d* ROS pacakge, which can be installed with the following command:
```bash
sudo apt install ros-melodic-find-object-2d
```

## Package content

The package consists of three directories, namely, *config*, *launch* and *pictures*.

### config

The direcotry contains parameter configurations for *find_object_2d* ROS node in *ini* format that are passed as arguments when the node is launched. The definitions of possible *find_object_2d* parameters are available in the [ROS wiki page](http://wiki.ros.org/find_object_2d):
- **find_object_2d.ini**: the default configuration used in all experiments, with input *imageRate* set to 10;
- **input_frame_rate_30.ini**: the configuration used in the image frame rate effect experiment, where *imageRate* parameter is set to 30 for respective treatments; 

### launch

The object recognition task is configured and launched via two launch files:
- **sherlock_object_recognition.launch**: object recognition is launched on the local machine, with the possibility of visualisation with *Rqt* interface when *gui* parameter is set to true; 
- **sherlock_object_recognition_remote.launch**: object recognition is launched on the remote machine that is passed as a parameter. If this launch file is used, it is important that the *sherlock_object_recognition* is cloned and configured on the remote machine. The absolute paths to the *ini* confguration file in use and to the folder containing object that can be detected need to be set accordingly for the remote machine.

### pictures  

The directory contains images of 50 objects that can be detected, in *jpg*, *jpeg* and *png* formats. The images represent 50 most famous paintings of all time, according to [this](https://listsurge.com/top-50-most-famous-paintings/) source, from which the images are obtained from as well.
