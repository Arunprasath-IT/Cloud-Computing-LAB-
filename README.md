# Cloud-Computing-LAB-
CLOUD-COMPUTING-LAB
Installing Google App Engine, setting up a project, and deploying a basic "Hello, World" web app using Python.

# Google App Engine Hello World (Python)

This project demonstrates how to install Google App Engine and deploy a simple "Hello, World" app using Python.

---

## 🛠 Prerequisites

Before you begin, make sure you have the following:

- A **Google Cloud account**: https://cloud.google.com
- A **Google Cloud project** with **billing enabled**

---

## 📥 Step 1: Install Google Cloud SDK

1. Download and install the Cloud SDK:  
   👉 https://cloud.google.com/sdk/docs/install

2. After installation, open your terminal and run:

```bash
gcloud init
Log in with your Google account
Select or create a Google Cloud project
☁️ Step 2: Enable App Engine
Enable App Engine and select your region:

gcloud app create --region=us-central
Replace us-central with your preferred region (e.g., europe-west).

📂 Step 3: Create Hello World App
Directory Structure
hello-world/
├── app.yaml
├── main.py
└── requirements.txt
main.py
from flask import Flask

app = Flask(__name__)

@app.route('/')
def hello():
    return 'Hello, World from Google App Engine!'

if __name__ == '__main__':
    app.run(host='127.0.0.1', port=8080, debug=True)
app.yaml
runtime: python39
entrypoint: gunicorn -b :$PORT main:app

handlers:
- url: /.*
  script: auto
requirements.txt
Flask==2.3.3
gunicorn==21.2.0
🔧 Step 4: Install Python Packages
Run the following in your project folder:

pip install -r requirements.txt
🚀 Step 5: Deploy to App Engine
Deploy your app with:

gcloud app deploy
To open your deployed app in the browser:

gcloud app browse
🧪 Step 6: Run Locally
To test the app locally before deployment:

python main.py
Visit http://127.0.0.1:8080 in your browser.

✅ Done!
You’ve successfully created and deployed a "Hello, World" app using Google App Engine with Python. 🎉
