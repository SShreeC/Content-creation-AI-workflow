# ✨ AI-Powered Content Repurposing Workflow (n8n + Gemini)

This project automates the process of **transforming a single content input** (like a blog post or summary) into multiple content formats for **different platforms**, using AI. Built using [n8n](https://n8n.io) and **Google Gemini**, it helps creators, marketers, and teams quickly scale their content production.

---

## 🎯 Goal

Transform a **single content input** into a full content kit:
- 📸 Instagram Caption + Reels Idea
- 🧵 Twitter Thread
- 📧 Email Newsletter
- 💼 LinkedIn Post
- 📌 Key Takeaways
- 🧠 Hashtags + Image Idea
- 📊 Store everything in Google Sheets for easy access

---

## 🧩 Workflow Architecture

| Step | Node | Description |
|------|------|-------------|
| 🔘 1 | On Form Submission | Accepts input: topic/title + optional long form content |
| 🔀 2 | Split Out | Splits input for parallel processing |
| 🧠 3 | Google Gemini Chat (x6) | Generates content for various platforms (Instagram, Twitter, LinkedIn, Newsletter, Hashtags, Takeaways) |
| 🔗 4 | Merge | Recombines all generated content |
| 📤 5 | Information Extractor | Structures the output |
| 📊 6 | Google Sheets | Appends the result into a spreadsheet for reuse |

---

## 📝 Form Inputs

Users must fill:
- **Title/Topic** (e.g., "Benefits of Remote Work")
- **Optional long-form content** (e.g., blog snippet or key points)

---

## 🤖 AI Agents (Google Gemini)

| Node | Role |
|------|------|
| `Instagram Caption` | Generates engaging captions for Instagram posts |
| `Instagram Reels` | Suggests reel script ideas or hooks |
| `Twitter Thread` | Breaks down the content into an X-thread format |
| `LinkedIn Post` | Formats content professionally for LinkedIn |
| `Email Newsletter` | Creates a short and valuable newsletter format |
| `Content Key Points` | Extracts and summarizes important takeaways |
| `Image & Hashtag Ideas` | Suggests visuals and hashtags for social reach |

---

## 📄 Sample Prompt Template (Used in Gemini Nodes)

> "You are a content strategist. Based on the input below, generate a [format] suitable for [platform]. Keep the tone [professional/friendly/fun].  
>
> **Topic:** {{topic}}  
> **Details:** {{content}}"

Each node adjusts the prompt based on its target platform and tone.

---

## 🧠 Information Structuring

After AI generation, all content is:
- Combined via a **Merge node**
- Structured using a **Data Extractor**
- Stored into **Google Sheets** with fields like:
  - Topic/Title
  - Instagram Caption
  - Reels Hook
  - Twitter Thread
  - LinkedIn Post
  - Newsletter Draft
  - Key Takeaways
  - Suggested Hashtags
  - Image Prompt

---

## 🔁 Sample Output (from Sheet)

| Topic | Instagram Caption | Twitter Thread | LinkedIn Post | ... |
|-------|-------------------|----------------|---------------|-----|
| Benefits of Remote Work | "💼 Work from anywhere..." | "1. Flexibility is power..." | "Remote work is here to stay..." | ... |

---

## 📥 How to Use

1. 🔧 Open your **n8n workflow**
2. 🧩 Connect Google Gemini API and Google Sheets
3. 🌐 Embed a form or trigger this via external app
4. 🚀 Click "Execute Workflow"
5. ✅ Watch content generate and auto-save

---

## 🌟 Use Cases

- 🚀 Content marketing automation
- 📅 Social media planning
- 💡 Idea repurposing from long blogs/podcasts
- 📩 Newsletter creation
- 🧵 X/Twitter thread generation

---

## 💡 Optional Improvements

- 🎯 Add content categorization or tone options
- 📁 Export as PDFs for teams/clients
- 🕒 Schedule posts via social media API integrations
- 🔁 Loop to create variations (A/B testing style)



