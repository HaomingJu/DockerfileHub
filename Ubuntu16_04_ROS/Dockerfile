# sshd
#
# VERSION               0.0.1

FROM     ubuntu:16.04
MAINTAINER Haoming.Ju "thatcher@dotcloud.com"

# make sure the package repository is up to date
COPY ./sources.list /etc/apt/sources.list

RUN apt-key adv --keyserver 'hkp://keyserver.ubuntu.com:80' --recv-key C1CF6E31E6BADE8868B172B4F42ED6FBAB17C654

RUN apt-get update

RUN apt-get install -y ros-kinetic-ros-base

RUN rosdep init && rosdep fix-permissions && rosdep update

RUN ["/bin/bash", "-c", "echo 'source /opt/ros/kinetic/setup.bash' >> ~/.bashrc && source ~/.bashrc "]

#export ROS_HOSTNAME=192.168.1.1
#export ROS_MASTER_URI=http://192.168.1.1:11311

