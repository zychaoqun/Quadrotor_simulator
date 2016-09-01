# Quadrotor_simulator
This project is based on the simulator in <http://ardupilot.org/dev/docs/using-rosgazebo-simulator-with-sitl.html> with some changes.
This repository describes how to build a simulation environment for quadrotor. In this tutorial, we will introduce how to build the simulation environment for quadrotor step by step.  

##1.Installation ardupilot

    git clone https://github.com/alexbuyval/ardupilot  
    git checkout RangeFinderSITL2  
    
##2.Install the ros indigo and create a catkin workspace  

     sudo apt-get install ros-indigo-octomap-msgs  
     sudo apt-get install ros-indigo-mavlink  
 then install all the required package  

     cd catkin_ws/src  
     git clone https://alexbuyval@bitbucket.org/alexbuyval/arducopter_sitl_ros.git  
     git clone https://github.com/PX4/mav_comm.git  
     git clone https://github.com/alexbuyval/rotors_simulator.git  
     git clone https://github.com/ethz-asl/glog_catkin.git  
     git clone https://github.com/catkin/catkin_simple.git  
     cd rotors_simulator  
     git checkout sonar_plugin
     cd ../..  
     wstool init src  
     wstool set -t src mavros --git https://github.com/zychaoqun/mavros  
     wstool update -t src  
     rosdep install --from-paths src --ignore-src --rosdistro indigo -y  
here I have change the interface.cpp and param.cpp so as to avoid the build error in the next step.

##3.Build  
     cd catkin_ws/src
     catkin_make

