Team Lead: Joseph Stevens - joseph.stevens1@louisiana.edu

Members:
* Nathan Madsen   - nathan.madsen1@louisiana.edu
* Brennan Moeller - Brennan.moeller1@louisiana.edu
* Benjamin Willis - benjamin.willis1@louisiana.edu




# Integration of a UAV to the RoboBoat to aid in task completion and navigation

## Long-term Project Goal
Integrate a drone to the RoboBoat to increase the points gained while completing certain tasks and aid in navigating the courses more efficiently.

## Short-term Goal
To define specific metrics for success.
To complete a working draft of design tools.

## Recent Results Overview

1. QR code and Barcode localization
    * Localization processes can be used to identify QR codes or Barcodes in an image. This may be a useful way to detect the distance between the UAV and ASV. During the localization process a geometric square, "code candidate box", is overlaid the detected QR or Bar code. I believe a distance model could be constructed through machine learning using a simple regression formula. This model could be used to calculate distance depending on the pixel count of the "code candidate box". There are many localization algorithms that are available. **JS**


2. ArUco Marker Detection

	* OpenCV has a ton of information on this. These ArUco Markers can be used for 6 DOF pose estimation in navigation. To me, from what I've read so far, it seems that this this would be a solid way to go if we are going to have a camera on the UAV. **JS**

	* While the ArUco marker could be useful in a landing situation when the UAV is in fairly close proximity of the ASV, it may not be useful at distances longer than 4-5 meters. It may help to increase the size of the ArUco marker, but could cause issues do to a narrow field of view when up close.
	[Dynamic Markers: UAV landing proof of concept](https://arxiv.org/pdf/1709.04981.pdf#:~:text=Whycon%20is%20a%20good%20alternative,and%20for%20Whycon%2013.181%20m.) **JS**

	* Instead of using the traditional fiducial markers in the ArUco library, fractal markers are also available in the ArUco libray. These were designed to work under conditions of occlusion and are acutally composed of several fiducial markers. I think if we are to use ArUco markers, this would be a better option. We will be opperating in an outdoor environment and cannot stop insects and/or small animals such as birds from blocking a portion of the marker. Fractal markers also work better at longer distances. This was shown in: [Fractal Markers: A New Approach for Long-Range Marker Pose Estimation Under Occlusion](https://ieeexplore.ieee.org/document/8890613). It was shown that a 16.3 inch marker could be detected as close as 3 inches and starts dropping at approximately 50 feet until about 80 feet. The fractual marker only adds about 8.1 ms of computing time as well. **JS**

	[Google docs Fractal Markers Library Documentation](https://docs.google.com/document/d/1SdsOTjGdu5o8gy2Ot2FDqYDS9ALgyhOBJcJHOZBR7B4/mobilebasic)

	[Google docs ArUco Library Documentation](https://docs.google.com/document/d/1QU9KoBtjSM2kF6ITOjQ76xqL7H0TEtXriJX5kwi9Kgc/edit#)

3. Other Marker Dection Options
	* I am currently looking into other marker detection options. I need to read through this research:
		* Whycon Markers: [Dynamic Markers: UAV landing proof of concept](https://arxiv.org/pdf/1709.04981.pdf#:~:text=Whycon%20is%20a%20good%20alternative,and%20for%20Whycon%2013.181%20m.)


4. The [House of Quality, Gantt chart, and function tree](http://crawlab.org/owncloud/index.php/apps/files/?dir=%2Fshared%2FRoboBoat%2FRoboBoat2021%2FSeniorProjects_Design_Tools) are ready for review. The specification sheet is being worked on, but is not complete. We are still determining bounds for some aspects of the UAV and the required components. **BM**


5. Compiled a list of potential UAVs
	* The potential UAVs have been put on a list on the GitHub Project board for us to reference as the project develops. The UAVs vary in size, price, and included parts such as sensors, GPS, and controllers. Some of the UAVs come ready-to-fly while others are near-ready-to-fly.


6. Mapping Possibilities
	* GMapping creates a 2-D occupancy grid map. It has limits with the range of the laser, how long the map updates, and how many points are needed to build an accurate map. As Dr. Vaughan stated in the pervious meeting; there are better options than this type of mapping, but there is a lot of resources for this type of mapping. As a team it was decided that this type of mapping is not the route to take due to the fact that there are better options. **BW**

	* With Sonar Mapping, Ultrasonic Sensors are used to emit a soundwave and receive the soundwave. This can create a 3-D map, but has its limits in the range, temperature levels and surface reflection of the sound. There are different ranges in frequency depending on what is used, but the most common frequency range is 30-80 kHZ for a long range distance and the frequency can go up to 500 kHz in some applications. The beacon (ALP-365 Beacon) that is used in the competition for the RoboBoat competition uses a frequency between 25 - 40 kHz in .5 kHz increments. That is about as far as I was able to get, but from what I have found it appears this may not be an option to explore much further. **BW**

	* Other mapping possibilities that were researched include RTAB-Map and Hector mapping. RTAB-Map can subscribe to either stereo camera or Lidar data. The Hector mapping package subscribes only to Lidar data, and it leverages the high update rate of most modern Lidar systems. Both of these mapping packages can utilize the loop closure method that detects when the sensor has made it back to its starting position. By recognizing when it reaches its starting position, the algorithm is able to make corrections to its recorded map which increases the maps accuracy. I have a research paper by MIT that used multiple drones and a lidar system for mapping that integrated the maps real time. They refer to the package as C-SLAM in the paper, but I have not been able to find anymore information on this SLAM package. **NM**

7. * Some common hardware that can be used to make sure a UAV can be flown autonomously include the Pixhawk4 flight controller, NAVIO2 autopilot pi board hat, IMU sensors, many different types of cameras, odometry sensors, barometer sensors, different types of depth sensors, and different GPS/GNSS systems. Many different degrees of precision can be achieved with these types of sensors. RTK GNSS/GPS systems can be used to achieve cm precision. This would allow for more precise data on the UAV's location to be recorded. However, if different sensor's data is simultaneously collected and fed into certain filter algorithms decent precision can be achieved. It isn't cm, but it is still useful and an option. The thing I have not been able to determine yet is what is the "best" way for us to achieve autonomous flight from the UAV we will eventually pick. **BM**


## Questions/Comments
1. Would one way to achieve our end goal of aiding the boat in navigating the course be to use the drone as "pin" for the boat to follow like humans do when someone drops a pin on their location? **BM**

2. I know that the WAM-V is already using some sort of object recognition algorithm, is this already implemented on the RoboBoat? If not, can we use the same algorithm? If so, I would like to know it's name, so I can beggin learning about it. **JS**

## Plan for the next two weeks
1. We are still waiting to register with RoboNation.
2. Finish a first draft of a specification sheet.
3. Determine the "best" solutions for our product sub-functions by completing a morphological chart. 
4. Begin compiling an Evaluation Matrix.


### What are your next steps?
1. I (Brennan) plan to continue diving into ROS. I have some Udemy courses that I can leverage to learn ROS basics. I also found some files on the PX4 Vision that I can leverage to learn and start to write some initial scripts that will fly the UAV in a prescribed area.  

2. I (Nathan) plan to work on an online course which will include learning the basic control of a drone, drone exploration, and drone navigation.

3. I (Ben) plan to get into understanding the basics of ROS and I will be helping out wherever I am needed. I (as well as the rest of the team) will also be working on adding more to the Specification Sheet and the Evaluation Matrix.

4. I (Joseph) have created an account on robotigniteacademy.com and will be starting with the programming drones with ROS course. I will also be doing some more reading on different kinds of markers used for pose estimation and distance calculation. I am also going to go through this tutorial on ArUco markers being used in ROS to estimate the ArUco markers 6 DOF pose: [ArUco Marker Tutorial](http://ros-developer.com/2017/04/23/aruco-ros/)


### What work do you expect to have done by next report? What results to you expect?
By next report, we plan to have a finished first draft of the specification sheet, a morphological chart, and a working draft of an Evaluation Matrix with the "best" design for this application determined.

### Are we on schedule with respect to the GitHub Project and/or Gantt Chart?
Yes we would say that we are on schedule for this semester, but need to speed up our decision making process on actual hardware and UAVs that we will need to complete this project.

# Long-term planning
 As a team we would like to be able to have the success of this project defined in the next few weeks. We want to have the final design concept decided by mid October. We would like to have the drone flying autonomously with a camera attached to the bottom of it within a pre-defined area by the begging of next semester. We want to fully test this design by late February, early March to have time to correct the flaws in the coding and design. We are looking to have the UAV fly autonomously with a camera attached to it, map the course, raise/deliver an object, and have the UAV integrated with ASV by the end of next semester.

## Up coming Paper Deadlines
### Senior projects progress report due every other Thursday starting September 16, 2020.

## Administrative Deadlines
### None yet. Waiting on rules form RoboNation to be released.
