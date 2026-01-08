<div align="center">
  <p>
      <img width="100%" src="" alt="Nextits Data Processing Banner">
  </p>

[English](../README.md) | [한국어](./README_ko.md) | 简体中文

<!-- icon -->
![python](https://img.shields.io/badge/python-3.8~3.12-aff.svg)
![os](https://img.shields.io/badge/os-linux%2C%20win%2C%20mac-pink.svg)
[![License](https://img.shields.io/badge/license-Apache_2.0-green)](../LICENSE)



**Nextits Data Processing 是一个用于处理和转换多模态数据（文本、图像、音频、PDF）的集成管道系统**

</div>

# Nextits Data Processing
[![Framework](https://img.shields.io/badge/Python-3.8+-blue)](#)
[![Pipeline](https://img.shields.io/badge/Pipeline-Text%20%7C%20Image%20%7C%20Audio-orange)](#)
[![Document](https://img.shields.io/badge/Document-PDF%20Processing-green)](#)

> [!TIP]
> Nextits Data Processing 提供了一个集成解决方案，可将各种数据格式转换为适合 AI 的格式。
>
> 它可以高效处理包括文本、图像、音频和 PDF 在内的多模态数据。


**Nextits Data Processing** 是一个强大的管道系统，可将各种数据格式转换为**结构化的、AI 友好的数据**。它可以高效处理和转换包括文本、图像、音频和 PDF 文档在内的多模态数据。

### 核心功能

- **集成管道系统 (pipe/)**  
  用于处理文本、图像和音频数据的统一管道，能够以一致的方式处理各种数据格式。

- **文档矫正 (UVDoc/)**  
  自动校正文档图像失真以提高 OCR 准确性。该模块基于 [UVDoc 项目](https://github.com/tanguymagne/UVDoc)。

- **高性能推理引擎 (vllm/)**  
  用于大型语言模型的高效推理引擎。该模块基于 [vLLM 项目](https://github.com/vllm-project/vllm)。

## 📣 最近更新

### 🔥 2025.01: 多模态数据处理管道发布

- **集成管道系统**:
  - 文本处理管道 (`pipeline_text.py`)
  - 图像处理管道 (`pipeline_image.py`)
  - 音频处理管道 (`pipeline_sound.py`)
  - 统一文件处理器 (`run_file_processor.py`)

- **文档矫正功能**:
  - 基于 UVDoc 的文档图像失真校正
  - 高质量文档扫描结果

- **高性能推理支持**:
  - 基于 vLLM 的高效模型推理
  - 大规模批处理支持

## ⚡ 快速开始

### 1. 安装

```bash
# 安装基本依赖
pip install -r requirements.txt

# 安装 UVDoc 依赖（用于文档矫正）
cd UVDoc
pip install -r requirements_demo.txt

# 安装 vLLM 依赖（用于高性能推理）
cd vllm
pip install -e .
```

### 2. 运行管道

```bash
# 文本处理管道
python pipe/pipeline_text.py

# 图像处理管道
python pipe/pipeline_image.py

# 音频处理管道
python pipe/pipeline_sound.py

# 统一文件处理器
python pipe/run_file_processor.py
```

### 3. 文档矫正

```bash
cd UVDoc
python demo.py --input_path <输入图像路径> --output_path <输出图像路径>
```

## 📂 项目结构

```
nextits_data/
├── pipe/                      # 集成管道系统
│   ├── pipeline_text.py       # 文本处理管道
│   ├── pipeline_image.py      # 图像处理管道
│   ├── pipeline_sound.py      # 音频处理管道
│   ├── run_file_processor.py  # 统一文件处理器
│   ├── main_pipe/             # 主管道模块
│   ├── text_pipe/             # 文本处理模块
│   └── image_pipe/            # 图像处理模块
├── UVDoc/                     # 文档矫正（基于外部项目）
└── vllm/                      # 高性能推理引擎（基于外部项目）
```

## 🔧 主要模块

### 管道系统 (pipe/)

用于处理多模态数据的集成管道系统。

**主要功能:**
- 文本数据预处理和转换
- 图像数据处理和特征提取
- 音频数据处理和转换
- 支持各种文件格式

**使用示例:**
```python
from pipe.pipeline_text import TextPipeline

pipeline = TextPipeline()
result = pipeline.process(input_data)
```

### 文档矫正 (UVDoc/)

用于自动校正文档图像失真的模块。

> [!NOTE]
> 该模块基于 [UVDoc 项目](https://github.com/tanguymagne/UVDoc)。
> UVDoc 是一个基于深度学习的解决方案，可有效校正文档图像失真。

**主要功能:**
- 自动检测文档图像失真
- 高质量文档图像恢复
- 支持各种失真类型

**参考资料:**
- [UVDoc GitHub 仓库](https://github.com/tanguymagne/UVDoc)
- [UVDoc 论文](https://arxiv.org/abs/2405.02529)

### 高性能推理引擎 (vllm/)

用于大型语言模型的高效推理引擎。

> [!NOTE]
> 该模块基于 [vLLM 项目](https://github.com/vllm-project/vllm)。
> vLLM 是一个开源库，可显著提高大型语言模型的推理速度。

**主要功能:**
- 高速批量推理
- 高效内存管理
- 支持各种模型架构

**参考资料:**
- [vLLM GitHub 仓库](https://github.com/vllm-project/vllm)
- [vLLM 文档](https://docs.vllm.ai/)

## 📊 性能

### 管道处理速度

| 管道 | 处理速度 | 支持格式 |
|------|---------|---------|
| 文本 | 1000+ docs/sec | TXT, JSON, CSV |
| 图像 | 100+ images/sec | JPG, PNG, PDF |
| 音频 | 50+ files/sec | WAV, MP3, FLAC |

## 🛠️ 开发指南

### 要求

- Python 3.8 或更高版本
- CUDA 11.0 或更高版本（用于 GPU）
- 充足的内存（建议至少 16GB）

### 开发环境设置

```bash
# 克隆仓库
git clone <repository_url>
cd nextits_data

# 创建虚拟环境
python -m venv venv
source venv/bin/activate  # Linux/Mac
# venv\Scripts\activate  # Windows

# 安装依赖
pip install -r requirements.txt
```

### 测试

```bash
# 运行单元测试
pytest tests/

# 运行集成测试
pytest tests/integration/
```

## 📝 许可证

本项目根据 Apache 2.0 许可证分发。详情请参阅 [LICENSE](../LICENSE) 文件。

## 🙏 致谢

本项目得益于以下开源项目的帮助：

- **[UVDoc](https://github.com/tanguymagne/UVDoc)**: 文档矫正功能
- **[vLLM](https://github.com/vllm-project/vllm)**: 高性能推理引擎

## 🎓 引用

如果您在研究中使用本项目，请引用以下论文：

### UVDoc
```bibtex
@inproceedings{UVDoc,
  title={{UVDoc}: Neural Grid-based Document Unwarping},
  author={Floor Verhoeven and Tanguy Magne and Olga Sorkine-Hornung},
  booktitle={SIGGRAPH ASIA, Technical Papers},
  year={2023},
  url={https://doi.org/10.1145/3610548.3618174}
}
```

### vLLM
```bibtex
@inproceedings{kwon2023efficient,
  title={Efficient Memory Management for Large Language Model Serving with PagedAttention},
  author={Woosuk Kwon and Zhuohan Li and Siyuan Zhuang and Ying Sheng and Lianmin Zheng and Cody Hao Yu and Joseph E. Gonzalez and Hao Zhang and Ion Stoica},
  booktitle={Proceedings of the ACM SIGOPS 29th Symposium on Operating Systems Principles},
  year={2023}
}
```

## 📧 联系方式

如果您对项目有任何问题或建议，请提交 issue。

## 🌟 贡献

欢迎贡献！请发送 Pull Request 或提交 issue。

---

<div align="center">
Made with ❤️ by Nextits Team
</div>
