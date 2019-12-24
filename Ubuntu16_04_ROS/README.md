# 使用说明

## Ubuntu16.0.4 ROS Docker
使用清华软件源, 速度会快点

### 1. 镜像构建

```
sudo docker build -t ros_image ./
```
### 2. 运行容器

```
sudo docker container run  --name ros_container -p 2222:22 -i -d ros_image
```

### 3. 登录

```
ssh root@192.168.3.186 -p 2222
```

