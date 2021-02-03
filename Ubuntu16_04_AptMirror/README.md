# 使用说明

## Ubuntu16.0.4 apt-mirror Docker

### 1. 镜像构建

```
sudo docker build -t apt-mirror:latest ./

# TODO: 需要另行构建nginx容器用来发布
```
### 2. 运行容器
```
sudo docker run -d -t -p 8011:80 \
    -v /mnt/sdc/docker/:/mnt/apt-mirror/ubuntu/16.04 \
    apt-mirror:latest
```
