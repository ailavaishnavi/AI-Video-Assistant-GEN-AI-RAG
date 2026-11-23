# 🎥 AI Video Assistant

**Transcribe · Summarise · Extract Insights · Chat with Your Videos**

AI Video Assistant is an AI-powered meeting and video intelligence application that turns YouTube videos and local audio/video files into useful, searchable information. It processes the audio, generates a transcript, creates an AI-powered summary, extracts important discussion points, and lets users ask questions about the video through a chat interface.

## ✨ Features

- **YouTube video input:** Analyse a video by providing its YouTube URL.
- **Local media input:** Process supported audio and video files from your computer.
- **Audio processing:** Extract, convert, and prepare audio for transcription.
- **Speech-to-text:** Generate a text transcript from spoken content using OpenAI Whisper.
- **Language support:** Includes an English transcription workflow and Hindi-to-English translation support.
- **Automatic title generation:** Generate a meaningful title based on the video content.
- **AI summarisation:** Convert long transcripts into concise summaries and key discussion points.
- **Information extraction:** Identify useful information such as action items, decisions, and open questions.
- **Full transcript view:** Review the generated transcript.
- **RAG-based meeting chat:** Ask questions in natural language and retrieve answers using information from the processed transcript.
- **Streamlit interface:** Use the application through an interactive web interface.

## 🖥️ Application Screenshots

### 1. Analysis Results and Summary

The results view displays the generated session title, summary, key discussion points, and an option to open the full transcript.

![Analysis results and summary](screenshots/01-analysis-summary.png)

### 2. Home Page

The home screen provides the starting point for analysing a YouTube video or a local media file.

![Ready to analyse home page](screenshots/02-ready-to-analyse.png)

### 3. Chat with Your Meeting

The chat interface allows users to ask questions about the processed video and get responses grounded in its transcript.

![Meeting chat interface](screenshots/03-meeting-chat.png)

## 🏗️ How It Works

The application follows a sequence of processing steps:

```text
YouTube URL / Local Audio or Video
                |
                v
       Audio Extraction
       and Preprocessing
                |
                v
          Audio Chunking
                |
                v
       Speech-to-Text
       (OpenAI Whisper)
                |
                v
           Transcript
                |
        +-------+--------+
        |       |        |
        v       v        v
     Title   Summary   Information
   Generation         Extraction
                         |
                         v
              Action Items / Decisions /
                  Open Questions
                |
                v
        Text Chunking and Embeddings
                |
                v
          ChromaDB Vector Store
                |
                v
        Similarity-Based Retrieval
                |
                v
          LLM-Powered RAG Chat
                |
                v
       Answers about the Video
```

## 🛠️ Technology Stack

| Technology | Purpose |
|---|---|
| Python | Main programming language |
| Streamlit | Web application interface |
| yt-dlp | Retrieving audio from YouTube videos |
| Pydub | Audio processing and conversion |
| FFmpeg | Media conversion and audio handling |
| OpenAI Whisper | Speech recognition and transcription |
| Deep Translator | Hindi-to-English translation support |
| LangChain | LLM orchestration and RAG workflow |
| Mistral AI | Language model for text generation and responses |
| Hugging Face Sentence Transformers | Text embeddings |
| ChromaDB | Vector storage and similarity search |
| PyTorch / Torchaudio | Backend support for Whisper |

## ⚙️ Installation and Setup

### Prerequisites

- Python 3.10 or later
- FFmpeg installed and available on your system PATH
- Required API credentials for the services configured in the project

### 1. Get the project files

Download or clone this project repository to your computer.

```bash
git clone <your-github-repository-url>
cd <your-project-folder>
```

Replace the placeholders with your GitHub repository URL and project folder name.

### 2. Create and activate a virtual environment

**Windows (PowerShell):**

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
```

**macOS / Linux:**

```bash
python3 -m venv .venv
source .venv/bin/activate
```

### 3. Install FFmpeg

FFmpeg is required for audio/video processing. Install it using the instructions for your operating system and make sure the `ffmpeg` command is available in your terminal.

### 4. Install Python dependencies

```bash
pip install -r Requirements.txt
```

### 5. Configure environment variables

Create a `.env` file in the project root and add the API keys required by the source code.

```env
MISTRAL_API_KEY=your_mistral_api_key
```

Keep your actual API keys private. Check the project's source code for the exact environment-variable names used by your local version. Never commit the `.env` file to GitHub.

### 6. Run the application

```bash
streamlit run app.py
```

Open the local URL printed in the terminal (usually `http://localhost:8501`) in your browser.

## 🚀 How to Use

1. Start the Streamlit application.
2. Paste a YouTube URL or provide a local audio/video file path in the input section.
3. Select the required language.
4. Click **Analyse** and wait for the processing pipeline to complete.
5. Review the generated session title, summary, and extracted information.
6. Open the full transcript when you need to inspect the spoken content.
7. Use **Chat with your Meeting** to ask questions about the processed video.

## 💬 Example Questions

You can ask questions such as:

- What is the main topic of this video?
- What are the key discussion points?
- What decisions were made?
- Which action items or follow-ups were mentioned?
- What does the speaker say about a particular topic?
- Can you summarise the discussion about a specific issue?

## 📌 Project Information

- **Project:** AI Video Assistant
- **Author:** Aila Vaishnavi

---

*Before publishing, verify the dependency-file name, environment-variable names, and supported file formats against the exact code in your project folder.*
