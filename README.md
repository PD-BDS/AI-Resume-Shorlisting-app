# AI Resume Shortlisting App

A powerful and scalable AI-driven tool for **automated resume shortlisting** based on a given job description. This project leverages large language models (LLMs) via the **Groq API** to extract structured insights from job descriptions and intelligently rank the most relevant candidates from a pool of resumes.

---

## 🧠 Project Overview

In recruitment workflows, shortlisting suitable candidates is time-consuming and prone to human bias. This app solves that problem by:

- Parsing **unstructured job descriptions** into structured key-value fields.
- Extracting and ranking **top 5 resumes** based on role relevance.
- Providing **explainable ranking decisions** to ensure transparency.

> Uses **LLaMA-3.3-70B via Groq API** for job and resume intelligence.

---

## 🔧 Features

- 📝 Analyze and extract role-specific insights from job descriptions.
- 📂 Process CSV uploads of candidate resumes.
- 📊 Rank resumes based on match with role requirements.
- 🧾 Save output in structured JSON format.
- ✅ Simple to run, no frontend required.

---

## 🧰 Tech Stack

- **Python 3**
- **Groq API** for LLM-powered reasoning
- **Pandas** for resume dataset handling
- **Pydantic** for schema enforcement
- **Charset Normalizer** for encoding detection
- **JSON** for I/O operations

---

## 📂 Project Structure

```
📁 AI-Resume-Shortlisting-App
├── JobDescriptionStandalone.py       # Extracts key info from job descriptions
├── bestFitStandalone.py              # Ranks resumes based on extracted job details
├── uploaded_file.csv                 # Candidate resume data (CSV format)
├── Job.txt                           # Unstructured job description text
├── JobAnalyzed.json                  # Parsed job description
├── bestFit.json                      # Final ranking output
```

---

## 🚀 How It Works

### 1. Analyze the Job Description

**`JobDescriptionStandalone.py`** reads a text job description and generates structured data (title, skills, qualifications, responsibilities).

```bash
python JobDescriptionStandalone.py
```

➡ Output saved as `JobAnalyzed.json`.

---

### 2. Match & Rank Resumes

**`bestFitStandalone.py`** takes `JobAnalyzed.json` and a CSV of candidate profiles and finds the best 5 candidates based on fit.

```bash
python bestFitStandalone.py
```

➡ Output saved as `bestFit.json`, including reasoning.

---

## 📊 Output Example

```json
{
  "rankedCandidates": [
    {"name": "Jane Doe", "fitScore": 0.92, "reason": "Excellent match in required skills"},
    ...
  ],
  "jobAnalyzed": {
    "jobTitle": "Data Scientist",
    "company": "XYZ Corp",
    ...
  }
}
```

---

## 📦 Requirements

```bash
pip install -r requirements.txt
```

Sample `requirements.txt`:
```txt
groq
pandas
charset_normalizer
pydantic
```

---

## 📌 Notes

- This app uses **Groq API keys** stored as environment variables (`GROQ_API_KEY`).
- Resumes should be formatted and uploaded as a CSV file (`uploaded_file.csv`).
- The app uses **streaming LLM responses**, so output generation is efficient and scalable.

---

## 📚 Keywords

AI recruiting, resume ranking, job matching, NLP, Groq, LLM, BERT, structured extraction, job parsing
