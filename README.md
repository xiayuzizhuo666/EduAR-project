# EduAR - Open-Source Educational AR Platform 
[![License](https://img.shields.io/badge/License-MIT-green.svg)](https://opensource.org/licenses/MIT)
[![Build Status](https://img.shields.io/github/actions/workflow/status/yourname/EduAR/ci.yml?branch=main)](https://github.com/yourname/EduAR/actions)

**Transform classroom learning through affordable augmented reality**

## 🌟 Key Features
- **多模态交互系统**：融合眼动/手势/语音输入
- **轻量化SLAM**：基于ORB-SLAM3优化（[源码](https://github.com/UZ-SLAMLab/ORB_SLAM3)）
- **离线AI推理**：TensorFlow Lite量化模型（<50MB）
- **跨学科内容**：数学/化学/地理可视化工具链

## 🛠️ Tech Stack
| 模块 | 核心技术 | 开源组件 |
|------|----------|----------|
| AR核心 | OpenXR + AR Foundation | [OpenXR Toolkit](https://github.com/OpenXR-Toolkit) |
| AI推理 | ONNX Runtime + TFLite | [MediaPipe](https://github.com/google/mediapipe) |
| 3D渲染 | Three.js + Unity | [Babylon.js](https://github.com/BabylonJS/Babylon.js) |
| 后端服务 | FastAPI + Redis | [Supabase](https://github.com/supabase/supabase) |

## 🚀 快速开始
```bash
# 1. 克隆仓库
git clone --recurse-submodules https://github.com/yourname/EduAR.git

# 2. 安装依赖
cd EduAR && pip install -r requirements.txt

# 3. 启动示例场景（需连接AR设备）
python examples/chemistry_lab.py
