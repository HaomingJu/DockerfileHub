# sshd
#
# VERSION               0.0.1

FROM     ubuntu:16.04
MAINTAINER Haoming.Ju "thatcher@dotcloud.com"

COPY ./sources.list /etc/apt/sources.list

RUN apt-key adv --keyserver 'hkp://keyserver.ubuntu.com:80' --recv-key C1CF6E31E6BADE8868B172B4F42ED6FBAB17C654

RUN apt-get update

RUN apt-get install -y ros-kinetic-ros-base

RUN rosdep init

RUN rosdep fix-permissions

#RUN rosdep update

RUN ["/bin/bash", "-c", "echo 'source /opt/ros/kinetic/setup.bash' >> ~/.bashrc && source ~/.bashrc "]

RUN apt-get install -y openssh-server

RUN mkdir /var/run/sshd

RUN echo 'root:1' |chpasswd

RUN sed -i 's/prohibit-password/yes/g' /etc/ssh/sshd_config

EXPOSE 22
CMD    ["/usr/sbin/sshd", "-D"]
