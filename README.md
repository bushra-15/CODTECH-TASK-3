# CODTECH-TASK-3

Name:BUSHRA ASRAR KHAN
Company:CODTECH IT SOLUTIONS
ID:CT4MQFS
Domain:Data Science 
Duration:4 months

Project: Sentiment Analysis Web App with Machine Learning & FastAPI
As part of my internship at CODTECH IT SOLUTIONS, I built an end-to-end Sentiment Analysis Web Application. The project combines a Logistic Regression ML model with a user-facing web interface powered by FastAPI, serving real-time predictions on user input.

Objective:
To develop a complete machine learning pipeline and deploy it as a dynamic web application using FastAPI, supporting real-time sentiment classification from text input.

🗂️ Project Pipeline
1. Data Collection
Source: UCI Sentiment Labelled Sentences Dataset (simplified subset used)
Tool: requests module for downloading

2. Data Preprocessing:
Cleaning: Lowercasing and punctuation removal using pandas
TF-IDF vectorization using TfidfVectorizer
Train/test split with scikit-learn
Serialized using joblib into data/processed/

3. Model Training:
Algorithm: Logistic Regression
Accuracy: ~100% on small dataset
Tools: scikit-learn, joblib
Model saved as sentiment_model.pkl

4. API Deployment:
Framework: FastAPI
Endpoints:
POST /predict: Returns sentiment label and confidence
GET /: Returns HTML page using Jinja2 templating

5. Frontend Integration:
Jinja2 templates used to render index.html
Static files (CSS, JS) served using StaticFiles from FastAPI
Enabled browser interaction for sentiment predictions

from fastapi.staticfiles import StaticFiles
from fastapi.templating import Jinja2Templates
from fastapi import Request

app.mount("/static", StaticFiles(directory="static"), name="static")
templates = Jinja2Templates(directory="src/templates")

@app.get("/")
async def read_root(request: Request):
    return templates.TemplateResponse("index.html", {"request": request})

6. Run the App:
uvicorn src.app:app --reload

7. requirements.txt:
fastapi>=0.68.0
uvicorn>=0.15.0
scikit-learn>=0.24.2
pandas>=1.3.0
joblib>=1.0.1
requests>=2.26.0
python-multipart

8. Technologies Used:
Programming Language-Python
Backend-FastAPI
Frontend Templating-Jinja2
Machine Learning-Scikit-learn, TfidfVectorizer, LogisticRegression
Serialization-joblib
API Testing-Uvicorn
Web Assets-StaticFiles (CSS, JS)
Dataset-UCI Sentiment Labelled Sentences

9. Outcome:
Built a robust, full-stack Sentiment Analysis Web App
Learned about frontend-backend integration using FastAPI
Gained hands-on experience in model deployment, API design, and template rendering
