# Basic LLM Application Using LCEL

This is a simple LangChain-based project that demonstrates how to deploy and consume a language model application using **LCEL (LangChain Expression Language)** with **FastAPI**, **LangServe**, and **Streamlit**. The application performs language translation using the **Gemma2-9b-It** model hosted by **Groq**.

---

## 🔧 Project Structure

```
.
├── serve.py         # FastAPI backend exposing the LangChain chain
├── client.py        # Streamlit frontend to interact with the backend
├── requirements.txt # Required dependencies
├── .env             # Stores the GROQ API key (not committed)
```

---

## 🚀 Features

- 🔗 LCEL-powered translation chain using LangChain
- 🌐 FastAPI + LangServe backend for serving the chain as an API
- 🧠 Groq-hosted Gemma2-9b-It model for natural language translation
- 🎛️ Streamlit frontend for real-time user interaction
- ⚡ Simple interface for translating text into French

---

## 📦 Requirements

Install the dependencies:

```bash
pip install -r requirements.txt
```

Sample `requirements.txt`:

```txt
langchain
langchain-core
langchain-groq
langserve
fastapi
uvicorn
python-dotenv
streamlit
requests
```

---

## 🔐 Environment Variables

Create a `.env` file in the root directory and add your Groq API key:

```env
GROQ_API_KEY=your_groq_api_key_here
```

---

## 🖥️ Usage

### 1. Start the FastAPI Server

```bash
python serve.py
```

It will be available at: `http://127.0.0.1:8000`

### 2. Launch the Streamlit Frontend

```bash
streamlit run client.py
```

Open the local Streamlit URL in your browser to interact with the app.

---

## 📥 Example Input

**User Input (in Streamlit):**
```
Hi
```

**Backend Output (via Groq/Gemma2-9b-It):**
```
Salut
```

---

## 🧱 How it Works

1. `serve.py` sets up a FastAPI server that defines a LangChain chain using:
   - A `ChatPromptTemplate` for defining the prompt
   - Groq's `Gemma2-9b-It` model for LLM inference
   - `StrOutputParser` to parse the result

2. `LangServe` is used to expose the chain at `/chain`.

3. `client.py` sends input to this endpoint using `requests` and displays the output via Streamlit.

---

## 📌 Future Improvements

- Add language selection dropdown
- Support other LLM models
- Add user input validation and error handling

---

## 🧠 Tech Stack

- Python
- LangChain + LCEL
- Groq API
- FastAPI + LangServe
- Streamlit
