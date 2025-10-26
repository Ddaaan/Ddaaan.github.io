---
title: "Development and Operation of Jeonnam Office of Education Survey Website"
date: 2024-08-01
summary: "A Django-based web platform commissioned by the Jeollanam-do Office of Education, enabling integrated management of school democracy surveys with statistical and administrative functions."
featured:
  image: "uploads/jne-survey/featured.jpg"
  alt: "Main Page of Jeonnam Education Survey Website"
tags: ["Django", "MySQL", "Nginx", "Ubuntu", "Fullstack"]
links:
  - name: GitHub
    url: "https://github.com/Ddaaan/EduWebCode"
    icon: github
    icon_pack: fab
  - name: Learnings
    url: "https://www.notion.so/12184dccb3788007a936ed1918ffab09?pvs=21"
    icon: book
    icon_pack: fas
---

## 💡 Project Overview
This project was commissioned by the **Jeollanam-do Office of Education**, aimed at creating an integrated platform for conducting and managing democracy-related surveys across schools.  
The platform was developed and operated using Django as the backend framework.

**Service Link**: [http://jndedu-school-democracy.kr/](http://jndedu-school-democracy.kr/) (Hosting terminated)

{{< figure src="static/project/jne-survey/traffic.png" alt="Traffic Statistics" >}}

---

## 🌟 Key Features
### 👩‍🏫 Users (Students, Parents, Faculty)
- Participate in customized surveys according to user type (student, parent, or faculty)  
- Access announcements and download attachments from the resources section  
- View educational resources related to school democracy  

### 🧑‍💻 Administrators (School / Regional Office / Main Office)
- Role-based admin accounts with tiered access (school, regional office, headquarters)  
- Create and manage announcements or resources with file uploads  
- Real-time statistics by school, region, and education level  
- Visualize and export statistics by question or category  

---

## ⚙️ Tech Stack
- **Language**: Python 3.11.9  
- **Framework**: Django  
- **Database**: MySQL  
- **Server**: Ubuntu + Nginx  
- **Deployment**: Gunicorn, crontab (automatic reboot scheduling)

---

## 🧠 Key Learnings
- **High-Traffic Management**: Gained hands-on experience handling sudden traffic spikes in a live environment by optimizing Nginx and Gunicorn configurations.  
- **Database Optimization**: Solved Django ORM N+1 query problems using `select_related` and `prefetch_related`, and minimized DB load for complex queries with `annotate` and `aggregate`.  
- **Server Operations**: Learned to maintain stable Ubuntu-based servers using scheduled crontab tasks for automatic reboots and monitoring.

> 👉 [Detailed Learnings on Site Operation](https://www.notion.so/12184dccb3788007a936ed1918ffab09?pvs=21)

---

## 🔗 GitHub Repository
[https://github.com/Ddaaan/EduWebCode](https://github.com/Ddaaan/EduWebCode)
