# smaitic-devops-assignment
# Career Objective
A passionate DevOps Engineer with hands-on experience in Kubernetes, CI/CD pipelines, and cloud infrastructure. Seeking to leverage my skills in container orchestration, automation, and monitoring to deliver reliable, scalable, and secure production systems.

---

# Production-Ready Microservice

## Overview
Deploying a stateless Node.js API to AWS EKS using Jenkins CI/CD, Prometheus/Grafana monitoring, and ELK stack logging.

## Architectural Decisions

| Area | Decision | Reason |
|------|----------|--------|
| Docker | Multi-stage build | Smaller image, no dev tools in production |
| Base Image | node:18-alpine | Lightweight and secure |
| Security | Non-root user | Reduces attack surface |
| Kubernetes | AWS EKS | Managed scalable cluster |
| CI/CD | Jenkins | Pipeline automation |
| Monitoring | Prometheus + Grafana | Metrics and alerting |
| Logging | ELK Stack | Centralized log management |

## Assumptions
- App listens on port 3000
- npm run build compiles the app
- npm run start starts the production server
- AWS EKS cluster is already provisioned
- Docker Hub used as container registry

## Setup Instructions

### Build Docker Image
```bash
docker build -t your-dockerhub-username/node-api:latest .
docker push your-dockerhub-username/node-api:latest
