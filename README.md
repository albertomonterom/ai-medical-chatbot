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

Activate it

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

# ☁️ AWS Deployment with CI/CD (GitHub Actions)

### 1. Login to AWS Console

### 2. Create IAM User for Deployment
Grant only the necessary permissions (principle of least privilege):
- AmazonEC2FullAccess → to manage virtual machines (EC2).
- AmazonEC2ContainerRegistryFullAccess → to push/pull Docker images (ECR).

### 3. Create a ECR Repository
Store your Docker image in AWS Elastic Container Registry (ECR).
Save the URI generated, for example:
```bash
<your-account-id>.dkr.ecr.<region>.amazonaws.com/<repo-name>
```

### 4. Lauch an EC3 Instance (Ubuntu recommended)
This instance will run your chatbot in the cloud.

### 5. Install Docker in EC2

```bash
# optional
sudo apt-get update -y
sudo apt-get upgrade -y

# required
curl -fsSL https://get.docker.com -o get-docker.sh
sudo sh get-docker.sh
sudo usermod -aG docker ubuntu
newgrp docker
```

### 6. Configure EC2 as a Self-Hosted Runner
In GitHub:
```bash
Settings > Actions > Runners > New self-hosted runner
```
Choose OS, then run the commands provided inside your EC2.

### 7. Setup GitHub Secrets
In your repo, go to:
Create a `.env` file in the root directory and add your Pinecone & openai credentials as follows:

```bash
Settings > Secrets and variables > Actions
```

Add the following:
```bash
AWS_ACCESS_KEY_ID
AWS_SECRET_ACCESS_KEY
AWS_DEFAULT_REGION
ECR_REPO
PINECONE_API_KEY
OPENAI_API_KEY
```

### ⚙️ CI/CD Pipeline Flow
1. Build Docker image of the chatbot.
2. Push the Docker image to ECR.
3. Launch/Update EC2 instance.
4. Pull the Docker image from ECR to EC2.
5. Run the chatbot container on EC2.


### 🛠️ Techstack Used:
- Python
- LangChain
- OpenAI GPT
- Pinecone
- Flask
- AWS (EC2, ECR, IAM)
- GitHub Actions (CI/CD)