---
title: "시각장애인을 위한 캔 음료 구별 앱 (CanCheck)"
date: 2024-06-01
summary: "Yolov5와 TTS를 활용한 시각장애인용 캔 음료 구별 보조 애플리케이션"
featured:
  image: "uploads/cancheck/featured.jpg"
  alt: "CanCheck App"
tags: ["Android","YOLOv5","TTS","Computer Vision"]
links:
  - name: GitHub
    url: "https://github.com/Ddaaan/CanCheck"
    icon: github
    icon_pack: fab
---

## 💡 프로젝트 개요
시각장애인 사용자가 음료수 캔을 구별하는 데 겪는 어려움을 해결하기 위해 개발한 안드로이드 애플리케이션입니다. 스마트폰 카메라를 통해 실시간으로 캔을 인식하고, 객체 탐지 모델(YOLOv5)을 활용해 캔의 종류를 식별한 뒤, 그 결과를 TTS(Text-to-Speech) 음성으로 사용자에게 안내합니다.

---

## 🌟 주요 기능 및 특징
- **실시간 객체 탐지**: YOLOv5 모델을 모바일 환경에 최적화하여 실시간으로 캔 음료를 탐지합니다.
- **음성 안내 (TTS)**: 탐지된 캔의 이름을 즉시 음성으로 출력하여 시각적 정보 없이도 내용을 알 수 있습니다.
- **데이터셋 구축**: 원활한 학습을 위해 크롤링으로 데이터를 수집하고, Roboflow를 사용해 직접 라벨링 및 데이터셋을 구축했습니다.
- **모델 학습**: Google Colab 환경에서 YOLOv5 모델을 학습시키고 경량화하여 앱에 탑재했습니다.

---

## ⚙️ 기술 스택
- **Language**: Java, Python
- **Tools**: Android Studio, Google Colab, Roboflow
- **Model**: YOLOv5 (Object Detection), Google TTS API

---

## 🔗 GitHub Repository
[https://github.com/Ddaaan/CanCheck](https://github.com/Ddaaan/CanCheck)