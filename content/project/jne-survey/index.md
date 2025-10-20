---
title: "전남교육청 설문 시스템"
date: 2024-11-30
summary: "교육청 설문·집계·배포를 위한 Django 기반 웹 서비스"
featured:
  image: "uploads/slider1.jpg"   # 대표 이미지
tags: ["Django","Docker","GitHub Actions","Deploy"]
---

## 개요
전남교육청 설문 업무를 웹 기반으로 전환하기 위해 **Django**로 설문 작성/배포/집계 기능을 구현했습니다.

## 역할
- 설계/백엔드 전담, 배포 자동화(CI/CD) 구성  
- 관리자/응답자 권한 분리, 통계 대시보드

## 기술 스택
- **Backend:** Django, DRF  
- **DB:** PostgreSQL  
- **Infra:** Docker, Nginx, GitHub Actions

## 주요 기능
- 설문 템플릿, 만료/중복 방지, CSV 내보내기  
- 관리자 대시보드(응답 통계, 필터링)

## 성과
- 배포 자동화로 핫픽스 평균 배포시간 **10분 → 2분** 단축  
- 실제 운영(2024.08–11) 동안 무중단 서비스

## 링크
- (선택) 시연 영상 / 저장소 / 문서 링크
