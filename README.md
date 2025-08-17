# 🤖 LinkedIn Agent – AI-Powered Personal Branding

This project automates the creation and publishing of **unique LinkedIn posts** for **Sarthak Singh (Co-founder of IntrinsAi.com, NVIDIA Inception + AWS for Founders)**.

It uses **n8n** + **OpenAI** + **Google Live Search** to:
- Fetch the **latest tech news & facts** dynamically  
- Generate **professional, engaging posts** tailored to my voice  
- Publish them directly to LinkedIn  
- Log each post to Google Sheets + send confirmation email  

---

## 🚀 Features  
- ✅ Daily automated posting at **10:00 AM IST**  
- ✅ Pulls **latest AI/Tech 2025 news** via Google Search API  
- ✅ Generates **unique LinkedIn posts** using OpenAI  
- ✅ Automatically publishes to **LinkedIn**  
- ✅ Logs posts into **Google Sheets**  
- ✅ Sends a **confirmation email** when published  

---

## ⚙️ Workflow Highlights  
- **Trigger**: Runs daily at `10:00 AM IST`  
- **Google Live Search**: Fetches latest AI/Tech news  
- **OpenAI Chat**: Generates insightful LinkedIn posts  
- **LinkedIn API**: Publishes content automatically  
- **Google Sheets**: Logs post history  
- **Gmail API**: Sends success email  

---

## 📝 Prompt Setup  

### 🔧 System Message  
```
You are creating LinkedIn content for Sarthak Singh, BTech student and co-founder of IntrinsAi.com — a startup building AI solutions (part of NVIDIA Inception + AWS for Founders).

Tone: Professional yet approachable. Posts should mix **tech insights + factual commentary + news updates** with a forward-looking perspective. Keep them crisp, thought-provoking, and engaging.

Goals:
- Position Sarthak as a young innovator who shares value-packed updates about AI, cloud, automation, and new technologies.
- Blend industry news with unique insights — not just reposts.
- Add context: why the news/fact matters for businesses, students, or startups.
- Make each post original, no repetition of past topics.

Critical:
- Always tie the news/fact back to a broader theme (innovation, entrepreneurship, AI adoption).
- Avoid sounding like a journalist; instead, provide personal perspective or prediction.
- Use clear, engaging storytelling — no jargon dumps.
```

### 🔧 User Message Prompt  
```
Write a LinkedIn post for Sarthak Singh about a recent tech trend, fact, or news update.

Latest trend/news: {{ $('Google Live Search').item.json.items ? $('Google Live Search').item.json.items.slice(0,2).map(r => r.title).join(', ') : 'AI in 2025 – automation, cloud, and innovation' }}

The post should:
1. Highlight the fact/news in simple terms.
2. Add context on why it matters.
3. Share a short perspective, lesson, or prediction.

Tone: professional + insightful, but easy to read. Keep it unique, engaging, and vision-driven.
```

---

## 📂 Repo Structure  
```
├── workflow-template.json   # sanitized version with placeholders
├── README.md                # project overview + setup guide
└── /docs                    # screenshots, sample outputs
```

---

## 🔧 Setup Guide  
1. Clone the repo  
2. Import `workflow-template.json` into your **n8n** instance  
3. Replace placeholders with your own credentials:  
   - `<YOUR_GOOGLE_API_KEY>`  
   - `<YOUR_GOOGLE_CX_ID>`  
   - `<YOUR_LINKEDIN_PERSON_ID>`  
   - `<YOUR_GOOGLE_SHEET_URL>`  
   - `<YOUR_EMAIL>`  
4. Activate the workflow  

---

## 📝 Example Generated Post (sample)  
> “AI in cloud computing is no longer just about scale — it’s about intelligence. At IntrinsAi, we’ve seen how NVIDIA Inception + AWS for Founders helped us move faster from idea → execution.  
>
> Being a student-founder, every constraint feels like an advantage — you’re forced to innovate smarter. That’s the real beauty of building in 2025.”  

---

## 🌟 Why This Project  
- Demonstrates **real-world n8n automation** with multiple integrations  
- Showcases **AI + automation for personal branding**  
- Unique angle: *student + founder scaling AI startup + personal brand*  

---

## 📜 License  
This project is open-source. You can use and modify the template workflow with your own credentials.  

---
