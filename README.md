# 🧾 LegalLens (LegalDoc Genie)  - for google gen-ai exchange hackathon
**Demystifying Legal Documents for India using Generative AI**  

---

## 🚨 Problem  

In India, everyday citizens sign **rental agreements, BNPL/loan contracts, and app Terms & Conditions** filled with archaic legal jargon.  
- Rental deposits often exceed **6–10 months’ rent** without tenants realizing.  
- BNPL/fintech apps bury **prepayment penalties & late fee ladders** in small print.  
- ToS routinely grant **broad data-sharing and background tracking rights**.  

These create **information asymmetry**: people agree to unfair terms they don’t understand, leading to exploitation.  

---

## 💡 Solution – *LegalLens*  

LegalLens is a **Google Cloud–powered AI assistant** that:  
- 📄 **Simplifies** legal documents into plain English or any other indian language.  
- 🛡️ **Flags risky clauses** (India-specific heuristics).  
- ✅ **Generates checklists** of obligations & deadlines.  
- ⚡ Works on **web uploads, browser highlights, and mobile scans**.  

**Not legal advice** – purely informational to empower better decision-making.  

---

## ✨ Features (MVP Demo)  

- **Upload/Scan → Plain-language Summary**  
  - PDF or scanned image → Document AI OCR → Gemini summary.  
  - Change language for easy accessibility.  

- **ClauseMap Risk Heatmap**  
  - Auto-detects common risky clauses:  
    - 🟥 *Security deposit > 3 months* (rentals)  
    - 🟥 *Prepayment penalty / foreclosure charges* (loans/BNPL)  
    - 🟨 *Mandatory arbitration / class-action waiver* (ToS)  
    - 🟨 *Data sharing without opt-out* (apps)  
  - Each risk includes **why it matters** + **clause citation**.  

- **Browser Extension (Highlight → Simplify)**  
  - Right-click any ToS clause → “Simplify with LegalLens.”  
  - Popup shows plain meaning + risk badge.  

---

## 📊 India-Specific Differentiators  

- **Hinglish summaries** (English + Hindi mix).  
- **PII Shield** → masks Aadhaar, PAN, phone numbers before upload.  
- **Negotiation Prompts** (non-legal):  
  - “Can we cap deposit at 2–3 months and add a return deadline?”  
  - “Please confirm no prepayment penalty in writing.”  
- **Consumer Rights Nudges** → links to RBI/Consumer Protection resources.  

---

## 🏗️ Architecture (Google Cloud)  

**Frontend**  
- Streamlit web app (prototype)  
- Chrome Extension (context-menu demo)  

**Backend (GCP)**  
- Document AI → OCR & clause structuring  
- Vertex AI (Gemini 1.5/Flash) → summaries, Hinglish rewrite, risk explanations  
- Cloud Run / Functions → API endpoints  
- Firebase (Auth + Hosting) → roadmap  
- Cloud DLP → client-side redaction of Aadhaar/PAN/phone  

**Optional (roadmap)**  
- Vertex Matching Engine for fast Q&A with citations  
- Firestore for user-doc storage  
- BigQuery for anonymized analytics  

---

## 🛠️ Tech Stack  

- **Google Cloud:** Document AI, Vertex AI (Gemini), Cloud DLP, Firebase  
- **Frontend:** Streamlit (demo), Chrome Extension  
- **Backend:** Python (FastAPI on Cloud Run)  
- **Other:** pdfplumber, regex heuristics, cloud translation  

---

## 🎥 Demo  

- **Prototype (Streamlit):** [Live App](#)  
- **3-min Video:** [Watch Here](#)  
- **Slides:** [Pitch Deck](#)  

---

## 📅 Roadmap  

- ✅ MVP: Upload → Summary → Risk Heatmap → Hinglish toggle  
- 🔜 Checklist export (calendar reminders for deadlines)  
- 🔜 WhatsApp bot (share doc → instant risks)  
- 🔜 Compare 2 contracts (see deposit/fee/notice differences)  
- 🔜 Multilingual support (Hindi, Tamil, Kannada, Bengali)  

---

## ⚖️ Disclaimer  

LegalLens provides **informational summaries only**.  
It does **not** constitute legal advice. For binding interpretation or disputes, please consult a qualified lawyer.  

---

## 🚀 Quickstart (for developers)  

```bash
# Clone the repo
git clone https://github.com/yourusername/legal-lens.git
cd legal-lens

# Create virtual environment & install deps
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt

# Run the app
streamlit run app/app.py

