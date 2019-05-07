# Fusion

**[deprecation]: this package has been moved on into alfred-py: http://github.com/jinfagang/alfred , pls head of there for more easy to use and installzatoin**
this libarary contains some helper functions that using in robot or autonomous driving, such as:

- coordinary convert between camera and lidar;
- world coordinate system convertion between camera and image space;
- projection of 3D point onto image;
- 3d box and 2d box convertion;
- extract particular angle point cloud with camera angle of view.


## APIs

1. `data structure`:

Basic data structure that using for provide extrinsic params and intrinsic params. 

```
class FrameCalibrationData(object):
    """
    3x4    p0-p3      Camera P matrix. Contains extrinsic
                          and intrinsic parameters.

    3x3    r0_rect    Rectification matrix, required to transform points
                      from velodyne to camera coordinate frame.

    3x4    tr_velodyne_to_cam    Used to transform from velodyne to cam
                                 coordinate frame according to:
                                 Point_Camera = P_cam * R0_rect *
                                                Tr_velo_to_cam *
                                                Point_Velodyne.
    """
    def __init__(self):
        self.p0 = []
        self.p1 = []
        self.p2 = []
        self.p3 = []
        self.r0_rect = []
        self.tr_velodyne_to_cam = []
```

The basic `FrameCalibrationData` like this, it contains camera P matrix which have extrinsic and intrinsic params. Another transform points from lidar to camera coordinate system.


2. `lidar_to_cam_frame`: convert fusion to camera frame.
3. `get_lidar_point_cloud`: get a particular angle point cloud.
4. more to come



## Copyright

This library written by *Lucas Jin*, if you have any question, you can find me via my blog: www.jinfagang.github.io . License is GPL.
