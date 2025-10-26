---
title: "CanCheck: A Mobile App for Identifying Canned Drinks for the Visually Impaired"
date: 2024-06-01
summary: "An assistive Android application for visually impaired users that distinguishes canned beverages using YOLOv5 and TTS."
featured:
  image: "uploads/cancheck/featured.jpg"
  alt: "CanCheck App"
tags: ["Android", "YOLOv5", "TTS", "Computer Vision"]
links:
  - name: GitHub
    url: "https://github.com/Ddaaan/CanCheck"
    icon: github
    icon_pack: fab
---

## 💡 Project Overview
CanCheck is an Android application designed to help visually impaired users identify canned beverages.  
It uses the smartphone camera to detect cans in real-time through an object detection model (YOLOv5), then announces the detected label via TTS (Text-to-Speech) audio output.

---

## 🌟 Key Features
- **Real-time Object Detection**: Optimized the YOLOv5 model for mobile to detect canned beverages in real time.  
- **Voice Guidance (TTS)**: Announces the detected can name through speech output, allowing users to identify beverages without visual information.  
- **Dataset Creation**: Built a custom dataset by web crawling and manual labeling using Roboflow.  
- **Model Training**: Trained the YOLOv5 model on Google Colab, optimized and deployed it on the Android app.

---

## ⚙️ Tech Stack
- **Language**: Java, Python  
- **Tools**: Android Studio, Google Colab, Roboflow  
- **Model**: YOLOv5 (Object Detection), Google TTS API

---

## 🔗 GitHub Repository
[https://github.com/Ddaaan/CanCheck](https://github.com/Ddaaan/CanCheck)
