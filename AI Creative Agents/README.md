# 🎬 Short-form Video Ads Agent

[![n8n](https://img.shields.io/badge/Built%20with-n8n-EA4B71?logo=n8n&logoColor=white)](https://n8n.io/)
[![OpenAI](https://img.shields.io/badge/Powered%20by-OpenAI-412991?logo=openai&logoColor=white)](https://openai.com/)
[![Kie.ai](https://img.shields.io/badge/Video%20Generation-Kie.ai-black)](https://kie.ai/)
[![Telegram](https://img.shields.io/badge/Interface-Telegram-26A5E4?logo=telegram&logoColor=white)](https://telegram.org/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

Automatically generate **cinematic 10-second video ads** from a single image using AI.

Send a photo to Telegram → AI generates a commercial → video is delivered back automatically.

---

## ✨ Features

- AI image analysis  
- Cinematic commercial prompt generation  
- Automated video generation (Sora-2 via Kie.ai)  
- Telegram bot interface  
- Fully automated n8n workflow  

---

## ⚙️ How It Works

1. Send photo to Telegram bot  
2. AI analyzes the image  
3. AI generates ad prompt  
4. Kie.ai generates video  
5. Video sent back to Telegram  

---

## 🎥 Example Results
Find the videos here:
https://drive.google.com/drive/folders/1f3zeR1PJJgN34wyd1Si5lZBxHrfcsrPN?usp=sharing

Example Shots:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/7442560d-e196-4f16-b80b-3c4fed319071" />

<img width="1920" height="1076" alt="image" src="https://github.com/user-attachments/assets/8225be06-7a14-42dd-8163-3795b333832a" />




---

## 💰 Cost

Kie.ai pricing for Sora 2 image-to-video stable:

- **$0.175 per 10-second video**
- **or 35 credits per video**

(OpenAI costs apply separately)

---

## 📦 Requirements

- n8n  
- OpenAI API key  
- Kie.ai API key  
- Telegram Bot  
- Google Drive  

---

## 🚀 Setup

1. Import workflow JSON into n8n  
2. Add required credentials  
3. Activate workflow  
4. Send image to Telegram bot  
