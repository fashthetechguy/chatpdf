# 💬 ChatPDF - Bamisoro

This is a **Retrieval-Augmented Generation (RAG)** app built with **LangChain**, **Streamlit**, and **Groq's LLM** (`Gemma2-9b-It`) that lets users **upload PDFs and chat with their content**, while preserving the **chat history** between interactions.

> Supports multi-PDF uploads, session-based memory, and reformulates questions using context from previous chat turns.

---

## 🧠 Features

- 📄 Upload one or more PDFs
- 🤖 Ask context-aware questions
- 🧠 Maintains chat history per session
- 🔍 Reformulates questions using previous conversation
- 📚 Uses `Chroma` vector store + `HuggingFace` embeddings
- ⚡ Powered by `Groq` LLMs (`Gemma2-9b-It`)

---

## 📦 Dependencies

Make sure you have the following installed:


### Example requirements.txt:

pip install -r requirements.txt

streamlit
langchain
langchain-core
langchain-community
langchain-chroma
langchain-groq
langchain-huggingface
langchain-text-splitters
python-dotenv


##  ⚙️ 1 Setup
### Clone the Repository 
git clone https://github.com/your-username/chatpdf-bamisoro.git
cd chatpdf-bamisoro



## 2 Environment Variables

### Create a .env file in the project root:

env
Copy
Edit
HF_TOKEN=your_huggingface_token


## 3 Run the App

bash
Copy
Edit

## Groq API Key
### You’ll need a Groq API key to use the LLM.

### Enter it in the Streamlit app when prompted.




## 🧠 How It Works

### 1. PDF Ingestion

- Upload PDFs via the Streamlit interface.
- PDFs are read with `PyPDFLoader` and chunked using `RecursiveCharacterTextSplitter`.

### 2. Embedding + Vector Store

- Each document chunk is embedded using `all-MiniLM-L6-v2` via HuggingFace.
- Stored in a `Chroma` vector store for efficient retrieval.

### 3. Context-Aware Q&A

- Chat history is maintained with `ChatMessageHistory`.
- Questions are reformulated using a prompt chain for standalone understanding.
- The app fetches relevant document chunks and responds using the LLM.

### 4. Stateful Conversations

- Each session is identified with a custom `session_id`.
- Chat history is isolated by session.





## 🧪 Example Usage

1. **Upload PDFs**  
   Use the file uploader in the Streamlit interface to upload one or more PDF documents.

2. **Input Your Groq API Key**  
   When prompted, enter your [Groq API key](https://console.groq.com/) in the input field.

3. **Ask a Question**  
   Type your question into the chat box, for example:




The app will return a concise, accurate response based on the document content.

4. **Review Chat History**  
Chat history is maintained for each session using the session ID you provide. You can view previous messages for context or follow-up.


## 📄 License
MIT License
