---
title: "통합 데이터 기반 분석/리포트 생성 시스템"
date: 2025-01-01
summary: "사용자 업로드 데이터 기반 검색·전처리·미리보기·챗봇·한글 보고서 자동 생성까지 제공하는 End-to-End 데이터 분석 서비스"
featured:
  image: "uploads/capston/featured.jpg"
  alt: "Capston Project"
tags: ["Web","Streamlit","Flask","Rag","Docker"]
links:
  - name: GitHub
    url: "https://github.com/Ddaaan/capston"
    icon: github
    icon_pack: fab
  - name: Docker 가이드
    url: "https://www.notion.so/Docker-Trouble-Shooting-1d284dccb3788007bf86c6856df9e8e6"
    icon: docker
    icon_pack: fab
---

## 💡 프로젝트 개요
사용자가 데이터를 업로드하면, 이를 기반으로 **검색, 자동 전처리, 미리보기, RAG 챗봇 질의응답, 한글 보고서 자동 생성**까지 End-to-End로 제공하는 데이터 분석 서비스입니다. Streamlit과 Flask를 연동하여 사용자 친화적인 UI와 강력한 백엔드 분석 기능을 동시에 구현했습니다.


---

## 🌟 주요 기능
- **데이터 검색**: 통합 데이터 DB를 기반으로 빠른 데이터 검색을 지원합니다.
- **업로드 및 분석**: 사용자가 직접 데이터를 업로드하고 분석을 요청할 수 있습니다.
- **자동 전처리 및 미리보기**: 업로드된 데이터의 결측치, 타입을 자동 전처리하며 Schema와 샘플 데이터를 미리 볼 수 있습니다.
- **RAG 기반 챗봇**: 사용자가 선택한 파일을 컨텍스트로 하여 챗봇에게 자연어 질의응답이 가능합니다.
- **한글 보고서 자동 생성**: LLM의 응답을 요약하여 체계적인 한글 보고서로 자동 생성 및 다운로드를 제공합니다.

---

## ⚙️ 기술 스택
- **Language**: Python
- **Framework**: Streamlit, Flask
- **Server/Infra**: Docker
- **Models**: KURE-v1 (Embedding), Qwen3 (LLM)

---

## 🚀 프로젝트 특징
- **RAG 아키텍처**: 파일 업로드 시 S3 저장, 메타 파싱, 전처리, 임베딩 인덱싱(KURE-v1)을 거쳐 벡터 검색에 활용합니다.
- **LLM 연동**: 생성된 컨텍스트를 Qwen3 모델에 전달하여 답변/요약을 생성하고, 이를 보고서 템플릿으로 렌더링합니다.
- **Docker 기반 배포**: Docker를 통해 로컬과 서버 환경을 동일하게 구성하여 배포 용이성을 높였습니다.
- **상세 트러블슈팅 문서화**: Docker 환경 설정 및 운영 중 발생한 문제 해결 과정을 별도 문서로 기록했습니다.
  > 🔧 [Docker 환경 설정 / Trouble Shooting](https://www.notion.so/Docker-Trouble-Shooting-1d284dccb3788007bf86c6856df9e8e6)

---

## 🔗 GitHub Repository
[https://github.com/Ddaaan/capston](https://github.com/Ddaaan/capston)