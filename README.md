# EduXR - 教育增强现实教学系统开发平台

[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)
![Platform](https://img.shields.io/badge/Platform-AR%7CVR%7CMR-green)
![Status](https://img.shields.io/badge/Status-Alpha%20Testing-yellow)

## 🚀 项目简介
**EduXR** 是一款面向教育场景的扩展现实（XR）教学系统开发框架，深度融合SLAM定位、多模态交互与边缘AI推理能力，提供从三维课件开发、虚实融合渲染到智能教学分析的全栈解决方案。适配XR2/昇腾系列硬件平台，支持实验仿真、物理光学等核心教学场景。

---

## 🌟 核心特性
- **超低延迟交互**  
  XR2 Gen1 + 动态色温补偿算法，端到端延迟 ≤15ms @4K分辨率
- **多模态教学交互**  
  融合手势识别（MediaPipe Hands）、眼动追踪（未规划）（Pupil Core）、语音指令（Vosk API）的混合输入系统
- **异构AI推理加速**  
  支持昇腾NPU量化模型转换（TVM编译器），推理速度提升3×
- **跨平台兼容性**  
  基于OpenXR标准，无缝对接Unity XR/Unreal Engine/WebAR（Three.js）
- **学科专用工具链**  
  提供Blender→Three.js三维课件开发流水线，集成实验验证引擎

---

## 🛠️ 技术架构
### 硬件架构
| 模块        | 核心组件               | 关键技术                      |
|-------------|------------------------|-----------------------------|
| **主控**    | 骁龙XR2 Gen1          | 定制Linux 5.10显示驱动       |
| **AI加速**  | 昇腾310推理卡          | PyTorch NPU量化工具链        |
| **显示**    | 双2K LCoS光学模组      | DRM/KMS动态色温补偿算法       |
| **传感器**  | Intel RealSense D455   | 多源时空同步（LSL协议）       |



---

## ⚡ 快速开始
### 硬件原型验证

# 使用预构建Docker镜像
docker run -it --privileged eduxr-core:2.0
git lfs pull -I "3D_Models/Classroom_Demo"


### 开发环境部署

# 编译ORB-SLAM3核心模块
git clone https://github.com/UZ-SLAMLab/ORB_SLAM3
mkdir build && cd build
cmake .. -DCMAKE_BUILD_TYPE=Release -DEDUXR_MODE=ON
make -j$(nproc)


---

## 🔧 开发指南
### 实时SLAM优化

// ORBextractor.cc 教学场景参数配置
if (education_mode) {
  contrastThreshold = 0.05;   // 降低对比度阈值
  nfeatures *= 1.5;          // 增加特征点密度
  edgeThreshold = 20;         // 黑板边缘优化
}


### 多模态数据融合

# 时空对齐与意图识别
fusion_pipeline = MultiModalFusion(
  gesture_model=MediaPipeHands(),
  eye_tracker=PupilCore(ip='192.168.1.100'),
  voice_engine=VoskModel('model-education')
)

sync_data = fusion_pipeline.align_timestamps(
  tolerance_ms=3, 
  coordinate_system='blackboard'
)


---

## 🌐 开源生态
| 类型         | 项目                  | 用途                          | 链接                          |
|--------------|-----------------------|-------------------------------|-------------------------------|
| **AR引擎**   | OpenXR Toolkit        | 跨平台XR交互基础              | [GitHub](https://github.com/OpenXR-Toolkit) |
| **AI推理**   | ONNX Runtime          | 昇腾NPU模型部署              | [官网](https://onnxruntime.ai) |
| **3D开发**   | Three.js              | Web端课件渲染                | [文档](https://threejs.org)   |
| **测试框架** | Gazebo Simulator      | 多用户压力测试               | [下载](https://gazebosim.org) |

---

## 🤝 参与贡献
我们欢迎以下形式的贡献：
1. **问题反馈**：通过[Issues]()提交BUG报告
2. **代码提交**：Fork仓库后发起Pull Request
3. **模型扩展**：上传预训练模型至[Model]()
4. **学科插件**：参考[化学验证插件模板]()开发新模块

---

## 📅 开发路线
| 阶段                 | 里程碑                      | 预计周期 |
|----------------------|----------------------------|----------|
| **Alpha 1.0**        | 基础SLAM与手势交互          | 1个月    |
| **Beta 2.0**         | 多模态融合与NPU加速部署     | 3个月    |
| **Release 3.0**      | 化学/物理课程完整支持       | 6个月    |

---

## 许可证
本项目采用 **[Apache License 2.0](LICENSE)** 开源协议，商业使用需遵守[附加条款](docs/COMMERCIAL_USE.md)。

---
