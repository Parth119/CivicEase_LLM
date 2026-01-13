# CivicEase: Intelligent Citizen Profiling & Automated Benefit Application Agent

> **Bridging the gap between citizens and government benefits through AI-driven automation.**

![Python](https://img.shields.io/badge/Python-3.10%2B-blue)
![Streamlit](https://img.shields.io/badge/Frontend-Streamlit-red)
![LangChain](https://img.shields.io/badge/Framework-LangChain-green)
![Status](https://img.shields.io/badge/Status-Prototype-orange)

## 📖 Overview
**CivicEase** is an M.Tech project designed to solve the "last mile" problem in government welfare delivery. Instead of just searching for schemes, this "Digital Caseworker" agent analyzes user documents, determines strict eligibility, and **automatically fills official PDF application forms**, reducing the application process from hours to minutes.

## 🚀 Key Features
* **📄 Document-to-Profile OCR:** Extracts user demographics (Name, Income, Caste) from uploaded images (Income Certificate/Aadhaar) using `EasyOCR`.
* **🧠 Intelligent Eligibility Engine:** Uses an LLM (Mistral-7B via HuggingFace) to cross-reference user profiles against a logic-base of 500+ government schemes.
* **✍️ Automated Form Filling:** Maps user data onto official PDF coordinates to generate ready-to-sign application forms using `PyMuPDF`.
* **🔍 Semantic Search:** Leverages `FAISS` vector database to find relevant schemes even if the user uses non-standard terms.

## 🛠️ Tech Stack
* **LLM:** Mistral-7B-Instruct-v0.2 / Llama-3-8B (via HuggingFace Inference API)
* **Orchestration:** LangChain
* **Frontend:** Streamlit
* **Vector Database:** FAISS (Facebook AI Similarity Search)
* **OCR:** EasyOCR
* **PDF Manipulation:** PyMuPDF (fitz)

## ⚙️ Architecture Flow
1.  **Ingestion:** User uploads documents or enters bio.
2.  **Profiling:** System constructs a structured JSON profile `{ "income": 150000, "category": "SC" }`.
3.  **Matching:** RAG pipeline filters schemes based on strict logic rules.
4.  **Action:** The "Form Agent" takes the selected scheme template and overlays user data onto the PDF.

## 📦 Installation & Setup

### 1. Clone the Repository
```bash
git clone [https://github.com/Parth119/CivicEase_LLM.git](https://github.com/Parth119/CivicEase_LLM.git)
cd CivicEase 
```
### 2. Create a Virtual Environment
```
python -m venv venv
# Windows
venv\Scripts\activate
# Mac/Linux
source venv/bin/activate
```

### 3. Install Dependencies
```
pip install -r requirements.txt
```

### 4. Set up Environment Variables
Create a .env file in the root directory and add your HuggingFace API token:
```
HUGGINGFACEHUB_API_TOKEN=your_token_here
```