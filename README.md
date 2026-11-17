# Docker Full-Stack Assignment - DevOps

This repository contains my completed practical assignment for the **TuteDude DevOps** module. It demonstrates containerizing a multi-service full-stack application—consisting of a **Node.js/Express** frontend and a **Python/Flask** backend—using Docker and Docker Compose, with images published to Docker Hub.

## 📌 Assignment Objectives
Containerize and orchestrate a decoupled web application across four key steps:
1. **Frontend Service (Node.js & Express)**: Render a Student Registration Form (`EJS`) capturing Student Name, Email Address, and Course Name, and forward submissions to the backend API.
2. **Backend Service (Python & Flask)**: Expose a `/submit` POST endpoint that receives JSON payloads, validates input fields, and returns a success or error response.
3. **Multi-Container Orchestration**: Define separate `Dockerfile` configurations for both services and link them over a shared bridge network using `docker-compose.yaml`.
4. **Registry & Version Control**: Build, tag, and push both container images to Docker Hub and publish clean project code to GitHub.

---

## 🛠️ Tech Stack & Docker Images
* **Frontend:** Node.js 20 (`node:20-alpine`), Express.js, EJS, CSS
* **Backend:** Python 3.12 (`python:3.12-slim`), Flask
* **Containerization:** Docker, Docker Compose
* **Docker Hub Images:**
  * Frontend: `priyanshusaxenapriyanshu/docker-frontend:1.0`
  * Backend: `priyanshusaxenapriyanshu/flask-backend:1.0`

---

## 🚀 Setup & Running the Application

### 1. Clone the Repository
```bash
git clone https://github.com
cd Docker-Fullstack-Assignment
```

### 2. Build and Start Containers via Docker Compose
```bash
docker compose up -d --build
```
* **Frontend UI:** Accessible at `http://localhost:3000`
* **Backend API:** Running internally and exposed on `http://localhost:5000`

### 3. Verify Running Containers & Logs
```bash
docker ps
docker compose logs
```

### 4. Stop and Remove Containers
```bash
docker compose down
```

---

## 📂 Repository Structure
```text
Docker-Fullstack-Assignment/
├── backend/
│   ├── app.py              # Flask server with /submit POST JSON endpoint
│   ├── Dockerfile          # Backend container build instructions
│   └── requirements.txt    # Python dependencies
├── frontend/
│   ├── public/
│   │   └── style.css       # Frontend stylesheet
│   ├── views/
│   │   └── index.ejs       # Student registration form template
│   ├── Dockerfile          # Frontend container build instructions
│   ├── package.json        # Node.js dependencies
│   └── server.js           # Express server forwarding requests to Flask
├── .gitignore              # Excludes node_modules and local config files
├── docker-compose.yaml     # Multi-container network and service configuration
└── README.md               # Project documentation
```
