# sit737-2025-prac5D
# sit737-2025-prac5D
# 🧮 Calculator Microservice

This project is a simple calculator microservice built using **Node.js**, **Express**, and **Winston** for logging. It supports basic and advanced operations like addition, subtraction, multiplication, division, exponentiation, square root, and modulo.

---

## 🔧 Tech Stack

- Node.js
- Express.js
- Winston (Logging)
- Docker
- curl (for API testing)
- Google Cloud Platform (GCP)

---

## 📁 Project Structure
sit737-2025-prac4p/
├── Dockerfile
├── docker-compose.yml
├── index.js
├── package.json
├── logs/
│   ├── combined.log
│   └── error.log
---

## 🚀 Setup Instructions

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/sit737-2025-prac4p.git
cd sit737-2025-prac4p
2. Build the Docker Image :docker build -t rayudu1889/calculator-microservice .
3. Run the Docker Container: docker run -p 8080:8080 rayudu1889/calculator-microservice
4. Test API with curl:
curl -X POST "http://localhost:8080/add" \
  -H "Content-Type: application/json" \
  -d '{"num1": 10, "num2": 5}'
   Supported Endpoints;

🧮 Calculator Microservice – API Endpoints
Method	Endpoint	Description
POST	/add	Adds two numbers
POST	/subtract	Subtracts two numbers
POST	/multiply	Multiplies two numbers
POST	/divide	Divides two numbers
POST	/exponentiate	Raises num1 to the power of num2
POST	/sqrt	Takes the square root of num1
POST	/modulo	Finds the remainder of division
GET	/operations	Lists all available operations

📜 Logging

Logs are handled by Winston and written to:
	•	logs/error.log → Error logs
	•	logs/combined.log → All logs (including info and errors)

You’ll also see logs in the terminal when the server is running.

☁️ Google Cloud Platform (GCP) Deployment

🔧 Tools Used
	•	Google Cloud Run
	•	Google Container Registry (GCR)
	•	Google Kubernetes Engine (GKE) (Optional, if required)
	•	IAM & Admin (Permissions)
	•	Google Cloud Console / gcloud CLI

🧭 Steps Followed

1. Enable Required APIs

Make sure these APIs are enabled:
	•	Cloud Run API
	•	Cloud Build API
	•	Artifact Registry or Container Registry
	•	Kubernetes Engine API (if using GKE)

Authenticate GCP CLI
gcloud auth login
gcloud config set project <your-project-id>

. Build & Push Docker Image to GCR

gcloud builds submit --tag gcr.io/<project-id>/calculator-microservice

4. Deploy to Cloud Run
gcloud run deploy calculator-microservice \
  --image gcr.io/<project-id>/calculator-microservice \
  --platform managed \
  --region us-central1 \
  --allow-unauthenticated
