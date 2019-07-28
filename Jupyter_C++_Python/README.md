## 简述
本镜像基于`jupyter/base-notebook`构建而来

支持`Python3` 以及`C++11` `C++14` `C++17`

目前还未支持生成PDF文档 :(

## 构建

**构建**
```
sudo docker build -t IMAGE_NAME:TAG DOCKERFILE_PATH
```

## 容器生成

```
sudo docker run -d -P --name CONTAINER_NAME IMAGE_NAME
```

## 运行

**查看端口号**

```
sudo docker port CONTAINER_NAME 8888
```
jupyter 镜像的访问端口是8888, 要进行查看将其映射到了服务器的哪个端口.


**查看token**

```
sudo docker log --tail 100 CONTAINER_NAME
```

打开浏览器输入

```
localhost:xxxx
# xxxx 为查询到的端口号
```

在打开的页面上填入token进行访问
