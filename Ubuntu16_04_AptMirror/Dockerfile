FROM     ubuntu:16.04

MAINTAINER Haoming.Ju "juhaoming@outlook.com"

# 更新软件源
COPY ./sources.list /etc/apt/sources.list
RUN apt-get update
RUN apt-get install -y apt-mirror

# 安装apt-mirror
ARG BASE_PATH=/mnt/apt-mirror/ubuntu/16.04
ARG MIRROR_PATH=$BASE_PATH/mirror
ARG SKEL_PATH=$BASE_PATH/skel
ARG VAR_PATH=$BASE_PATH/var

## 创建存储路径所需的文件夹
RUN mkdir -p $BASE_PATH
RUN mkdir -p $MIRROR_PATH
RUN mkdir -p $SKEL_PATH
RUN mkdir -p $VAR_PATH

## 更新apt-mirror的路径和定时任务的配置文件
COPY ./mirror.list /etc/apt/mirror.list
COPY ./apt-mirror /etc/cron.d/apt-mirror

# 安装nginx, 为了用http协议发布自建仓库
#RUN apt-get install -y nginx
#COPY ./apt-mirror.conf /etc/nginx/conf.d/apt-mirror.conf
#RUN nginx -t

EXPOSE 80
