# Build a Medical Chatbot with LLMs, LangChain, Pinecone, Flask & AWS
This project implements a **Medical Chatbot** powered by **LLMs, LangChain, Pinecone, Flask, and AWS** with CI/CD deployment.

## 🚀 How to Run Locally

### 1. Clone the Repository
```bash
git clone https://github.com/albertomonterom/ai-medical-chatbot.git
cd ai-medical-chatbot
```

### STEP 01 -> Create a virtual environment after opening the repository

```bash
python -m venv medchat
```

```bash
source medchat/bin/activate   # Linux/Mac
medchat\Scripts\activate      # Windows
```

### STEP 02 -> Install the requirements
```bash
pip install -r requirements.txt
```

### Create a `.env` file in the root directory and add your Pinecone & openai credentials as follows:

```ini
PINECONE_API_KEY = "xxxxxxxxxxxxxxxxxxxxxxxxxxxxx"
OPENAI_API_KEY = "xxxxxxxxxxxxxxxxxxxxxxxxxxxxx"
```

```bash
# Run the following command to store embeddings to pinecone
python store_index.py
```

```bash
# Finally run the following command
python app.py
```

Now,
```bash
open up localhost:
```

### Techstack Used:

- Python
- LangChain
- Flask
- GPT
- Pinecone
