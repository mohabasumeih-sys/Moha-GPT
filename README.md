# Moha-GPT

Moha-GPT is a local conversational AI application built with **Streamlit**, **Ollama**, and **MongoDB**. It provides a user-friendly chat interface that connects to locally hosted large language models, allowing you to have private and secure conversations, while preserving your chat history in a database.

## Features

- **Local LLMs via Ollama**: Supports models such as `gemma2:2b`, `llama3:latest`, and `mistral:7b`.
- **Chat History**: Automatically saves and loads previous conversations using MongoDB.
- **Chat Titles**: Automatically generates a relevant title for newly created chats.
- **Web UI**: Built entirely with Streamlit for a clean, responsive web chat experience.

## Prerequisites

- **Python 3.10+**
- **MongoDB**: For storing conversation history locally (e.g. running on port `27017`).
- **Ollama**: For serving and communicating with local LLMs (e.g. running on port `11434`).

## Installation & Setup

1. **Clone the repository**:
   ```bash
   git clone https://github.com/mohabasumeih-sys/Moha-GPT.git
   cd Moha-GPT
   ```

2. **Set up a virtual environment** (recommended):
   ```bash
   python -m venv .venv
   source .venv/bin/activate  # On Windows use `.venv\Scripts\activate`
   ```

3. **Install dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

4. **Environment Variables**:
   Create a `.env` file in the root directory (you can copy from `env_template.txt`) and add the following:
   ```env
   MONGO_DB_URL="mongodb://localhost:27017/"
   MONGO_DB_NAME="Moha_GPT"
   OLLAMA_URL="http://localhost:11434"
   OLLAMA_MODELS="gemma2:2b,llama3:latest,mistral:7b"
   ```

5. **Dependencies Services (Ollama & MongoDB)**:
   Make sure you have MongoDB running locally or inside a Docker container.
   Start Ollama and pull your desired models as configured in the `.env`:
   ```bash
   ollama pull gemma2:2b
   ollama pull llama3:latest
   ollama pull mistral:7b
   ```

6. **Start the application**:
   ```bash
   streamlit run main.py
   ```
   Access the app in your browser at `http://localhost:8501`.

## AWS EC2 Deployment
Included in the repository is a `deploy_ec2.txt` outlining useful commands for deploying Moha-GPT into an AWS EC2 Ubuntu Instance. It includes instructions for setting up Dockerized containers for MongoDB and pulling models using the Ollama Docker container.

## License
Please refer to the `LICENSE` file for the details of the open-source license.
