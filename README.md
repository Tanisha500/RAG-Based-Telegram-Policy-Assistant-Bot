# RAG-Based-Telegram-Policy-Assistant-Bott

This project is a **Retrieval-Augmented Generation (RAG)** based assistant that answers user queries on **Policy & FAQs** — built entirely using **no-code tools** like n8n, Groq API, and **Telegram Bot API**.

##  Project Demo
Ask a question like:
> _"What's the return policy?"_  
and get a response like:  
> _"Returns are accepted within 30 days if unused and in original packaging."_  

##  Key Features
- Built without code using [n8n](https://n8n.io/) workflows
- Real-time Telegram chat interface (no hosting or HTTPS required)
- Uses **Groq's LLaMA 3 model** to generate context-aware answers
- Performs RAG using manually embedded PDF chunks
- No database, no hosting, no Docker exec — runs 100% locally

##  How It Works
1. **User Message**: A user sends a query to the Telegram bot.
2. **Fetch Updates**: An HTTP node fetches the latest messages (polling-based).
3. **Extract Info**: Chat ID and question are extracted using a `Code` node.
4. **Context Search**: The system matches relevant chunks from the PDF using basic string matching.
5. **Prompt Build**: A final prompt is constructed and sent to Groq API.
6. **Groq Response**: Groq generates an answer using the selected model.
7. **Send Reply**: The response is sent back to the user on Telegram.

##  Source Document
Policy and FAQ content was taken from a sample PDF

##  Tools Used
                               
**n8n** : Visual workflow automation platform    
**Groq API** : LLM (LLaMA 3) for answering questions  
**Telegram** : Chat interface for asking queries      

##  Technologies
- **Language Model**: `llama3-70b-8192` (via Groq)
- **Prompt Engineering**: Custom structured prompts
- **Context Matching**: JavaScript-based filtering in n8n
- **No-code Tools**: n8n, Telegram Bot, Groq API

## Workflow Screenshot
<img width="1819" height="554" alt="image" src="https://github.com/user-attachments/assets/bed42043-cc2b-41f0-b667-c596557c12c9" />

## Telegram Chat Screenshot
<img width="1252" height="442" alt="image" src="https://github.com/user-attachments/assets/562594b3-0b25-4e87-9b68-d3db52dbe61a" />

