# 使用说明

## Ubuntu16.0.4 Docker
### 1. 镜像构建
```
git clone https://github.com/HaomingJu/Dockerfile_Hub.git
cd Dockerfile_Hub
mkdir Ubuntu16_04/ && cd Ubuntu16_04
mv Dockerfile__ubuntu16_0_4_with_sshserver__ Dockerfile

sudo docker build --rm -t ubuntu16_04_with_ssh
```

镜像构建完成后，可以查看:
```
sudo docker image ls
```

### 2. 实例(容器)创建
创建镜像实例 - 容器

```
sudo docker container run --name self_ubuntu -p 2222:22  -i -d ubuntu16_04_with_ssh
```
创建名为self_ubuntu的实例，系统为Ubuntu16.0.4

进入实例就行必要修改:

```
# 修改root密码
passwd
```

```
# 允许root进行登录
vim /etc/ssh/sshd_config
---
file: /etc/ssh/sshd_config
PermitRootLogin yes
```


### 3. 登录
远程机A, 本地机B. Docker部署在远程机A上.
在本地机B 上登录到远程机A中的Docker 实例.

```
ssh root@192.168.3.133 -p 2222
```
**注意这里的端口指定**
