# LLM Chatbot Application

A conversational AI chatbot application built with Flask and HuggingFace Transformers, featuring a clean web interface for interactive conversations.

## Overview

This project demonstrates the integration of a Large Language Model (LLM) into a web application. It uses Facebook's BlenderBot model to create natural conversations with users through a simple, elegant web interface.

## Features

- **Conversational AI**: Powered by Facebook's BlenderBot-400M-distill model
- **Conversation History**: Maintains context across multiple exchanges
- **Real-time Responses**: Async communication between frontend and backend
- **Responsive UI**: Clean, user-friendly chat interface
- **Docker Support**: Containerized deployment ready

## Technologies Used

### Backend

- **Flask**: Lightweight web framework for Python
- **Flask-CORS**: Cross-Origin Resource Sharing support
- **Transformers**: HuggingFace library for pre-trained language models
- **PyTorch**: Deep learning framework for model inference

### Frontend

- **HTML5/CSS3**: Modern web standards
- **JavaScript (ES6+)**: Async/await for API communication
- **Fetch API**: HTTP requests to the backend

### AI Model

- **BlenderBot-400M-distill**: Facebook's conversational AI model optimized for dialogue

## Project Structure

```
LLM_application_chatbot/
├── app.py                 # Flask backend application
├── requirements.txt       # Python dependencies
├── Dockerfile            # Container configuration
├── templates/
│   └── index.html        # Main HTML template
└── static/
    ├── script.js         # Frontend JavaScript logic
    └── css/
        └── style.css     # Styling
```

## Setup Instructions

### Prerequisites

- Python 3.9 or higher
- pip package manager

### Local Development Setup

1. **Clone the repository**

   ```bash
   git clone <repository-url>
   cd LLM_application_chatbot
   ```

2. **Create a virtual environment**

   ```bash
   python3 -m venv .venv
   ```

3. **Activate the virtual environment**

   ```bash
   # macOS/Linux
   source .venv/bin/activate

   # Windows
   .venv\Scripts\activate
   ```

4. **Install dependencies**

   ```bash
   pip install -r requirements.txt
   ```

5. **Run the application**

   ```bash
   python app.py
   ```

6. **Access the chatbot**
   - Open your browser and navigate to `http://127.0.0.1:5000`

### Docker Deployment

1. **Build the Docker image**

   ```bash
   docker build -t llm-chatbot .
   ```

2. **Run the container**

   ```bash
   docker run -p 5000:5000 llm-chatbot
   ```

3. **Access the application**
   - Navigate to `http://localhost:5000`

## How It Works

### Backend Flow

1. Flask server initializes the BlenderBot model on startup
2. User sends a message via POST request to `/chatbot` endpoint
3. The message is combined with conversation history
4. The input is tokenized and passed to the model
5. Model generates a response based on context
6. Response is decoded and sent back to the frontend
7. Conversation history is updated with the exchange

### Frontend Flow

1. User types a message and submits the form
2. JavaScript captures the input and displays it in the chat
3. A loading animation appears while waiting for the response
4. Fetch API sends POST request to the backend
5. Response is received and displayed in the chat interface
6. Chat history is maintained in the DOM

## Learning Objectives

This project demonstrates:

- **LLM Integration**: How to integrate pre-trained language models into web applications
- **API Design**: Creating RESTful endpoints for AI services
- **State Management**: Maintaining conversation context across requests
- **Async Programming**: Handling asynchronous operations in JavaScript
- **Virtual Environments**: Python dependency isolation and management
- **Containerization**: Deploying applications with Docker

## Dependencies

Key packages (see `requirements.txt` for versions):

- `Flask`: Web framework
- `Flask-Cors`: CORS handling
- `torch`: PyTorch for model inference
- `torchvision`: Computer vision utilities
- `torchaudio`: Audio processing utilities
- `transformers`: HuggingFace model library

## Performance Considerations

- **Model Loading**: The BlenderBot model is loaded once at startup (not per request)
- **Memory Usage**: The 400M-distill variant is optimized for lower memory footprint
- **Response Time**: Depends on hardware; GPU acceleration recommended for production
- **Conversation History**: Stored in memory; consider database for persistence

## Future Improvements

- [ ] Add conversation history persistence (database)
- [ ] Implement user sessions for multi-user support
- [ ] Add model selection/switching capability
- [ ] Implement streaming responses for longer outputs
- [ ] Add conversation export functionality
- [ ] Improve error handling and user feedback
- [ ] Add conversation reset button
- [ ] Implement rate limiting

## Troubleshooting

**Model download takes too long**

- The first run downloads ~1.5GB model files
- Subsequent runs use cached models

**Out of memory errors**

- Consider using a smaller model variant
- Limit conversation history length
- Use CPU inference for development

**CORS errors**

- Ensure Flask-CORS is installed
- Check that the frontend URL matches the backend configuration

## License

This project is for educational purposes.

## Acknowledgments

- Facebook AI Research for the BlenderBot model
- HuggingFace for the Transformers library
- Original template by J.C. Chen
