# 🚀 AI Resume Screening & Candidate Ranking System

## 📌 Overview

An advanced AI-powered system that automatically screens resumes, ranks candidates, and provides explainable insights based on job descriptions using modern NLP and machine learning techniques.

---

## 🧠 Features

* 📄 Resume parsing (PDF/DOCX)
* 🔍 Semantic similarity matching using transformer models
* 🧩 Skill extraction & comparison
* 📊 Candidate ranking system
* 💡 Explainable AI insights (why selected/rejected)
* ⚡ Fast similarity search using vector indexing
* 🌐 REST API for integration
* 🐳 Dockerized for deployment

---

## 🏗️ Tech Stack

### Backend

* Python
* FastAPI

### Machine Learning / NLP

* Hugging Face Transformers
* spaCy
* scikit-learn
* Sentence Transformers

### Advanced Tools

* FAISS (vector search)
* MLflow (experiment tracking)
* Docker (containerization)

---

## 🔄 Project Workflow

### 1. Data Input

* Upload resumes
* Provide job description

### 2. Resume Parsing

* Extract and clean text from documents

### 3. Embedding Generation

* Convert text into vector representations using transformer models

### 4. Similarity Matching

* Compute similarity between resume and job description

### 5. Skill Extraction

* Identify and compare required vs existing skills

### 6. Candidate Ranking

* Combine multiple factors into final score

```
final_score = 0.5 * similarity + 0.3 * skills + 0.2 * experience
```

### 7. Explainability

* Highlight:

  * matched skills
  * missing skills
  * ranking reasons

### 8. API Layer

* /upload-resume
* /rank-candidates
* /get-report

---

## ⚙️ Installation

```bash
pip install fastapi uvicorn transformers spacy scikit-learn faiss-cpu sentence-transformers
```

---

## ▶️ Running the App

```bash
uvicorn main:app --reload
```

---

## 🧪 Sample Code

### Generate Embeddings

```python
from sentence_transformers import SentenceTransformer

model = SentenceTransformer('all-MiniLM-L6-v2')

resume_embedding = model.encode(resume_text)
job_embedding = model.encode(job_description)
```

### Compute Similarity

```python
from sklearn.metrics.pairwise import cosine_similarity

score = cosine_similarity([resume_embedding], [job_embedding])
```

### FastAPI Endpoint

```python
from fastapi import FastAPI

app = FastAPI()

@app.post("/match")
def match(resume: str, job: str):
    return {"score": score}
```

---

## 🚀 Advanced Enhancements

* Multi-resume batch processing
* Resume summarization using LLMs
* Chat-based recruiter assistant
* Bias detection in hiring
* Integration with vector databases
* Real-time candidate ranking dashboard

---

## 📦 Deployment

* Dockerize the application
* Deploy on AWS / Render / Railway

---

## 🎯 Use Cases

* HR Tech platforms
* Recruitment automation tools
* Resume screening systems
* Job portals

---

## 💡 Future Improvements

* Add frontend dashboard (React)
* Integrate authentication system
* Improve ranking with deep learning models
* Add multilingual resume support

---

## 👨‍💻 Author

Your Name

---

## 📜 License

MIT License
