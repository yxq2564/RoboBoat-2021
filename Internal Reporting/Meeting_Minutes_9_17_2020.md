U.A.V. Team Members:
-   Nathan Madsen -  [nathan.madsen1@louisiana.edu](mailto:nathan.madsen1@louisiana.edu)
-   Brennan Moeller -  [brennan.moeller1@louisiana.edu](mailto:brennan.moeller1@louisiana.edu) 
-   Joseph Stevens -  [joseph.stevens1@louisiana.edu](mailto:joseph.stevens1@louisiana.edu)
-   Benjamin Willis-  [benjamin.willis1@louisiana.edu](mailto:benjamin.willis1@louisiana.edu)

# Meeting Minutes from 9/17/2020

 1) Field of View 
	* Can calculate directly from center of camera. 
	* H = height, V = vertical, D = diagonal 
	* Coordinates as they relate to the field of view should be thought of as a sphere
	* Could do basic trig calculations using distance to get a better idea of the dimensions that could be captured at a defined distance. 

2) Camera Calibration 
	* "QR" codes (Aruco Codes) and April tags are used for this specifically and would be a good area of research 

3) Mapping 
	* Planer map could be G-mapping 
	* Research - How do we draw the map
	* Research - How do we figure out where the UAV is relative to the map, where the ASV is relative to the map, and where both are relative to each other.
	* Research -  S.L.A.M. algorithms that can be used in ROS 

4) Other research to be done for UAV
	* Rasberry pie hat look into tutorials for this
	* Research possible other distance sensing tools besides cameras (LiDAR, Sonar, etc.) 
	* Research and begin practicing how to use MAVROS, rtabmap_ROS, Docker, and apriltags/aruco tags. 

5) Competition
	* Will have a test day or two, first test run or day will most likely be able to use remote control, then fully autonomous from that point on throughout competition.
	* Will be able to remote control vehicle to up to beginning of course - distance determined by the judges.

6) Shared Links
	* [RobotX Machine Learning](https://github.com/CRAWlab/RobotX---Machine-Learning)
	* [RoboBoat Data Sharing Link](https://roboboat.org/data-sharing/)
	* [Docker](https://github.com/Tiryoh/docker_ros-desktop-vnc)
	* [ROS wiki for Aruco](http://wiki.ros.org/aruco_ros)
	* [ROS wiki for Apriltag](http://wiki.ros.org/apriltag_ros)
	* [ROS wiki for Rtabmap](http://wiki.ros.org/rtabmap_ros)
	* [Dr. Vaughan's flicker link for example of Rtabmap with kinect](https://flic.kr/p/2iJgejW)
	* [ROS wiki for Mavros](http://wiki.ros.org/mavros)
