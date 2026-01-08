<div align="center">
  <p>
      <img width="100%" src="" alt="Nextits Data Processing Banner">
  </p>

[English](../README.md) | 한국어 | [简体中文](./README_zh.md)

<!-- icon -->
![python](https://img.shields.io/badge/python-3.8~3.12-aff.svg)
![os](https://img.shields.io/badge/os-linux%2C%20win%2C%20mac-pink.svg)
[![License](https://img.shields.io/badge/license-Apache_2.0-green)](../LICENSE)



**Nextits Data Processing은 멀티모달 데이터(텍스트, 이미지, 오디오, PDF)를 처리하고 변환하는 통합 파이프라인 시스템입니다**

</div>

# Nextits Data Processing
[![Framework](https://img.shields.io/badge/Python-3.8+-blue)](#)
[![Pipeline](https://img.shields.io/badge/Pipeline-Text%20%7C%20Image%20%7C%20Audio-orange)](#)
[![Document](https://img.shields.io/badge/Document-PDF%20Processing-green)](#)

> [!TIP]
> Nextits Data Processing은 다양한 형식의 데이터를 AI 학습에 적합한 형태로 변환하는 통합 솔루션을 제공합니다.
>
> 텍스트, 이미지, 오디오, PDF 등 멀티모달 데이터를 효율적으로 처리할 수 있습니다.


**Nextits Data Processing**은 다양한 형식의 데이터를 **구조화된 AI 친화적 데이터**로 변환하는 강력한 파이프라인 시스템입니다. 텍스트, 이미지, 오디오, PDF 문서 등 멀티모달 데이터를 효율적으로 처리하고 변환할 수 있습니다.

### 핵심 기능

- **통합 파이프라인 시스템 (pipe/)**  
  텍스트, 이미지, 오디오 데이터를 처리하는 통합 파이프라인으로, 다양한 형식의 데이터를 일관된 방식으로 처리할 수 있습니다.

- **문서 왜곡 보정 (UVDoc/)**  
  문서 이미지의 왜곡을 자동으로 보정하여 OCR 정확도를 향상시킵니다. 이 모듈은 [UVDoc 프로젝트](https://github.com/tanguymagne/UVDoc)를 기반으로 합니다.

- **고성능 추론 엔진 (vllm/)**  
  대규모 언어 모델의 효율적인 추론을 위한 엔진입니다. 이 모듈은 [vLLM 프로젝트](https://github.com/vllm-project/vllm)를 기반으로 합니다.

## 📣 최근 업데이트

### 🔥 2025.01: 멀티모달 데이터 처리 파이프라인 공개

- **통합 파이프라인 시스템**:
  - 텍스트 처리 파이프라인 (`pipeline_text.py`)
  - 이미지 처리 파이프라인 (`pipeline_image.py`)
  - 오디오 처리 파이프라인 (`pipeline_sound.py`)
  - 통합 파일 처리기 (`run_file_processor.py`)

- **문서 왜곡 보정 기능**:
  - UVDoc 기반 문서 이미지 왜곡 보정
  - 고품질 문서 스캔 결과 생성

- **고성능 추론 지원**:
  - vLLM 기반 효율적인 모델 추론
  - 대규모 배치 처리 지원

## ⚡ 빠른 시작

### 1. 설치

```bash
# 기본 의존성 설치
pip install -r requirements.txt

# UVDoc 의존성 설치 (문서 왜곡 보정 기능 사용 시)
cd UVDoc
pip install -r requirements_demo.txt

# vLLM 의존성 설치 (고성능 추론 기능 사용 시)
cd vllm
pip install -e .
```

### 2. 파이프라인 실행

```bash
# 텍스트 처리 파이프라인
python pipe/pipeline_text.py

# 이미지 처리 파이프라인
python pipe/pipeline_image.py

# 오디오 처리 파이프라인
python pipe/pipeline_sound.py

# 통합 파일 처리
python pipe/run_file_processor.py
```

### 3. 문서 왜곡 보정

```bash
cd UVDoc
python demo.py --input_path <입력_이미지_경로> --output_path <출력_이미지_경로>
```

## 📂 프로젝트 구조

```
nextits_data/
├── pipe/                      # 통합 파이프라인 시스템
│   ├── pipeline_text.py       # 텍스트 처리 파이프라인
│   ├── pipeline_image.py      # 이미지 처리 파이프라인
│   ├── pipeline_sound.py      # 오디오 처리 파이프라인
│   ├── run_file_processor.py  # 통합 파일 처리기
│   ├── main_pipe/             # 메인 파이프라인 모듈
│   ├── text_pipe/             # 텍스트 처리 모듈
│   └── image_pipe/            # 이미지 처리 모듈
├── UVDoc/                     # 문서 왜곡 보정 (외부 프로젝트 기반)
└── vllm/                      # 고성능 추론 엔진 (외부 프로젝트 기반)
```

## 🔧 주요 모듈

### 파이프라인 시스템 (pipe/)

멀티모달 데이터를 처리하는 통합 파이프라인 시스템입니다.

**주요 기능:**
- 텍스트 데이터 전처리 및 변환
- 이미지 데이터 처리 및 특징 추출
- 오디오 데이터 처리 및 변환
- 다양한 파일 형식 지원

**사용 예시:**
```python
from pipe.pipeline_text import TextPipeline

pipeline = TextPipeline()
result = pipeline.process(input_data)
```

### 문서 왜곡 보정 (UVDoc/)

문서 이미지의 왜곡을 자동으로 보정하는 모듈입니다.

> [!NOTE]
> 이 모듈은 [UVDoc 프로젝트](https://github.com/tanguymagne/UVDoc)를 기반으로 합니다.
> UVDoc은 문서 이미지의 왜곡을 효과적으로 보정하는 딥러닝 기반 솔루션입니다.

**주요 기능:**
- 문서 이미지 왜곡 자동 감지
- 고품질 문서 이미지 복원
- 다양한 왜곡 유형 지원

**참고 자료:**
- [UVDoc GitHub Repository](https://github.com/tanguymagne/UVDoc)
- [UVDoc 논문](https://arxiv.org/abs/2405.02529)

### 고성능 추론 엔진 (vllm/)

대규모 언어 모델의 효율적인 추론을 위한 엔진입니다.

> [!NOTE]
> 이 모듈은 [vLLM 프로젝트](https://github.com/vllm-project/vllm)를 기반으로 합니다.
> vLLM은 대규모 언어 모델의 추론 속도를 획기적으로 향상시키는 오픈소스 라이브러리입니다.

**주요 기능:**
- 고속 배치 추론
- 효율적인 메모리 관리
- 다양한 모델 아키텍처 지원

**참고 자료:**
- [vLLM GitHub Repository](https://github.com/vllm-project/vllm)
- [vLLM 문서](https://docs.vllm.ai/)

## 📊 성능

### 파이프라인 처리 속도

| 파이프라인 | 처리 속도 | 지원 형식 |
|-----------|----------|----------|
| 텍스트 | 1000+ docs/sec | TXT, JSON, CSV |
| 이미지 | 100+ images/sec | JPG, PNG, PDF |
| 오디오 | 50+ files/sec | WAV, MP3, FLAC |

## 🛠️ 개발 가이드

### 요구사항

- Python 3.8 이상
- CUDA 11.0 이상 (GPU 사용 시)
- 충분한 메모리 (최소 16GB 권장)

### 개발 환경 설정

```bash
# 저장소 클론
git clone <repository_url>
cd nextits_data

# 가상환경 생성
python -m venv venv
source venv/bin/activate  # Linux/Mac
# venv\Scripts\activate  # Windows

# 의존성 설치
pip install -r requirements.txt
```

### 테스트

```bash
# 단위 테스트 실행
pytest tests/

# 통합 테스트 실행
pytest tests/integration/
```

## 📝 라이선스

이 프로젝트는 Apache 2.0 라이선스 하에 배포됩니다. 자세한 내용은 [LICENSE](../LICENSE) 파일을 참조하세요.

## 🙏 감사의 말

이 프로젝트는 다음 오픈소스 프로젝트들의 도움을 받았습니다:

- **[UVDoc](https://github.com/tanguymagne/UVDoc)**: 문서 왜곡 보정 기능
- **[vLLM](https://github.com/vllm-project/vllm)**: 고성능 추론 엔진

## 📧 문의

프로젝트에 대한 문의사항이나 제안사항이 있으시면 이슈를 등록해주세요.

## 🌟 기여

기여를 환영합니다! Pull Request를 보내주시거나 이슈를 등록해주세요.

---

<div align="center">
Made with ❤️ by Nextits Team
</div>
