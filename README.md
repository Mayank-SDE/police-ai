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

# Incident Reports

| Unique ID | Name | Age | Gender | Race | Imputation Probability | Date of Injury | Location of Injury | City | State | County | Full Address | Latitude | Longitude | Agency Involved | Force Level | Brief Description | Current Status |
|:---------:|:----:|:---:|:------:|:----:|:----------------------:|:--------------:|:------------------:|:----:|:-----:|:------:|:------------:|:--------:|:---------:|:---------------:|:-----------:|:-----------------:|:--------------:|
| 31490 | John Keene | 35 | Male | Caucasian | Not imputed | 9/18/2018 | 123 Maple Street | Springfield | IL | Sangamon | 123 Maple Street Springfield IL 62701 Sangamon | 39.781721 | -89.650148 | Springfield Police Department | Physical | John Keene was reported missing from his apartment in 2018. Police later found two distinct types of blood samples on the floor of his apartment. The circumstances surrounding his disappearance and the blood samples are under investigation. | Pending investigation and closed |
| 31495 | Ashley McClendon | 28 | Female | African-American/Black | Not imputed | 12/31/2021 | South Pearl Street and Tory Road | Pageland | SC | Chesterfield | South Pearl Street and Tory Road Pageland SC 29728 Chesterfield | 34.7452955 | -80.3930567 | Pageland Police Department | Vehicle | Ashley McClendon's boyfriend, Marcus Allen Davis, fled from police resulting in a crash killing McClendon. | Pending investigation and closed |
| 31496 | Name withheld by police | - | Female | Race unspecified | NA | 12/31/2021 | 1500 21st Street | Meridian | MS | Lauderdale | 1500 21st Street Meridian MS 39301 Lauderdale | 32.3793294 | -88.693972 | Meridian Police Department | Gunshot | Police responded to a man causing a disturbance. A shootout occurred, resulting in the deaths of a man and a woman. | Pending investigation and closed |
| 31497 | Name withheld by police | - | Male | Race unspecified | NA | 12/31/2021 | 1500 21st Street | Meridian | MS | Lauderdale | 1500 21st Street Meridian MS 39301 Lauderdale | 32.3793294 | -88.693972 | Meridian Police Department | Gunshot | Police responded to a man causing a disturbance. A shootout occurred, resulting in the deaths of a man and a woman. | Pending investigation and closed |
| 31491 | Johnny C. Martin Jr. | 36 | Male | Race unspecified | NA | 12/30/2021 | Martinez Lane | Nicholls | GA | Coffee | Martinez Lane Nicholls GA 31554 Coffee | 31.5307934 | -82.637819 | Coffee County Sheriff's Office | Gunshot | Johnny C. Martin Jr. died after a police chase and carjacking incident. | Pending investigation and closed |
| 31492 | Dennis McHugh | 44 | Male | European-American/White | NA | 12/30/2021 | 435 E 4th Street | Beaumont | CA | Riverside | 400 E 4th Street Beaumont CA | 33.9306751 | -116.960451 | Riverside Police Department | Gunshot | Dennis McHugh was found dead at home with a gunshot wound. Possible suicide. | Pending investigation and closed |
| 31498 | Emily Clark | 25 | Female | Caucasian | Not imputed | 5/12/2023 | 789 Maple Avenue | Chicago | IL | Cook | 789 Maple Avenue Chicago IL 60611 Cook | 41.878113 | -87.629799 | Chicago Police Department | Physical | Emily Clark was found dead under suspicious circumstances with signs of struggle and theft. | Pending investigation and closed |
| 31499 | David Larson | 38 | Male | Hispanic | Not imputed | 6/23/2023 | 345 Oakwood Drive | Dallas | TX | Dallas | 345 Oakwood Drive Dallas TX 75201 Dallas | 32.7766643 | -96.7969879 | Dallas Police Department | Physical | David Larson attempted to steal jewelry but was caught by police after fleeing. | Pending investigation and closed |
| 31500 | Rachel Smith | 22 | Female | African-American/Black | Not imputed | 7/10/2023 | 2323 Willow Street | Baltimore | MD | Baltimore | 2323 Willow Street Baltimore MD 21201 Baltimore | 39.290384 | -76.612189 | Baltimore Police Department | Non-lethal | Rachel Smith was found dead in an abandoned building. Cause of death unknown. | Pending investigation and closed |
| 31501 | Thomas Bryant | 29 | Male | Caucasian | Not imputed | 8/21/2023 | 789 Pine Road | Los Angeles | CA | Los Angeles | 789 Pine Road Los Angeles CA 90001 Los Angeles | 34.052235 | -118.243683 | Los Angeles Police Department | Non-lethal | Thomas Bryant was found dead with a suicide note, but investigation ongoing. | Pending investigation and closed |
| 31502 | Laura James | 31 | Female | Hispanic | Not imputed | 9/15/2023 | 456 Cedar Avenue | Miami | FL | Miami-Dade | 456 Cedar Avenue Miami FL 33101 Miami-Dade | 25.76168 | -80.19179 | Miami-Dade Police Department | Non-lethal | Laura James was caught attempting to steal, apprehended without incident. | Pending investigation and closed |
| 31503 | David Thompson | 5 | Male | Caucasian | Not imputed | 10/5/2023 | Central Park | New York | NY | New York | Central Park New York NY 10024 New York | 40.785091 | -73.968285 | New York Police Department | Non-lethal | David Thompson, a 5-year-old, was found dead in Central Park. Suspect sought. | Pending investigation and closed |
| 31504 | James Williams | 42 | Male | African-American/Black | Not imputed | 9/22/2023 | 203 Maple Drive | Houston | TX | Harris | 203 Maple Drive Houston TX 77002 Harris | 29.760427 | -95.369804 | Houston Police Department | Physical | James Williams was shot during a robbery attempt. One suspect arrested. | Pending investigation and closed |
| 31505 | Jessica Grant | 19 | Female | Hispanic | Not imputed | 10/1/2023 | 101 Birch Avenue | San Diego | CA | San Diego | 101 Birch Avenue San Diego CA 92101 San Diego | 32.715736 | -117.161087 | San Diego Police Department | Non-lethal | Jessica Grant found dead in apartment under mysterious circumstances. | Pending investigation and closed |

