---
title: Lab5 ROS配置
tags: 14353051 邓玲
grammar_footnote: true
grammar_cjkEmphasis: true
grammar_cjkRuby: true
grammar_plantuml: true
---

## ROS配置流程

1.	首先要查看自己的ubuntu的版本：
按住ctrl+alt+t打开一个终端，在里面输入：  

![enter description here][1]
 
2. Setup your sources.list
sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'

![enter description here][2]

3. Set up your keys
  sudo apt-key adv --keyserver hkp://ha.pool.sks-keyservers.net:80 --recv-key 0xB01FA116
sudo apt-get install libgl1-mesa-dev-lts-utopic

![enter description here][3]

 4.  Desktop-Full Install: (Recommended) : 
sudo apt-get install ros-jade-desktop-full

![enter description here][4]

 5. Desktop Install:
sudo apt-get install ros-jade-desktop

![enter description here][5]

 6. ROS-Base: (Bare Bones) ROS package, build, and communication libraries. No GUI tools. 
sudo apt-get install ros-jade-ros-base

![enter description here][6]

 7. Individual Package:
sudo apt-get install ros-jade-slam-gmapping

![enter description here][7]

 8. To find available packages, use: 
apt-cache search ros-jade

![enter description here][8]

9. Initialize rosdep
Before you can use ROS, you will need to initialize rosdep. rosdep enables you to easily install system dependencies for source you want to compile and is required to run some core components in ROS. 
sudo rosdep init
rosdep update

![enter description here][9]

 10. Environment setup
source /opt/ros/jade/setup.bash
Getting rosinstall
sudo apt-get install python-rosinstall

![enter description here][10]

 $ apt-get source ros-jade-laser-pipeline
 
 ![enter description here][11]
 
11. 配置心得：
     最后一步出现了一点小问题，但是之前的步骤都配置的很流畅，后来这个问题还待解决，此次配置ROS基本都是比较顺利，之时话费在等待的时间比较多，加之开始的时候由于粗心大意，所以导致后面的过程有很多失败了，后来就放弃，静下心来等第二次再重新配置就成功了


  [1]: http://7xrn7f.com1.z0.glb.clouddn.com/16-11-7/6667840.jpg
  [2]: http://7xrn7f.com1.z0.glb.clouddn.com/16-11-7/84820975.jpg
  [3]: http://7xrn7f.com1.z0.glb.clouddn.com/16-11-7/84820975.jpg
  [4]: http://7xrn7f.com1.z0.glb.clouddn.com/16-11-7/16993558.jpg
  [5]: http://7xrn7f.com1.z0.glb.clouddn.com/16-11-7/8925013.jpg
  [6]: http://7xrn7f.com1.z0.glb.clouddn.com/16-11-7/61338893.jpg
  [7]: http://7xrn7f.com1.z0.glb.clouddn.com/16-11-7/50982846.jpg
  [8]: http://7xrn7f.com1.z0.glb.clouddn.com/16-11-7/61395617.jpg
  [9]: http://7xrn7f.com1.z0.glb.clouddn.com/16-11-7/3841229.jpg
  [10]: http://7xrn7f.com1.z0.glb.clouddn.com/16-11-7/2435380.jpg
  [11]: http://7xrn7f.com1.z0.glb.clouddn.com/16-11-7/20749732.jpg
