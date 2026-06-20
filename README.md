# DevOps CI/CD Pipeline 🚀

A production-style CI/CD pipeline using **GitHub Actions**, **Docker**, and **Flask** — automatically builds and pushes a Docker image to Docker Hub on every push to `main`.

## Project Structure

```
Devops-cicd-project/
├── app.py                        ← Flask web application
├── Dockerfile                    ← Docker image definition
├── requirements.txt              ← Python dependencies
├── .github/
│   └── workflows/
│       └── main.yml              ← GitHub Actions CI pipeline
└── README.md
```

## Pipeline Flow

```
Push to main
    │
    ▼
GitHub Actions triggers
    │
    ├── Checkout code
    ├── Set up Python 3.10
    ├── Install dependencies
    ├── Run app smoke test
    ├── Login to Docker Hub
    └── Build & Push Docker image → Docker Hub
```

## Local Setup

```bash
# Run directly
pip install -r requirements.txt
python app.py

# Run with Docker
docker build -t devops-app .
docker run -p 5000:5000 devops-app
```

Visit `http://localhost:5000`

## CI/CD Secrets Required

Set these in **GitHub → Settings → Secrets and variables → Actions**:

| Secret            | Description                    |
|-------------------|--------------------------------|
| `DOCKER_USERNAME` | Your Docker Hub username       |
| `DOCKER_PASSWORD` | Your Docker Hub access token   |

## Tech Stack

| Tool            | Purpose                        |
|-----------------|--------------------------------|
| Flask           | Lightweight web app            |
| Docker          | Containerisation               |
| GitHub Actions  | CI/CD automation               |
| Docker Hub      | Container registry             |

## RISE Internship

Built as part of the RISE Internship (Tamizha Skills) — CI/CD Pipeline Automation track.
