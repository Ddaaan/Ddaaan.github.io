---
title: "Integrated Data Analysis and Automated Report Generation System"
date: 2025-01-01
summary: "An end-to-end data analysis service providing data upload, search, preprocessing, preview, RAG chatbot interaction, and automatic Korean report generation."
featured:
  image: "uploads/capston/featured.jpg"
  alt: "Capston Project"
tags: ["Web", "Streamlit", "Flask", "RAG", "Docker"]
links:
  - name: GitHub
    url: "https://github.com/Ddaaan/capston"
    icon: github
    icon_pack: fab
  - name: Docker Guide
    url: "https://www.notion.so/Docker-Trouble-Shooting-1d284dccb3788007bf86c6856df9e8e6"
    icon: docker
    icon_pack: fab
---

## 💡 Project Overview
This system provides an **end-to-end data analysis service** that allows users to upload their data and perform **search, automatic preprocessing, preview, RAG-based chatbot Q&A, and automatic Korean report generation**.  
By integrating Streamlit and Flask, it delivers both a user-friendly interface and powerful backend analytical capabilities.

---

## 🌟 Key Features
- **Data Search**: Enables fast data retrieval using an integrated database.  
- **Upload and Analysis**: Users can upload and analyze their own datasets.  
- **Automatic Preprocessing & Preview**: Handles missing values and data type preprocessing automatically, with schema and sample data preview.  
- **RAG-based Chatbot**: Supports natural language Q&A using the user-selected file as the context.  
- **Automatic Korean Report Generation**: Summarizes LLM responses into a structured Korean report available for download.

---

## ⚙️ Tech Stack
- **Language**: Python  
- **Framework**: Streamlit, Flask  
- **Server/Infra**: Docker  
- **Models**: KURE-v1 (Embedding), Qwen3 (LLM)

---

## 🚀 Project Highlights
- **RAG Architecture**: Uploaded files are stored in S3, parsed, preprocessed, and embedded (via KURE-v1) for vector-based retrieval.  
- **LLM Integration**: Context generated from vector search is passed to the Qwen3 model for response summarization and rendered into a report template.  
- **Docker-based Deployment**: The project is containerized for seamless deployment across local and server environments.  
- **Comprehensive Troubleshooting Documentation**: Detailed notes on Docker setup and issue resolution were recorded.  
  > 🔧 [Docker Setup / Troubleshooting Guide](https://www.notion.so/Docker-Trouble-Shooting-1d284dccb3788007bf86c6856df9e8e6)

---

## 🔗 GitHub Repository
[https://github.com/Ddaaan/capston](https://github.com/Ddaaan/capston)
