# Personalized Recruiter Chatbot (Powered by Gemini)

This project is a **personalized chatbot** that acts as **Karishma Rahaman’s virtual assistant**.  
The chatbot answers recruiter queries using **Gemini** with context from Karishma’s resume and summary.  
It also has **two specialized tools** for real-time communication:  

1. **Recruiter Details Tool** → Records recruiter details (email, name, notes) when they show interest.  
2. **Unknown Question Tool** → Logs and notifies Karishma in real time when the chatbot cannot answer a recruiter’s question.  



##  Features

- Resume-aware conversations (powered by Gemini and Karishma’s resume).  
- Tool 1: Records recruiter details + pushes real-time notification.  
- Tool 2: Records unknown questions + escalates to Karishma.  
- Instant notifications via **Pushover API**.  
- Simple and interactive chat interface using **Gradio**.  



##  Tech Stack

- **LLM**: Gemini (Google Generative Language API)  
- **Frameworks**: Python, Gradio  
- **Notifications**: Pushover API  
- **File Parsing**: PyPDF (for resume ingestion)  
- **Environment Management**: python-dotenv  



##  Flow of Work

Here’s how the system works step by step:

1. **User (Recruiter) asks a question** in the Gradio chat interface.  
2. **Gemini LLM** receives the query along with context (Karishma’s resume + summary).  
3. LLM tries to answer:  
   - If the recruiter shows **interest in connecting** → LLM calls **Tool 1** (`record_user_details`).  
   - If the recruiter asks something the LLM **cannot answer** → LLM calls **Tool 2** (`record_unknown_question`).  
4. **Tools** interact with the **Pushover API**:  
   - Tool 1 → Sends a message with recruiter’s name, email, and notes.  
   - Tool 2 → Sends a message with the unanswered recruiter question.  
5. **Karishma receives real-time notifications** directly on her device.  
6. The conversation continues naturally until the recruiter leaves or shares details.  



###  Workflow Diagram (Text-Based)
![A flowchart showing the process from Recruiter to Gradio Chat, then to a Gemini LLM which uses one of two tools. The tools then trigger a Pushover API to send a notification to Karishma.](https://drive.google.com/file/d/1zw5o7sYAlIpaTf3uG3q81QptzS2s0RwN/view?usp=drive_link)
