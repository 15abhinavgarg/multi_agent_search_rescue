# Final Project - Multi-Agent Hostage Rescue
[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)
![CICD Workflow status](https://github.com/mahimaarora2208/multi_agent_hostage_rescue/actions/workflows/build_and_coveralls.yml/badge.svg)
[![codecov](https://codecov.io/gh/mahimaarora2208/my-ros2-codecov-exp/branch/main/graph/badge.svg?token=AEULJJEMWV)](https://codecov.io/gh/mahimaarora2208/multi_agent_hostage_rescue)

## Project Description 
## Overview
This package simulates a Multi-agent system for search and rescue missions where we use turtlebot3 package in ROS2 Galactic. Our multi-agent system consists of 2- robots that are each specialized for a certain task. 5 turtlebots will be simulated as threats and another 5 turtlebots will be simulating the behavior of security forces (SWAT). The objective of the SWAT bots is to neutralize the threats and then go on to rescue the hostages. The SWAT knows the location of the hostages.

This software is a stepping stone in developing and studying the interaction between security forces and the adversaries. The objective is run all the swat bot simultaneously without bumping into each other.

## Background
The project will help us to gain insight as to how ROS2, Gazebo and RViz works. The goal is to have understanding as to how services and nodes work. Gazebo and Rviz was another tool which we plan to learn through this project
## Final Project Team: Group 1

 - Naveen Mangla (https://github.com/nvnmangla)
 - Mahima Arora  (https://github.com/mahimaarora2208)
 - Abhinav Garg  (https://github.com/15abhinavgarg)

## Development Team
Sprint | #1 | #2 | #3 |
--- | --- | --- | ---
Naveen Mangla | Design Keeper | Design Keeper | Driver
Mahima Arora | Navigator | Driver | Design Keeper
Abhinav Garg | Driver | Navigator | Design Keeper  

### Dependencies/ Assumptions
- OS : Ubuntu 20.04 
- ROS2 Distro : ROS2 Galactic
- Package build type : ```ament_cmake ```
- Package dependencies : ```rclcpp```, ```std_msgs``` 
- ROS2 Galactic Installation : [link](https://docs.ros.org/en/galactic/Installation/Ubuntu-Install-Debians.html)

## Github CI and Codecov

Badges for Github CI and codecov are located at the top of the readme file. 
Additional information on building the software to test for coverage is shown below. 

## License
We are going with a Apache 2.0 License.
## How to Run the ROS Package
### Build Instructions
```
cd <your_ROS2_ws>/src
git clone https://github.com/mahimaarora2208/multi_agent_hostage_rescue.git
cd ..   
rosdep install -i --from-path src --rosdistro galactic -y
colcon build --packages-select multi_agent_hostage_rescue
source . install/setup.bash
source ~/<your ROS2 installation>/opt/ros/galactic/setup.bash
```

## AIP Development

This project will be completed using AIP process with the involvement of 3 programmers using Pair-programming in turns. One of the programmer would be driver while other 2 would be navigator and design keeper. The detailed Product Backlog, Iteration Backlogs and Work Log are mentioned in the link given below :

[Agile Iterative Process](https://docs.google.com/spreadsheets/d/1q81OENQQRdlFShR4wcxflBOyHls5yuyU/edit?usp=sharing&ouid=106728747057946217321&rtpof=true&sd=true)  # TO-D0 Needs to be updated

## Important Links

[Phase 1 Proposal](https://drive.google.com/file/d/1Q7Ae7BqAT_y9z2TzFeA78kWwCRC0aNpY/view?usp=share_link)

[Phase 1 Video](https://drive.google.com/file/d/1j9FvWYJ_o5ee0BTNtfcTjndG6ISZVPU-/view)

[UML Class Diagram Phase 0](https://drive.google.com/file/d/1heAoCuE7eX8_rLSVcIel38kI9LPRAprV/view?usp=share_link)

[Activity Diagram Phase 0](https://drive.google.com/file/d/1A6i3RmnGnbHXjkOn1xPDj8RQZXLSRa0C/view?usp=share_link) 

[UML Class Diagram Phase 1](https://drive.google.com/file/d/1u1SfBBqCDe6bCdI-nSmj1gVIL7Obzjpz/view?usp=share_link)

[Quad Chart](https://drive.google.com/file/d/1Q7Ae7BqAT_y9z2TzFeA78kWwCRC0aNpY/view?usp=share_link)

## Table of Contents
   * [Phase 1 Proposal](https://drive.google.com/file/d/1Q7Ae7BqAT_y9z2TzFeA78kWwCRC0aNpY/view?usp=share_link)
   * [External Dependencies](#external-dependencies)
   * [Installation instructions](#installation-instructions)
   * [Tests](#tests)
   * [Generating documentation](#generating-documentation)
   * [Installation instructions](#installation-instructions)
   * [Activity Diagram](#activity-diagram)
   * [UML Class Diagram](#uml-class-diagram)
   * [Known Issues](#known-issues)

## Sprint Planning Notes
The below link contains combined notes of sprint 1.
[Link](https://docs.google.com/document/d/1eXNISSYEkhZfuHLOKzZ1n7hsESNZ54MTIxZAkLqt3zA/edit?usp=sharing)

## External Dependencies
- [ROS Noeitic](http://wiki.ros.org/noetic)
- [Gazebo](http://gazebosim.org/)
- [Move Base](http://wiki.ros.org/move_base)
- [RViz](http://wiki.ros.org/rviz)


### ROS2 Run TESTS
Run the following commands to test your test cases:
```
colcon build --packages-select multi_agent_hostage_rescue
source install/setup.bash
colcon test --packages-select multi_agent_hostage_rescue
colcon test --event-handlers console_direct+ --packages-select multi_agent_hostage_rescue 
colcon test-result --test-result-base build/multi_agent_hostage_rescue
echo $?
```

## To Generate and Check code coverage
```
sudo apt-get install lcov
cmake -D COVERAGE=ON -D CMAKE_BUILD_TYPE=Debug ../
make
make code_coverage
```
This generates a index.html page in the build/coverage sub-directory that can be viewed locally in a web browser.

## To Generate Doxygen Documentation
open your terminal in your repository
```
doxywizard
```
Follow steps in GUI after selecting path of your repository.