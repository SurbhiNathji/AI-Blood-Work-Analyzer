# 🩸 AI Blood Work Analyzer

An AI-powered web application that analyzes blood work reports using **Google GenAI** and **LangChain**, identifies values as **HIGH, LOW, or NORMAL** based on the reference ranges provided in the report, and generates a simplified health summary with an Indian diet plan.

> ⚠️ **Disclaimer:** This project is for educational and demonstration purposes only. It is not a medical diagnostic tool and should not replace professional medical advice.

## ✨ Features

- 🧪 Extracts blood test values from a pasted report
- 📊 Classifies results as **HIGH, LOW, or NORMAL**
- 🤖 Uses an LLM for natural-language analysis
- 🥗 Generates practical Indian diet suggestions
- 💬 Provides a simple, easy-to-understand health summary
- 🖥️ Interactive web interface built with Streamlit
- 🔐 API key managed securely using `.env`

## 🛠️ Tech Stack

- **Python**
- **LangChain**
- **Google GenAI / Gemma**
- **Streamlit**
- **python-dotenv**

## 🧠 How It Works

The application uses a two-stage LLM pipeline:

```text
Blood Work Report
       ↓
   Streamlit UI
       ↓
┌─────────────────────┐
│   Stage 1: LLM      │
│ Extract test values │
│ + classify results  │
└─────────────────────┘
       ↓
Extracted Analysis
       ↓
┌─────────────────────┐
│   Stage 2: LLM      │
│ Health Summary      │
│ + Indian Diet Plan  │
└─────────────────────┘
       ↓
   Streamlit UI
```

### Stage 1 — Blood Report Analysis

The LLM receives the blood work report and extracts the available test values.

Each result is classified according to the reference range provided in the report:

```text
Test Name: Hemoglobin
Value: 11.2 g/dL
Status: LOW
Reference: 12–16 g/dL
```

### Stage 2 — Health Summary & Diet Plan

The extracted results are passed to a second LLM prompt that generates:

- A simple health summary
- Foods to eat more of
- Foods to limit or avoid
- Practical Indian food suggestions

## 📂 Project Structure

```text
blood-work-analyzer/
│
├── app.py
├── .env
├── .gitignore
├── requirements.txt
└── README.md
```

## ⚙️ Installation

### 1. Clone the repository

```bash
git clone https://github.com/your-username/blood-work-analyzer.git
cd blood-work-analyzer
```

### 2. Create a virtual environment

```bash
python -m venv venv
```

Activate it:

**Windows:**

```bash
venv\Scripts\activate
```

**macOS/Linux:**

```bash
source venv/bin/activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Add your Google API key

Create a `.env` file:

```env
GOOGLE_API_KEY=your_api_key_here
```

Make sure `.env` is included in `.gitignore`:

```text
.env
venv/
__pycache__/
```

### 5. Run the application

```bash
streamlit run app.py
```

The application will open in your browser.

## 🔑 Environment Variables

| Variable | Description |
|---|---|
| `GOOGLE_API_KEY` | Google GenAI API key |

## 🚀 Future Improvements

- Add PDF/image upload for blood reports
- Use structured JSON output instead of plain text
- Add validation for extracted laboratory values
- Improve prompt reliability and error handling
- Add visualization of abnormal values
- Add conversation history
- Add automated report parsing using OCR
- Add RAG-based medical reference information

## 🎯 Learning Goals

This project was built to gain practical experience with:

- **Generative AI**
- **LLM API integration**
- **LangChain**
- **Prompt engineering**
- **Multi-stage LLM workflows**
- **Streamlit application development**
- **Environment variable and API-key management**

## 📌 Project Status

**Completed — with planned improvements for structured outputs, validation, and document/PDF processing.**