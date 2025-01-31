# Streaming Chat API with FastAPI and LangChain

## Overview
This project is a FastAPI-based streaming chat API that integrates with OpenAI's GPT-3.5-turbo model using LangChain. It enables real-time AI-generated responses via server-sent events (SSE), making it suitable for applications requiring low-latency AI interactions.

## Features
- **FastAPI Backend**: A lightweight, high-performance web framework.
- **Streaming Responses**: Uses `StreamingResponse` for real-time token streaming.
- **LangChain Integration**: Utilizes `ChatOpenAI` for intelligent responses.
- **CORS Support**: Allows cross-origin requests for flexibility.
- **Environment-Based Configuration**: Uses `.env` files to store API keys securely.

## Requirements
- Python 3.8+
- OpenAI API Key

## Installation
1. Clone this repository:
   ```sh
   git clone https://github.com/yourusername/yourproject.git
   cd yourproject
   ```
2. Create and activate a virtual environment:
   ```sh
   python -m venv venv
   source venv/bin/activate  # On Windows use `venv\Scripts\activate`
   ```
3. Install dependencies:
   ```sh
   pip install -r requirements.txt
   ```
4. Create a `.env` file and add your OpenAI API key:
   ```sh
   echo "OPENAI_API_KEY=your_api_key_here" > .env
   ```

## Usage
### Running the Server
Start the FastAPI server with:
```sh
uvicorn main:app --host localhost --port 8000 --reload
```

### Sending Requests
Use a `POST` request to `/stream_chat/` with JSON input:
```json
{
  "content": "Hello, how are you?"
}
```

### Example cURL Request
```sh
curl -X POST "http://localhost:8000/stream_chat/" \
     -H "Content-Type: application/json" \
     -d '{"content": "Tell me a joke."}'
```

## API Endpoint
### `POST /stream_chat/`
- **Request Body:** `{ "content": "message_text" }`
- **Response:** A streamed response with AI-generated text.


