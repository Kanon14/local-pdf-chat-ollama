# local-pdf-chat-ollama

## Overview
This project is a PDF-based conversational assistant, allowing users to upload PDF documents and ask questions about the content within them. The assistant extracts the text from the uploaded PDF, indexes the content using embeddings, and allows users to interactively query the document using a conversational model.

## How it Works
1. **File Upload**: When the user uploads a PDF, the system extracts the text from each page using PyPDF2.
2. **Text Splitting**: The extracted text is split into smaller chunks to ensure better embeddings.
3. **Embeddings & Vector Store**: Using Ollama's text embedding model, the system generates embeddings for each text chunk and stores them in Chroma for fast retrieval.
4. **Conversational Interface**: Users can ask questions after the document is processed. The system retrieves relevant text from the PDF and generates responses using the conversational retrieval chain.
5. **Memory & Context**: The system remembers previous interactions in the session, allowing for coherent and context-aware conversations.

## Project Setup
- Python 3.10+
- Compatible cuda toolkit and cudnn installed on your machine
- Anaconda or Miniconda installed on your machine
- An ollama installed on your machine. [[download link](https://ollama.com/download)]
- Install LLM model compatible with your machine, information can be found in [Ollama](https://github.com/ollama/ollama)

### Installation
1. Clone the repository:
```bash
git clone https://github.com/Kanon14/local-pdf-chat-ollama.git
cd local-pdf-chat-ollama
```

2. Create and activate a Conda environment:
```bash
conda create -n local-pdf-chat python=3.10 -y
conda activate local-pdf-chat
```

3. Install dependencies:
```bash
pip install -r requirements.txt
```

## How to Run
1. Installing required ollama model for LLM and create embeddings:
```bash
ollama pull llama3.2
ollama pull nomic-embed-text
```

2. Executing the project:
```bash
chainlit run app.py
```

3. Then, access the application via your web browser:
```bash
open http://localhost:<port>
```

4. Interact with the system:
- Upload a PDF file when prompted.
- Ask questions based on the content of the PDF.
- The assistant will provide answers and reference the relevant parts of the document. 
- To upload a new pdf file, click on `New Chat` and start over again. 