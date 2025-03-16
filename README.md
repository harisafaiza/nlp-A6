# RAG Chatbot

This project implements a Retrieval-Augmented Generation (RAG) chatbot using LangChain, OpenAI GPT, and ChromaDB. The chatbot retrieves personal documents and generates responses based on user queries.

## 📁 Project Structure
```
rag_chatbot/
│── documents/         # Folder containing personal documents
│── main.py            # Streamlit frontend
│── backend.py         # FastAPI backend
│── retriever.py       # Handles document retrieval
│── chatbot.py         # Defines the chatbot logic
│── submission.py      # Generates JSON submission file
│── requirements.txt   # Dependencies
│── submission.json    # JSON output (generated)
│── README.md          # Instructions
```

## 🚀 Setup & Installation

### 1️⃣ Clone the Repository
```bash
git clone https://github.com/your-repo/rag_chatbot.git
cd rag_chatbot
```

### 2️⃣ Install Dependencies
```bash
pip install -r requirements.txt
```

### 3️⃣ Prepare Personal Documents
- Place your resume, essays, or other documents in the `documents/` folder.
- These files will be used by the retriever to fetch relevant information.

## 🔹 Running the Application

### 1️⃣ Start the Backend (FastAPI)
```bash
uvicorn backend:app --reload
```
- This starts the FastAPI server that processes requests from the frontend.
- The chatbot processes user queries and retrieves document-based answers.

### 2️⃣ Run the Frontend (Streamlit)
```bash
streamlit run main.py
```
- This launches the chatbot's web interface, allowing users to interact with the system.

## 🔹 Generating JSON Submission
To create the JSON file with chatbot responses:
```bash
python submission.py
```
This generates `submission.json` containing structured Q&A pairs:
```json
[
  {"question": "How old are you?", "answer": "Your answer here"},
  {"question": "What is your highest level of education?", "answer": "Your answer here"}
]
```
- The JSON file is formatted according to the assignment submission requirements.

## 🔹 API Usage
The chatbot can be accessed via API as well:
```bash
curl -X POST "http://127.0.0.1:8000/chat" -H "Content-Type: application/json" -d '{"question": "How old are you?"}'
```
- This sends a question to the chatbot and retrieves a structured response.
- The API allows integration with other systems if needed.

## 📌 Features
- ✅ Retrieves answers from personal documents.
- ✅ Uses OpenAI GPT as the generator (Llama3-70B can be added for comparison).
- ✅ FastAPI backend for handling requests and responses.
- ✅ Streamlit frontend for an interactive chatbot experience.
- ✅ Generates JSON output for easy assignment submission.
- ✅ Modular code structure for easy customization.

## 🛠️ Future Improvements
- 🔹 Support for multiple LLMs like Claude or Mistral.
- 🔹 Integration with external knowledge bases (Wikipedia, Google Search API, etc.).
- 🔹 Advanced document parsing to handle different file formats like PDFs, Word Docs, and Web Pages.
- 🔹 Chatbot memory to maintain conversational history.



