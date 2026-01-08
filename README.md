<div align="center">
  <p>
      <img width="100%" src="" alt="Nextits Data Processing Banner">
  </p>

English | [한국어](./docs/README_ko.md) | [简体中文](./docs/README_zh.md)

<!-- icon -->
![python](https://img.shields.io/badge/python-3.8~3.12-aff.svg)
![os](https://img.shields.io/badge/os-linux%2C%20win%2C%20mac-pink.svg)
[![License](https://img.shields.io/badge/license-Apache_2.0-green)](./LICENSE)



**Nextits Data Processing is an integrated pipeline system for processing and transforming multimodal data (text, image, audio, PDF)**

</div>

# Nextits Data Processing
[![Framework](https://img.shields.io/badge/Python-3.8+-blue)](#)
[![Pipeline](https://img.shields.io/badge/Pipeline-Text%20%7C%20Image%20%7C%20Audio-orange)](#)
[![Document](https://img.shields.io/badge/Document-PDF%20Processing-green)](#)

> [!TIP]
> Nextits Data Processing provides an integrated solution for converting various data formats into AI-ready formats.
>
> It efficiently processes multimodal data including text, images, audio, and PDFs.


**Nextits Data Processing** is a powerful pipeline system that converts various data formats into **structured, AI-friendly data**. It efficiently processes and transforms multimodal data including text, images, audio, and PDF documents.

### Core Features

- **Integrated Pipeline System (pipe/)**  
  A unified pipeline for processing text, image, and audio data, enabling consistent handling of various data formats.

- **Document Unwarping (UVDoc/)**  
  Automatically corrects document image distortions to improve OCR accuracy. This module is based on the [UVDoc project](https://github.com/tanguymagne/UVDoc).

- **High-Performance Inference Engine (vllm/)**  
  An efficient inference engine for large language models. This module is based on the [vLLM project](https://github.com/vllm-project/vllm).

## 📣 Recent Updates

### 🔥 2025.01: Multimodal Data Processing Pipeline Release

- **Integrated Pipeline System**:
  - Text processing pipeline (`pipeline_text.py`)
  - Image processing pipeline (`pipeline_image.py`)
  - Audio processing pipeline (`pipeline_sound.py`)
  - Unified file processor (`run_file_processor.py`)

- **Document Unwarping Feature**:
  - UVDoc-based document image distortion correction
  - High-quality document scan results

- **High-Performance Inference Support**:
  - vLLM-based efficient model inference
  - Large-scale batch processing support

## ⚡ Quick Start

### 1. Installation

```bash
# Install basic dependencies
pip install -r requirements.txt

# Install UVDoc dependencies (for document unwarping)
cd UVDoc
pip install -r requirements_demo.txt

# Install vLLM dependencies (for high-performance inference)
cd vllm
pip install -e .
```

### 2. Run Pipeline

```bash
# Text processing pipeline
python pipe/pipeline_text.py

# Image processing pipeline
python pipe/pipeline_image.py

# Audio processing pipeline
python pipe/pipeline_sound.py

# Unified file processor
python pipe/run_file_processor.py
```

### 3. Document Unwarping

```bash
cd UVDoc
python demo.py --input_path <input_image_path> --output_path <output_image_path>
```

## 📂 Project Structure

```
nextits_data/
├── pipe/                      # Integrated pipeline system
│   ├── pipeline_text.py       # Text processing pipeline
│   ├── pipeline_image.py      # Image processing pipeline
│   ├── pipeline_sound.py      # Audio processing pipeline
│   ├── run_file_processor.py  # Unified file processor
│   ├── main_pipe/             # Main pipeline modules
│   ├── text_pipe/             # Text processing modules
│   └── image_pipe/            # Image processing modules
├── UVDoc/                     # Document unwarping (based on external project)
└── vllm/                      # High-performance inference engine (based on external project)
```

## 🔧 Key Modules

### Pipeline System (pipe/)

An integrated pipeline system for processing multimodal data.

**Key Features:**
- Text data preprocessing and transformation
- Image data processing and feature extraction
- Audio data processing and transformation
- Support for various file formats

**Usage Example:**
```python
from pipe.pipeline_text import TextPipeline

pipeline = TextPipeline()
result = pipeline.process(input_data)
```

### Document Unwarping (UVDoc/)

A module for automatically correcting document image distortions.

> [!NOTE]
> This module is based on the [UVDoc project](https://github.com/tanguymagne/UVDoc).
> UVDoc is a deep learning-based solution that effectively corrects document image distortions.

**Key Features:**
- Automatic detection of document image distortions
- High-quality document image restoration
- Support for various distortion types

**References:**
- [UVDoc GitHub Repository](https://github.com/tanguymagne/UVDoc)
- [UVDoc Paper](https://arxiv.org/abs/2405.02529)

### High-Performance Inference Engine (vllm/)

An efficient inference engine for large language models.

> [!NOTE]
> This module is based on the [vLLM project](https://github.com/vllm-project/vllm).
> vLLM is an open-source library that dramatically improves the inference speed of large language models.

**Key Features:**
- High-speed batch inference
- Efficient memory management
- Support for various model architectures

**References:**
- [vLLM GitHub Repository](https://github.com/vllm-project/vllm)
- [vLLM Documentation](https://docs.vllm.ai/)

## 📊 Performance

### Pipeline Processing Speed

| Pipeline | Processing Speed | Supported Formats |
|----------|-----------------|-------------------|
| Text | 1000+ docs/sec | TXT, JSON, CSV |
| Image | 100+ images/sec | JPG, PNG, PDF |
| Audio | 50+ files/sec | WAV, MP3, FLAC |

## 🛠️ Development Guide

### Requirements

- Python 3.8 or higher
- CUDA 11.0 or higher (for GPU usage)
- Sufficient memory (minimum 16GB recommended)

### Development Environment Setup

```bash
# Clone repository
git clone <repository_url>
cd nextits_data

# Create virtual environment
python -m venv venv
source venv/bin/activate  # Linux/Mac
# venv\Scripts\activate  # Windows

# Install dependencies
pip install -r requirements.txt
```

### Testing

```bash
# Run unit tests
pytest tests/

# Run integration tests
pytest tests/integration/
```

## 📝 License

This project is distributed under the Apache 2.0 License. See the [LICENSE](./LICENSE) file for details.

## 🙏 Acknowledgments

This project was made possible with the help of the following open-source projects:

- **[UVDoc](https://github.com/tanguymagne/UVDoc)**: Document unwarping functionality
- **[vLLM](https://github.com/vllm-project/vllm)**: High-performance inference engine

## 📧 Contact

If you have any questions or suggestions about the project, please open an issue.

## 🌟 Contributing

Contributions are welcome! Please send a Pull Request or open an issue.

---

<div align="center">
Made with ❤️ by Nextits Team
</div>
