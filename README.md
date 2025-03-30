# EduAR - 开源教育AR教学系统
[![License](https://img.shields.io/badge/License-MIT-green.svg)](https://opensource.org/licenses/MIT) 
[![Documentation](https://img.shields.io/badge/docs-passing-brightgreen)](https://yourname.github.io/EduAR-docs)
[![Star History Chart](https://api.star-history.com/svg?repos=yourname/EduAR&type=Date)](https://star-history.com/#yourname/EduAR&Date)

**基于昇腾AI处理器的轻量化AR教育解决方案**

## 🚀 核心特性
- **全场景教学支持**：覆盖数学/化学/地理等学科的三维可视化
- **多模态交互引擎**：眼动+手势+语音融合输入（<5ms延迟）
- **离线AI推理**：昇腾310 NPU支持（50TOPS INT8算力）
- **跨平台部署**：支持Android/Linux/Windows系统

## 🛠️ 技术架构
### 硬件平台
| 模块 | 组件 | 开源支持 | 开发文档 |
|------|------|----------|----------|
| 主控 | 骁龙XR2 Gen1 | [Linux Kernel 5.10](https://www.kernel.org/) | [显示驱动开发指南](docs/hardware/display.md) |
| AI加速 | 昇腾310 NPU | [PyTorch昇腾插件](https://www.hiascend.com/document/detail/zh/CANNCommunityEdition/70RC1alpha001/operatordev) | [模型量化工具](tools/model_quantization/) |
| 显示 | 双2K LCoS | [DRM/KMS框架](https://dri.freedesktop.org/) | [色温补偿算法](software/core/display_ctl/) |

