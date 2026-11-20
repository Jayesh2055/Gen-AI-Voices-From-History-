# Problem Statement 16: Persona Chatbot (Historical Figure)

A Python-only Streamlit app for talking with an AI role-play of a historical figure. Choose from six figures, ask questions in a chat interface, and continue the conversation while the browser session stays open.

The app labels the conversation as AI role-play and asks the model to stay grounded in known history, acknowledge uncertainty, avoid invented quotations, and not pretend to be the real person. AI responses can still be wrong; verify important details with reliable sources.

## Figures included

- Cleopatra VII
- Leonardo da Vinci
- Mahatma Gandhi
- Albert Einstein
- A. P. J. Abdul Kalam
- Marie Curie

## Requirements

- Python 3.10 or newer
- A Groq API key
- Internet connection while chatting

## Run on Windows PowerShell

```powershell
Set-Location -LiteralPath "C:\path\to\problem_statement_16"
py -m venv .venv
.\.venv\Scripts\python.exe -m pip install -r requirements.txt
Copy-Item .env.example .env
notepad .env
```

Add your key after `GROQ_API_KEY=` in `.env`, save, then run:

```powershell
.\.venv\Scripts\python.exe -m streamlit run app.py
```

Open the local address shown in the terminal (usually <http://localhost:8501>). The API key stays server-side. `.env` and Streamlit's local secrets file are excluded from Git.

### Optional Streamlit secrets setup

You can also store your key in `.streamlit/secrets.toml`:

```toml
GROQ_API_KEY = "your_groq_key_here"
GROQ_CHAT_MODEL = "openai/gpt-oss-120b"
```

## Try these questions

1. What challenge shaped your life the most?
2. What do people often misunderstand about your time?
3. What advice would you give a student today?
4. Which of your ideas influenced later generations?
5. What is one thing historians still debate about your life?

Choosing a different figure or starting a new conversation clears the current chat. The app does not save conversations after the browser session ends.

## Project files

- `app.py` — Streamlit UI, persona instructions, session history, and Groq API request.
- `.streamlit/config.toml` — app theme.
- `.env.example` — local key configuration template.
- `requirements.txt` — Python packages.
