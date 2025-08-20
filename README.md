# Build a Medical Chatbot with LLMs, LangChain, Pinecone, Flask & AWS
This project implements a **Medical Chatbot** powered by **LLMs, LangChain, Pinecone, Flask, and AWS** with CI/CD deployment.

## 🚀 How to Run Locally

### 1. Clone the Repository
```bash
git clone https://github.com/albertomonterom/ai-medical-chatbot.git
cd ai-medical-chatbot
```

### 2. Create a virtual environment

```bash
python -m venv medchat
```


### Activate it

```bash
source medchat/bin/activate   # Linux/Mac
medchat\Scripts\activate      # Windows
```

### 3. Install Requirements
```bash
pip install -r requirements.txt
```

### 4. Configure Environment Variables
Create a `.env` file in the root directory and add your Pinecone & openai credentials as follows:

```ini
PINECONE_API_KEY = "xxxxxxxxxxxxxxxxxxxxxxxxxxxxx"
OPENAI_API_KEY = "xxxxxxxxxxxxxxxxxxxxxxxxxxxxx"
```

### 5. Store Embeddings to Pinecone

```bash
# Run the following command to store embeddings to pinecone
python store_index.py
```


### 6. Run the Application

```bash
# Finally run the following command
python app.py
```

Open in your browser:
```bash
open up localhost:
```

### Techstack Used:

- Python
- LangChain
- OpenAI GPT
- Pinecone
- Flask
- AWS
