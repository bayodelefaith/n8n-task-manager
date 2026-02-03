
# n8n Automation – Django API Integration

This repository contains **n8n workflows** that integrate with a Django REST API (Project 1).
The workflows are designed to be reusable and can be connected to a locally running server
using **ngrok**.



## 📌 Prerequisites

Before getting started, ensure you have:

- A GitHub account
- An n8n Cloud account
- Python 3.10+
- Django & Django REST Framework
- ngrok installed

---

## 🔁 Forking the Projects

You will need to fork **two repositories**:

1. **Project 1 – Django API**
2. **This repository – n8n Workflows**

### Step 1: Fork Project 1 (Django API)
1. Open the Django API repository
2. Click **Fork**
3. Clone your fork locally:
   ```bash
   >>> git clone https://github.com/bayodelefaith/Task-Manager-API.git
   >>> cd project-1-django-api

### Step 2: Fork This n8n Repository

1. Click **Fork** on this repository
2. Clone it:

   ```bash
   >>> git clone https://github.com/bayodelefaith/n8n-task-manager.git
   ```

---

## ▶️ Running the Django Server Locally

### Step 1: Create and activate a virtual environment

```bash
>>> python -m venv venv
>>> source venv/bin/activate  # Windows: venv\Scripts\activate
```

### Step 2: Install dependencies

```bash
>>> pip install -r requirements.txt
```

### Step 3: Run migrations and start the server

```bash
>>> python manage.py migrate
>>> python manage.py runserver
```

Your server will be available at:

```
http://127.0.0.1:8000
```

---

## 🌍 Exposing the Local Server with ngrok

Since n8n Cloud cannot access `localhost`, ngrok is used.

### Step 1: Start ngrok

```bash
>>> ngrok http 8000
```

### Step 2: Copy the public URL

Example:

```
https://abc123.ngrok-free.app
```

This URL will be used in n8n instead of `localhost`.

---

## ⚙️ Importing & Updating n8n Workflows

### Step 1: Import the workflow

1. Log into **n8n Cloud**
2. Go to **Workflows**
3. Click **Import from File**
4. Upload the workflow JSON from this repository

---

### Step 2: Update Webhook & HTTP Request Nodes

After importing the workflow:

* Replace all instances of:

  ```
  http://127.0.0.1:8000
  ```
* With your ngrok URL:

  ```
  https://abc123.ngrok-free.app
  ```

⚠️ **Note:** ngrok URLs change each time you restart it.

---

## 🔐 Credentials Setup in n8n

This repository does **not** include credentials.

In n8n Cloud:

1. Open **Credentials**
2. Create the required credentials (API keys, headers, auth tokens)
3. Attach them to the relevant nodes

Never commit credentials to GitHub.

---

## 🔄 Updating the Workflow for Your Setup

You may need to modify:

* API endpoints
* HTTP methods
* Headers (e.g. Authorization)
* Environment-specific variables

All changes can be made directly in the n8n editor after import.

---

## 🧪 Testing the Automation

1. Ensure Django server is running
2. Ensure ngrok is active
3. Trigger the workflow (webhook / manual trigger)
4. Verify requests reach your local Django API

---

## 🧠 Notes

* These workflows were exported from **n8n Cloud**
* Version control is handled via GitHub using JSON workflow exports
* Best practice is **one workflow per JSON file**

---

## 📄 License

MIT License

---

## ✨ Author

**Bayodele Faith**

Backend Developer | Django | Node.js | n8n Automations
