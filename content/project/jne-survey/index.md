---
title: "전남교육청 설문조사 홈페이지 구현 및 운영"
date: 2024-08-01
summary: "전라남도교육청 의뢰 프로젝트로, 학교 민주주의 설문조사 시스템 구축 및 통계·관리 기능을 포함한 Django 기반 웹 서비스"
featured:
  image: "uploads/jne/featured.jpg"
  alt: "전남교육청 설문조사 메인 화면"
tags: ["Django","MySQL","Nginx","Ubuntu","Fullstack"]
links:
  - name: GitHub
    url: "https://github.com/Ddaaan/EduWebCode"
    icon: github
    icon_pack: fab
  - name: 배운점
    url: "https://www.notion.so/12184dccb3788007a936ed1918ffab09?pvs=21"
    icon: book
    icon_pack: fas
---

## 🔗 LINK
[http://jndedu-school-democracy.kr/](http://jndedu-school-democracy.kr/)  
*(현재 호스팅 종료)*

{{< figure src="static/project/jne-survey/traffic.png" alt="트레픽통계" >}}

---

## 📋 프로젝트 설명

### 👩‍🏫 학생, 학부모, 교직원
- 학교 민주주의 관련 이론 자료 제공  
- 사용자 유형(학생 / 학부모 / 교직원)에 따른 설문조사 참여  
- 공지사항 및 자료실 게시글 열람  
- 게시글 내 첨부파일 다운로드 기능 지원  

### 🧑‍💻 관리자 (학교별 / 지역청별 / 본청)
- 관리자 로그인 및 비밀번호 변경  
- 공지사항·자료실 게시글 작성 및 첨부파일 업로드  
- 학교별, 지역별, 학교급별 통계 조회  
- 문항별·파트별 통계 시각화 및 다운로드 기능  

{{< figure src="static/project/jne-survey/main.png" alt="메인화면" >}}
{{< figure src="static/project/jne-survey/webpage.png" alt="설문조사 참여 화면" >}}

---

## 💬 프로젝트 개요
> 전라남도교육청의 외주 프로젝트로,  
> 교육청 산하 학교들의 민주주의 설문조사를 통합적으로 운영할 수 있는 플랫폼을 개발하였습니다.

---

## ⚙️ TECH STACK
- **Language**: Python 3.11.9  
- **Framework**: Django  
- **Database**: MySQL  
- **Server**: Ubuntu + Nginx  
- **Deployment**: Gunicorn, crontab 기반 자동 리부트  

---

## 🧠 배운점
운영 과정에서의 **서버 트래픽 관리**, **Django ORM 최적화**,  
**DB 쿼리 캐싱**과 같은 백엔드 성능 튜닝을 실무 수준에서 경험할 수 있었습니다.  
👉 [사이트 운영 중 배운점 보기](https://www.notion.so/12184dccb3788007a936ed1918ffab09?pvs=21)

---

## 📁 GitHub Repository
🔗 [https://github.com/Ddaaan/EduWebCode](https://github.com/Ddaaan/EduWebCode)
