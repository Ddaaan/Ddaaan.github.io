---
title: "통합 데이터 기반 분석/리포트 생성 시스템"
date: 2025-01-01
summary: "사용자 업로드 데이터 기반 검색·전처리·미리보기·챗봇·한글 보고서 자동 생성까지 제공하는 End-to-End 데이터 분석 서비스"
featured:
  image: "uploads/capston/featured.jpg"   # 대표 이미지 (아래 안내대로 파일만 두면 됨)
  alt: "Capston Project"
tags: ["Web","Streamlit","Flask","Rag","Docker"]
# 페이지 상단에 액션 버튼들
links:
  - name: GitHub
    url: "https://github.com/Ddaaan/capston"
    icon: github
    icon_pack: fab
  - name: Docker 가이드
    url: "https://www.notion.so/Docker-Trouble-Shooting-1d284dccb3788007bf86c6856df9e8e6?pvs=21"
    icon: docker
    icon_pack: fab
---

## 프로젝트 설명
- **통합 데이터 DB** 기반의 빠른 **데이터 검색**
- **사용자 데이터 업로드** 및 **분석** 지원
- 업로드 데이터의 **자동 전처리**
- **데이터 미리보기** 제공 (Schema/샘플 확인)
- 사용자가 선택한 파일을 바탕으로 **챗봇 질의응답**
- **LLM 응답을 요약**하여 **한글 보고서 자동 생성**

{{< figure src="uploads/capston/featured.jpg" alt="서비스 화면" >}}

---

## Tech Skills
- **Language**: Python  
- **Framework**: Streamlit, Flask  
- **Server/Infra**: Docker  
- **Models**: KURE-v1 (Embedding), Qwen3 (LLM)

---

## 아키텍처 개요
1. 파일 업로드 → S3/로컬 저장 + 메타 파싱  
2. 전처리 파이프라인(결측/타입 정리, 샘플링)  
3. 임베딩 인덱싱(KURE-v1) → **벡터 검색**  
4. 컨텍스트 생성 → **Qwen3**로 답변/요약 → 보고서 템플릿 렌더  
5. Streamlit UI로 미리보기/질의/리포트 다운로드 제공

---

## 실행 & 운영 메모
- **Docker** 기반으로 로컬/서버 동일 환경 구성
- CI/CD 연결 시 이미지 태깅 및 롤백 용이

> 상세 Trouble Shooting과 설치 방법은 아래 문서 참고  
> 🔧 [Docker 환경 설정 / Trouble Shooting](https://www.notion.so/Docker-Trouble-Shooting-1d284dccb3788007bf86c6856df9e8e6?pvs=21)

---

## 레포지토리
- GitHub: **https://github.com/Ddaaan/capston**

