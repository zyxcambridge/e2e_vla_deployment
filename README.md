# Adas System DeployMent
# 20241111 by update zhang
## 1. 介绍
本项目是用于部署adas系统的docker镜像，包括adas的各个模块，如：adas主控、adas相机、adas雷达、adas毫米波雷达、adas激光雷达、adas高精度地图、adas感知、adas决策、adas控制、adas仿真等。

## 2. 使用方法
### 2.1. 安装docker
请参考docker官方文档进行安装。

### 2.2. 下载镜像
请使用以下命令下载镜像：
```
docker pull registry.cn-hangzhou.aliyuncs.com/adas_system/adas_system:latest
```

### 2.3. 运行容器
请使用以下命令运行容器：
```
docker run -it --name adas_system -v /dev:/dev -v /tmp/.X11-unix:/tmp/.X11-unix -v /home/adas_system/adas_system:/home/adas_system/adas_system -e DISPLAY=$DISPLAY registry.cn-hangzhou.aliyuncs.com/adas_system/adas_system:latest
```

### 2.4. 进入容器
请使用以下命令进入容器：
```
docker exec -it adas_system /bin/bash
```

### 2.5. 运行adas系统
请使用以下命令运行adas系统：
```
cd /home/adas_system/adas_system
source /home/adas_system/adas_system/setup.bash
ros2 launch adas_system adas_system.launch.py
```

## 3. 注意事项
请确保在运行adas系统之前，已经正确安装了所有依赖项，并且已经正确配置了环境变量。

