# 🚀 AI YouTube Shorts Automation with n8n, Gemini AI, Google Drive & YouTube API

![n8n](https://img.shields.io/badge/n8n-Automation-orange)
![Gemini AI](https://img.shields.io/badge/Gemini-AI-blue)
![YouTube](https://img.shields.io/badge/YouTube-Shorts-red)
![Docker](https://img.shields.io/badge/Docker-Containerized-blue)
![Google Drive](https://img.shields.io/badge/Google%20Drive-Storage-green)
![License](https://img.shields.io/badge/License-MIT-yellow)

An end-to-end AI-powered YouTube Shorts automation workflow built with **n8n**, **Google Gemini AI**, **Google Drive**, **Google Sheets**, **Docker**, and **YouTube Data API v3**.

This workflow automatically fetches scheduled videos from Google Drive, generates AI-powered captions and hashtags using Gemini AI, uploads videos to YouTube Shorts, updates publishing status in Google Sheets, and archives uploaded videos — all without manual intervention.

Built and tested on a **Dockerized local n8n environment**.

---

# 📸 Workflow Preview

> Add your workflow screenshot below

![Workflow](screenshots/workflow.png)

---

# 🌟 Features

✅ Fully Automated YouTube Shorts Publishing

✅ Google Sheets Based Content Calendar

✅ Google Drive Video Storage

✅ AI Caption Generation using Gemini AI

✅ AI Hashtag Generation

✅ Automatic YouTube Upload

✅ Content Scheduling

✅ Status Tracking in Google Sheets

✅ Automatic File Archiving

✅ Docker-Based Deployment

✅ No-Code / Low-Code Workflow

✅ OAuth 2.0 Authentication

✅ Scalable Content Publishing Pipeline

---

# 🎯 Why This Project?

Managing multiple YouTube Shorts manually becomes time-consuming.

This workflow automates the entire publishing pipeline:

- Schedule videos in Google Sheets
- Store videos in Google Drive
- Generate captions using AI
- Upload automatically to YouTube
- Track upload status
- Archive uploaded content

Perfect for:

- Content Creators
- Faceless YouTube Channels
- AI Content Channels
- Social Media Agencies
- Marketing Teams
- Automation Enthusiasts
- Creator Economy Startups

---

# 🏗 Workflow Architecture

```text
Schedule Trigger
        │
        ▼
Google Sheets
(Read Scheduled Content)
        │
        ▼
Check Upload Status
        │
        ▼
Validate Schedule Time
        │
        ▼
Google Drive Search
        │
        ▼
Download Video
        │
        ▼
Gemini AI
(Caption + Hashtags)
        │
        ▼
YouTube Upload
        │
        ▼
Update Google Sheet
        │
        ▼
Archive Uploaded Video
```

---

# ⚙️ Workflow Overview

The workflow follows these steps:

### Step 1

The Schedule Trigger starts automatically at predefined intervals.

### Step 2

Google Sheets is checked for scheduled videos.

### Step 3

The workflow verifies:

- Video is not already uploaded
- Scheduled time matches current time

### Step 4

The video file is searched inside Google Drive.

### Step 5

The video is downloaded from Google Drive.

### Step 6

Gemini AI generates:

- Caption
- Hashtags

based on the content outline.

### Step 7

The video is uploaded to YouTube Shorts automatically.

### Step 8

Google Sheets status is updated.

### Step 9

The uploaded file is moved to an archive folder.

---

# 🛠 Tech Stack

| Technology | Purpose |
|------------|----------|
| n8n | Workflow Automation |
| Docker | Local Deployment |
| Google Drive API | Video Storage |
| Google Sheets API | Content Scheduling |
| YouTube Data API v3 | Video Publishing |
| Google Gemini AI | AI Caption Generation |
| OAuth 2.0 | Authentication |
| Google Cloud Platform | API Management |

---

# 📂 Repository Structure

```text
ai-youtube-shorts-automation-n8n-gemini-google-drive
│
├── README.md
├── LICENSE
├── Drive to youtube upload automation.json
│
├── screenshots
│   └── workflow.png
│
└── docs
    └── architecture.png
```

---

# 🔐 Required Credentials

This workflow requires the following credentials.

## Google Drive OAuth2

Used For:

- Search Video
- Download Video
- Move Uploaded File

Required Scope:

```text
https://www.googleapis.com/auth/drive
```

---

## Google Sheets OAuth2

Used For:

- Read Scheduled Content
- Update Upload Status

Required Scope:

```text
https://www.googleapis.com/auth/spreadsheets
```

---

## YouTube OAuth2

Used For:

- Upload YouTube Shorts

Required Scopes:

```text
https://www.googleapis.com/auth/youtube
https://www.googleapis.com/auth/youtube.upload
```

---

## Gemini API

Used For:

- Caption Generation
- Hashtag Generation

Get API Key:

https://aistudio.google.com/

---

# ☁️ Google Cloud Setup

## Create Project

Go to:

https://console.cloud.google.com/

Create a new Google Cloud Project.

---

## Enable APIs

Enable:

- Google Drive API
- Google Sheets API
- YouTube Data API v3

---

## Configure OAuth Consent Screen

1. Open OAuth Consent Screen
2. Select External
3. Add App Information
4. Add Yourself as Test User

---

## Create OAuth Credentials

Create:

```text
OAuth Client ID
```

Application Type:

```text
Web Application
```

Authorized Redirect URI:

```text
http://localhost:5678/rest/oauth2-credential/callback
```

---

# 📊 Google Sheet Structure

Create a sheet with the following columns:

| File Name | Outline | Schedule Time | Status |
|------------|----------|---------------|---------|
| video1.mp4 | Funny Story | 2026-06-10 09:00 | Pending |
| video2.mp4 | Motivation | 2026-06-10 18:00 | Pending |

---

# 📁 Google Drive Structure

```text
Google Drive
│
├── Scheduled Videos
│   ├── video1.mp4
│   ├── video2.mp4
│   └── video3.mp4
│
└── Uploaded Videos
    ├── video1.mp4
    ├── video2.mp4
    └── video3.mp4
```

---

# 🐳 Running n8n Locally with Docker

This project was developed and tested on a local Docker-based n8n setup.

## Pull n8n Docker Image

```bash
docker pull n8nio/n8n
```

---

## Run n8n Container

```bash
docker run -it --rm \
-p 5678:5678 \
-v ~/.n8n:/home/node/.n8n \
n8nio/n8n
```

---

## Open n8n

```text
http://localhost:5678
```

---

# 📥 Installation

## Clone Repository

```bash
git clone https://github.com/yourusername/ai-youtube-shorts-automation-n8n-gemini-google-drive.git
```

---

## Import Workflow

Import:

```text
Drive to youtube upload automation.json
```

into your n8n instance.

---

## Configure Credentials

Create the following credentials inside n8n:

- Google Drive OAuth2
- Google Sheets OAuth2
- YouTube OAuth2
- Gemini API

---

## Update Resource IDs

Replace the following with your own values:

- Google Sheet ID
- Source Google Drive Folder ID
- Archive Google Drive Folder ID

---

## Activate Workflow

Turn workflow status to:

```text
Active
```

The workflow will now run automatically based on the configured schedule.

---

# 💼 Resume / Portfolio Highlights

- Designed and developed an AI-powered content publishing automation pipeline.
- Integrated Google Drive, Google Sheets, Gemini AI, and YouTube APIs.
- Implemented OAuth 2.0 authentication across multiple Google services.
- Automated video scheduling, caption generation, uploading, and tracking.
- Built and tested in a Dockerized local n8n environment.
- Reduced manual content publishing effort by more than 90%.

---

# 🚀 Future Improvements

- Instagram Reels Publishing
- Facebook Reels Publishing
- LinkedIn Video Publishing
- TikTok Automation
- AI Thumbnail Generation
- AI Title Generation
- Telegram Notifications
- Slack Notifications
- Analytics Dashboard
- Multi-Channel Support
- Multi-Language Captions
- SEO Score Optimization

---

# 🔍 Keywords

AI Automation, YouTube Shorts Automation, n8n Workflow, Gemini AI, Google Drive Automation, Google Sheets Automation, YouTube API, Content Automation, Social Media Automation, Creator Tools, AI Content Pipeline, Docker Automation, No-Code Automation, Low-Code Workflow, Automated Video Publishing.

---

# 📈 Use Cases

- Content Creators
- YouTube Shorts Channels
- Faceless YouTube Automation
- AI Generated Content
- Social Media Agencies
- Marketing Teams
- Startup Growth Teams
- Creator Economy Businesses

---

# 👨‍💻 Author

### Abdul Shamshuddin Sheikh

B.Tech Computer Science (Artificial Intelligence)

Vishwakarma Institute of Technology (VIT), Pune

LinkedIn: Add Your LinkedIn Profile

GitHub: Add Your GitHub Profile

---

# ⭐ Support

If you found this project useful:

⭐ Star this repository

🍴 Fork this repository

📢 Share it with other automation enthusiasts

Contributions, suggestions, and improvements are always welcome.

---

# 📜 License

This project is licensed under the MIT License.

Feel free to use, modify, and distribute this project.
