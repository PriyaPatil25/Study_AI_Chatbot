Study Bot – AI Powered Study Assistant
Project Overview

Tech Stack
-FastAPI
-MongoDB Atlas
-LangChain
-Groq LLM
-Render Deployment

System Architecture
User → FastAPI → LLM (Groq)
User & Assistant messages → MongoDB
Previous messages → injected into prompt

Memory Implementation
user_id based session
timestamp sorting
contextual injection

API Endpoints
GET /
POST /chat

Deployment
Live Link:
https://study-ai-chatbot.onrender.com
