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

## 프로젝트 설명
- 시각장애인을 위한 **캔 음료 구별 앱**
- **YOLOv5**를 이용한 실시간 **캔 인식**
- 인식된 캔의 이름을 **TTS(Text-to-Speech)** 로 음성 안내

{{< figure src="uploads/cancheck/featured.jpg" alt="앱 실행 화면" >}}

---

## 프로젝트 진행
- 크롤링을 통한 학습 데이터 수집  
- **Roboflow**를 이용한 데이터 라벨링 및 데이터셋 구축  
- **Google Colab** 환경에서 YOLOv5 모델 학습  
- **TTS 구현**으로 인식된 캔 이름 음성 출력  

---

## Tech Skills
- **Language**: Java, Python  
- **Tools**: Android Studio, Google Colab, Roboflow  
- **Model**: YOLOv5 (Object Detection), Google TTS API  

---

## 프로젝트 특징
1. 모바일 기기에서 실시간 객체 탐지 수행  
2. 모델 최적화로 경량화 및 빠른 추론  
3. 인식된 객체 이름을 음성으로 안내하여 시각적 불편 해소  

---

## GitHub Repository
🔗 [https://github.com/Ddaaan/CanCheck](https://github.com/Ddaaan/CanCheck)
