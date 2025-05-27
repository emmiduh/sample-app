# Sample App (Go)

This repository contains a simple Go application contains a sample Go web application designed to demonstrate a full DevOps workflow using **Google Cloud Build**, **Cloud Deploy**, and **GitHub Triggers**..

---

## 🚀 Project Overviewand Structure

This project is part of the **"Implement DevOps Workflow in Google Cloud"** challenge.  
It focuses on delivering a containerized Go application from **source to production** using automated pipelines.

sample-app/

├── main.go # Core Go application

├── Dockerfile # Container build file

├── cloudbuild.yaml # Cloud Build pipeline for production

├── cloudbuild-dev.yaml # Cloud Build pipeline for development

├── dev/ # Development deployment configs

├── prod/ # Production deployment configs

└── README.md # Project info and instructions

---

## 🛠️ Tech Stack

- **Language**: [Go](https://golang.org/), [Python](https://python.org/)
- **CI/CD**: [Google Cloud Build](https://cloud.google.com/build), [GitHub Actions](https://github.com/features/actions)
- **Artifact Storage**: [Artifact Registry](https://cloud.google.com/artifact-registry)
- **Deployment Targets**: [Cloud Run](https://cloud.google.com/run) or [GKE](https://cloud.google.com/kubernetes-engine)

---


## 🚀 Deployment Workflow

This project uses the following pipeline:

1. **Push to GitHub**
2. **Cloud Build Trigger** starts automatically
3. **Container is built using Dockerfile**
4. **Cloud Deploy** pushes app to  GKE
5. **Promotion to production** or rollback as needed

## 📦 Cloud Build Triggers

- `cloudbuild-dev.yaml`: for development environment
- `cloudbuild.yaml`: for production environment

Each trigger is connected to specific branches (`main`, `dev`, etc.).

## 🛠️ Setup Instructions

To use this repository:

1. Fork or clone this repo into your GitHub account
2. Connect the repo to Google Cloud Build triggers
3. Deploy the app using:
   - `gcloud builds submit --config=cloudbuild-dev.yaml .` (for dev)
   - `gcloud builds submit --config=cloudbuild.yaml .` (for prod)
4. View and manage deployments in **Google Cloud**

## 🧪 Rollback Steps

If production has an issue:
- Use **Cloud Build History UI** to rollback to a previous release version
- Or run a manual rollback using `kubectl rollout undo`



