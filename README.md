# police-ai
# AI-Powered Police Case Management Web Application

---

## ✨ Project Description
A web application where police officers can:
- Login, Logout, Reset Password
- Upload case `.csv` files
- View, search, and filter cases (including natural language search)
- See case priority scores (AI + Logic-based)
- View AI-summarized case details
- Generate 3D visualizations (text-to-image AI)
- Download case details as PDFs
- Download summary and visualizations

---

## 🛠️ Tech Stack Overview

| Layer | Technology/Service | Free Tier? |
|:-----|:-------------------|:----------|
| Frontend | React.js + Tailwind CSS | ✅ |
| Backend | Node.js + Express.js | ✅ |
| Authentication | Firebase Authentication OR JWT | ✅ |
| Database | MongoDB Atlas (Free Tier 512MB) | ✅ |
| File Parsing | csv-parser (Node.js library) | ✅ |
| AI Summarization | Hugging Face `facebook/bart-large-cnn` | ✅ |
| AI Image Generation | Hugging Face `stable-diffusion-v1-5` | ✅ |
| Hosting Frontend | Vercel (Free Tier) | ✅ |
| Hosting Backend | Render.com (Free Tier) | ✅ |
| PDF Generation | pdf-lib or puppeteer | ✅ |
| Search | Elasticlunr.js / MongoDB Full-Text Search | ✅ |

---

## 🌐 Frontend Features (React.js)

- **Login / Logout / Forgot Password**
- **CSV Upload** (Drag and Drop)
- **Table View** (Paginated, Sortable)
- **Search and Filter**
  - Search by Name, Date, Location, etc.
  - Natural Language Search (AI Embedding based)
- **Case Detail Page**
  - AI-generated Summary
  - AI-generated Visualization
- **Download Options**
  - Download Case Report PDF
  - Download Summary and Visualization
- **Responsive Design** (Desktop & Mobile)

---

## ⚙️ Backend APIs (Node.js + Express.js)

| API Endpoint | Method | Description |
|:------------|:-------|:------------|
| `/api/auth/login` | POST | Login Police Officer |
| `/api/auth/logout` | POST | Logout Officer |
| `/api/auth/forgot-password` | POST | Send password reset email |
| `/api/cases/upload` | POST | Upload CSV and Parse Cases |
| `/api/cases` | GET | Get all cases |
| `/api/cases/:id` | GET | Get case by ID |
| `/api/cases/:id/summary` | GET | Get AI Summary for a case |
| `/api/cases/:id/visualization` | GET | Generate AI Visualization |
| `/api/cases/:id/download-pdf` | GET | Download Case Report as PDF |
| `/api/search` | POST | Search cases (text or natural language) |

---

## 🧠 AI Models Used

- **Summarization**
  - `facebook/bart-large-cnn` (Hugging Face)
- **Natural Language Search**
  - `sentence-transformers/all-MiniLM-L6-v2`
- **Image Generation**
  - `CompVis/stable-diffusion-v1-5` (Text-to-Image)

---

## 📂 Database (MongoDB Atlas)

**Collection:** `cases`

| Field | Type | Description |
|:-----|:----|:------------|
| `_id` | ObjectId | Unique ID |
| `caseId` | Number | Case Unique ID |
| `name` | String | Victim's Name |
| `age` | Number | Age |
| `gender` | String | Gender |
| `race` | String | Race |
| `dateOfInjury` | Date | Date of Incident |
| `locationOfInjury` | String | Address of Incident |
| `latitude` | Number | Latitude |
| `longitude` | Number | Longitude |
| `agencyInvolved` | String | Police Agency |
| `forceUsed` | String | Level of Force |
| `description` | String | Brief Description |
| `disposition` | String | Case Status |
| `useOfForceType` | String | Intended Force Type |
| `summary` | String | AI Generated Summary |
| `visualizationImage` | String (URL) | AI Generated Visualization Image URL |

---

## 🔒 Authentication Flow

- Login using Email/Password (Firebase / JWT)
- Store access tokens in HTTP-only cookies
- Use token-based authentication for protected APIs
- Forgot password sends reset link via Firebase Auth / custom emailer

---

## 🔥 Deployment Plan

- **Frontend (React App)** → Deploy to Vercel (Free Tier)
- **Backend (Node Server)** → Deploy to Render.com (Free Tier)
- **Database (MongoDB Atlas)** → Free Tier 512MB
- **Environment Variables** → Setup `.env` in frontend and backend separately
- **AI API Keys** → Hugging Face Inference API key (free monthly usage)

---

## 🎯 Complete Application Flow

1. Officer logs into system
2. Officer uploads CSV of cases
3. Backend parses and stores cases in MongoDB
4. Cases listed in frontend table
5. Officer can search/filter cases naturally
6. Clicking a case → opens detail page
7. Detail page:
   - AI Summary fetched
   - Visualization Image generated
8. Officer can download:
   - Case PDF report
   - Summary + Visualization bundle
9. Officer logs out securely

---

> 🚀 Built with ❤️ to empower investigations faster, smarter, and with AI.

