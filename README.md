# 📚 AI-Powered Medical Chatbot with RAG Pipeline

An end-to-end **AI-powered medical chatbot** delivering **credible, medically-sourced answers** using a **Retrieval Augmented Generation (RAG)** pipeline.

---

## ⚙️ Project Structure

### ✅ Phase 1 — Build the Knowledge Base

* Load medical PDFs with `PyPDFLoader` (LangChain)
* Split text into chunks with overlap using `RecursiveCharacterTextSplitter`
* Convert chunks to embeddings (`SentenceTransformers all-MiniLM-L6-v2`)
* Store embeddings in **FAISS**

### ✅ Phase 2 — Connect to LLM

* Load **Mistral 7B Instruct v3** from Hugging Face with `HuggingFaceEndpoint`
* Use a custom prompt to restrict answers to the context only
* Use `RetrievalQA` with FAISS retriever (top 3 docs)
* Return answers with source pages

### ✅ Phase 3 — User Interface

* Build UI with **Streamlit**
* Maintain chat history with `st.session_state`
* Use `@st.cache_resource` for vector store
* Display sources for transparency

---

## 🧩 Tech Stack

* **LangChain** — RAG pipeline
* **Hugging Face** — LLM and embeddings
* **FAISS** — Vector database
* **Streamlit** — UI
* **Python** — Core language

---

## 🚀 Run Locally

```bash
git clone https://github.com/<your-username>/medical-chatbot-rag.git
cd medical-chatbot-rag
pip install -r requirements.txt
echo HF_TOKEN="<your_token>" > .env
streamlit run app.py
```

---

## 📌 Example

✅ *"What is diabetes?"* → Detailed answer + page numbers
❌ *"Who won the World Cup?"* → "I don't know that information."

---

## 📬 Contact

janailluru2207@gmail.com — Contributions welcome!
