# Adas System DeployMent
## 1. 介绍
本项目旨在逐步部署先进的自动驾驶系统，涵盖以下三种关键技术路径：

1. **端到端（End-to-End）自动驾驶系统**：该阶段的目标是构建一个能够直接从环境感知数据（如摄像头图像、激光雷达点云等）生成车辆控制指令（如转向、加速或减速）的完整系统。端到端方法试图通过单一模型简化自动驾驶的决策过程，减少对复杂子系统的依赖。

2. **端到端结合视觉语言模型（VLM, Vision-Language Model）的自动驾驶系统**：在此阶段，我们将在端到端架构的基础上，引入视觉语言模型来增强系统的理解和决策能力。通过融合视觉信息与自然语言处理，使自动驾驶系统能更好地理解复杂的交通场景，比如识别路标指示、理解交通规则等，从而做出更加安全和合理的驾驶决策。

3. **视觉-语言-动作（VLA, Vision-Language-Action）自动驾驶系统**：最终阶段的目标是开发一个高度集成的自动驾驶系统，它不仅能够基于视觉和语言信息作出决策，还能有效执行这些决策。VLA系统旨在通过更深层次的多模态融合，实现更为精准和灵活的自动驾驶功能，以应对更加复杂多变的现实驾驶环境。

每个阶段都将包括以下几个关键步骤：
- **需求分析与方案设计**：明确项目目标，设计技术路线图。
- **数据收集与预处理**：获取高质量的数据集，包括但不限于图像、视频、点云数据等，并对其进行必要的清洗和标注。
- **模型选择与训练**：基于项目需求选择合适的模型架构，利用收集的数据集进行训练。
- **系统集成与测试**：将训练好的模型集成到自动驾驶平台中，进行模拟及实车测试，确保系统稳定性和安全性。
- **持续优化与迭代**：根据测试反馈不断调整优化模型和算法，提升系统性能。

通过这三个阶段的实施，本项目期望能够推动自动驾驶技术的发展，为未来智能交通系统提供强有力的技术支持。

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

