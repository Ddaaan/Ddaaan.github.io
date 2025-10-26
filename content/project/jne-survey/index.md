---
title: "전남교육청 설문조사 홈페이지 구현 및 운영"
date: 2024-08-01
summary: "전라남도교육청 의뢰 프로젝트로, 학교 민주주의 설문조사 시스템 구축 및 통계·관리 기능을 포함한 Django 기반 웹 서비스"
featured:
  image: "uploads/jne-survey/featured.jpg"
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

## 💡 프로젝트 개요
전라남도교육청의 외주 프로젝트로, 교육청 산하 학교들의 민주주의 설문조사를 통합적으로 운영할 수 있는 플랫폼을 Django 기반으로 개발 및 운영하였습니다. 

**운영 링크**: [http://jndedu-school-democracy.kr/](http://jndedu-school-democracy.kr/) (현재 호스팅 종료)

{{< figure src="static/project/jne-survey/traffic.png" alt="트레픽통계" >}}

---

## 🌟 주요 기능
### 👩‍🏫 사용자 (학생, 학부모, 교직원)
- 사용자 유형(학생/학부모/교직원)에 따른 맞춤형 설문조사 참여
- 공지사항 및 자료실 게시글 열람 및 첨부파일 다운로드
- 학교 민주주의 관련 이론 자료 제공

### 🧑‍💻 관리자 (학교/지역청/본청)
- 등급별 관리자(학교, 지역청, 본청) 로그인 및 권한 관리
- 공지사항·자료실 게시글 작성 및 첨부파일 업로드
- 학교별, 지역별, 학교급별 통계 실시간 조회
- 문항별·파트별 통계 시각화 및 데이터 다운로드 기능

{{< figure src="static/project/jne-survey/main.png" alt="메인화면" >}}
{{< figure src="static/project/jne-survey/webpage.png" alt="설문조사 참여 화면" >}}

---

## ⚙️ 기술 스택
- **Language**: Python 3.11.9
- **Framework**: Django
- **Database**: MySQL
- **Server**: Ubuntu + Nginx
- **Deployment**: Gunicorn, crontab (자동 리부트)

---

## 🧠 배운점
- **대규모 트래픽 관리**: 실제 운영 환경에서 순간적으로 몰리는 트래픽을 Nginx와 Gunicorn 설정으로 분산 처리하고 대응한 경험을 쌓았습니다.
- **DB 성능 최적화**: Django ORM 사용 시 발생하는 N+1 문제를 `select_related`, `prefetch_related`로 해결하고, 복잡한 통계 쿼리는 `annotate`와 `aggregate`를 활용해 DB 부하를 최소화했습니다.
- **서버 운영**: crontab을 이용한 주기적인 서버 자동 리부트 설정 등 안정적인 리눅스(Ubuntu) 서버 운영 노하우를 익혔습니다.

> 👉 [사이트 운영 중 배운점 상세 보기](https://www.notion.so/12184dccb3788007a936ed1918ffab09?pvs=21)

---

## 🔗 GitHub Repository
[https://github.com/Ddaaan/EduWebCode](https://github.com/Ddaaan/EduWebCode)