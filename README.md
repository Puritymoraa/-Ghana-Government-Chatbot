# 🇬🇭 Ghana Government Chatbot

A RAG-based AI chatbot that makes Ghana government information easily accessible by answering questions from official government documents with accurate source citations.

## Problem Statement

Finding information from Ghana government agencies is difficult because:
- Documents are scattered across multiple websites
- PDFs are long, complex, and hard to search
- No unified way to query government information

## Solution

An intelligent chatbot that:
- Answers questions using real government documents
- Provides source citations for transparency
- Supports voice interaction
- Makes adding new sources effortless via browser extension

## Key Features

- **RAG Architecture**: Retrieval Augmented Generation prevents hallucination
- **Voice Chat**: Ask questions with your voice, get spoken answers
- **Browser Extension**: Add any webpage to the knowledge base with one click
- **Climate Filtering**: Automatic detection and filtering of climate-related content
- **Source Citations**: Every answer shows which documents were used
- **Easy Extensibility**: Upload PDFs, provide URLs, or use the extension

## Technology Stack

- **LLM**: Llama 3.1 (8B) via Ollama and Phi 3
- **Vector DB**: ChromaDB with sentence-transformers embeddings
- **Backend**: FastAPI (Python)
- **Frontend**: HTML/CSS/JavaScript (Vanilla)
- **Document Processing**: PyMuPDF, BeautifulSoup, Selenium
- **Voice**: Web Speech API + Google Text-to-Speech
- **Extension**: Chrome Extension (Manifest V3)

## Architecture

```
User Interface (Web + Extension)
         ↓
    FastAPI Backend
         ↓
    ┌────┴────┐
    ↓         ↓
Retrieval  Generation
(ChromaDB) (Llama 3.1 + Phi 3)
    ↓         ↓
    └────┬────┘
         ↓
   Document Store
```

## Installation

### Prerequisites
- Python 3.8+
- Ollama installed
- Chrome browser (for extension)

### Backend Setup

```bash
# Clone repository
git clone https://github.com/yourusername/ghana-gov-chatbot.git
cd ghana-gov-chatbot

# Install dependencies
pip install -r requirements.txt

# Pull Llama model
ollama pull llama3.1

# Start backend
cd ghana-chatbot
uvicorn api:app --host 0.0.0.0 --port 8000
```

### Frontend Setup

```bash
# Open web interface
cd ghana-chatbot
# Open index.html in your browser
```

### Browser Extension Setup

1. Open Chrome and go to `chrome://extensions`
2. Enable "Developer mode"
3. Click "Load unpacked"
4. Select the `ghana-chatbot-extension` folder

## Usage

### Web Interface
1. Open `index.html` in your browser
2. Ask questions in the chat interface
3. Upload PDFs or provide URLs to add documents
4. Click microphone icon for voice chat

### Browser Extension
1. Navigate to any Ghana government website
2. Click the extension icon
3. Click "Add Current Page" to index content
4. Ask questions directly in the extension

## Novelty Features

### 1. Voice Chat
- Speech-to-text using Web Speech API
- Text-to-speech using Google TTS
- Hands-free interaction

### 2. Browser Extension
- One-click webpage addition
- Automatic content extraction
- Instant availability for queries

## Project Context

This project was built as a final project for Natural Language Processing (NLP) course at Ashesi University. It demonstrates:
- Practical RAG implementation
- Document processing pipelines
- Vector database usage
- Full-stack development
- Browser extension development

## Team

- Purity Moraaa Kinaro
- Velma tieno Ombiuuya
- Alvin Appiah
- Ibrahim Abdou

##  Project Achievements

-  Fit-for-purpose solution with live demo
-  Extensible design (multiple ways to add sources)
-  Climate-focused with automatic detection
-  Innovative features (voice + extension)

## Performance

- **Response Time**: 6-7 seconds (using Google Colab T4 GPU)
- **Accuracy**: High (answers grounded in actual documents)
- **Scalability**: Handles thousands of document chunks

## Technical Highlights

### Chunking Strategy
- 1000 characters per chunk
- 200-character overlap
- Sentence-boundary splitting

### Retrieval
- Semantic search via ChromaDB
- Top-k selection (default: 5)
- Metadata filtering (climate, year, source)

### Generation
- Prompt engineering to prevent hallucination
- Context-grounded responses
- Automatic source citation

## API Endpoints

```
POST /chat              - Ask questions
POST /upload-pdf        - Upload documents
POST /scrape-url        - Scrape websites
POST /text-to-speech    - Generate audio
GET  /stats             - Database statistics
GET  /health            - System health check
```

## Known Limitations

- Currently optimized for English documents
- Requires manual updates for new government content
- No user authentication (single knowledge base)

## Future Enhancements

- Multilingual support
- Scheduled automatic scraping
- User authentication and personal knowledge bases
- Analytics dashboard
- Mobile app version

##  License

This project is licensed under the MIT License - see the LICENSE file for details.

##  Acknowledgments

- Ashesi University NLP Course
- Ghana Government for open document access
- Anthropic Claude for development assistance
- Ollama team for local LLM infrastructure
- My team members. This couldn't have been possible without you 

## Contact

For questions or collaborations, reach out to purity.moraa@ashesi.edu.gh

---

I really love thissssssss
