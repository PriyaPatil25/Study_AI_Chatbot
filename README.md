Study Bot – AI Powered Study Assistant
Project Overview:
Study Bot is a context-aware AI chatbot designed to assist users with academic questions. The chatbot integrates a Large Language Model (LLM) with MongoDB to store and retrieve previous conversations, enabling persistent and contextual responses.

Live Deployment
Hosted API:
https://study-ai-chatbot.onrender.com

Tech Stack
-FastAPI
-MongoDB Atlas
-LangChain
-Groq LLM API
-Render (Deployment)

System Architecture
User → FastAPI Backend → MongoDB (History Retrieval) → LLM → Store Response → Return Output

The system retrieves past messages based on user_id and injects them into the prompt before generating a response.

Memory Implementation
Each conversation is stored with:
-user_id
-role (user/assistant)
-message
-timestamp

On each request:
-Previous messages are fetched
-Sorted chronologically
-Passed into the prompt template
-LLM generates a contextual response
-Conversation is saved back to MongoDB
This ensures persistent session memory.

API Endpoints
GET /
Returns welcome message.

POST /chat
Request Body:
{
  "user_id": "student1",
  "question": ""
}

Response:
{
  "response": "Newton's Laws describe..."
}

Running Locally

1.Clone the repository

2.Install dependencies
pip install -r requirements.txt

3.Create a .env file with:
GROQ_API_KEY=your_key
MONGODB_URI=your_uri

4.Run the server:
uvicorn app:app --reload

Deployment
The application is deployed on Render.

Build Command:
pip install -r requirements.txt

Start Command:
uvicorn app:app --host 0.0.0.0 --port 10000

And You are Done.
