# Spring Boot DevOps CI/CD Project

A containerized Spring Boot Employee Service deployed using a complete DevOps workflow with Docker, Jenkins, Kubernetes and AWS.

The project demonstrates application containerization, CI/CD automation, Kubernetes deployment on Amazon EKS, Amazon ECR image management, AWS Application Load Balancer integration, and an observability stack using Prometheus, Grafana and the ELK stack.

---

## 🚀 Project Overview

This project takes a Spring Boot Employee Service from source code to a containerized application deployed on Kubernetes.

### Workflow

GitHub
↓
Jenkins CI/CD
↓
Maven Build & Test
↓
Docker Image
↓
Amazon ECR
↓
Amazon EKS
↓
Kubernetes Service
↓
AWS Application Load Balancer
↓
Application

Monitoring and logging are supported through:

Prometheus → Grafana

Application Logs → Filebeat → Elasticsearch → Kibana

---

## 🏗️ Architecture / Technology Stack

### Application

- Java 17
- Spring Boot
- Spring Data JPA
- MySQL
- Maven

### Containerization

- Docker
- Dockerfile

### CI/CD

- Jenkins
- Jenkins Pipeline
- GitHub

### Container Registry

- Amazon ECR

### Kubernetes

- Kubernetes
- Amazon EKS
- Kubernetes Deployments
- Kubernetes Services
- Kubernetes Ingress
- Kubernetes Configurations

### AWS

- Amazon EKS
- Amazon ECR
- AWS Application Load Balancer
- AWS Load Balancer integration

### Monitoring

- Prometheus
- Grafana

### Logging

- Elasticsearch
- Kibana
- Filebeat

---

## 🔄 CI/CD Pipeline

The Jenkins pipeline automates the application delivery workflow.

### Pipeline Flow

1. Checkout source code from GitHub
2. Build the Spring Boot application using Maven
3. Run application tests
4. Build the Docker image
5. Tag the Docker image
6. Authenticate with Amazon ECR
7. Push the Docker image to Amazon ECR
8. Deploy/update the application on Kubernetes when deployment is enabled
9. Verify the Kubernetes deployment

The pipeline also includes deployment controls to avoid unnecessary changes to the existing EKS workload.

---

## 🐳 Docker

The application is packaged as a Docker image using a JRE-based runtime image.

The Dockerfile separates application build/runtime concerns and provides a containerized runtime for the Spring Boot service.

---

## ☸️ Kubernetes / Amazon EKS

The application is deployed to Amazon EKS using Kubernetes manifests.

The repository contains manifests for:

- Employee Service Deployment
- Employee Service
- Application Ingress
- EKS configuration
- Prometheus
- Grafana
- Elasticsearch
- Kibana
- Filebeat
- Monitoring namespace
- Prometheus RBAC
- Prometheus configuration
- Persistent storage

---

## 📊 Monitoring

Prometheus is configured as the metrics collection component.

Grafana is included as the visualization layer for monitoring application/infrastructure metrics.

### Monitoring Flow

Application / Kubernetes
↓
Prometheus
↓
Grafana

---

## 📝 Centralized Logging

The project also contains an ELK-based logging stack.

### Logging Flow

Application Logs
↓
Filebeat
↓
Elasticsearch
↓
Kibana

This provides a foundation for centralized log collection, storage and visualization.

---

## 📁 Repository Structure

```text
.
├── eks/
│   └── employee-eks.yaml
│
├── k8s/
│   ├── employee-deployment.yaml
│   ├── employee-service.yaml
│   ├── employee-ingress.yaml
│   ├── monitoring-namespace.yaml
│   ├── prometheus-*.yaml
│   ├── grafana-*.yaml
│   ├── elasticsearch.yaml
│   ├── kibana.yaml
│   └── filebeat.yaml
│
├── src/
│   └── main/
│
├── Dockerfile
├── Jenkinsfile
├── docker-compose.yml
├── pom.xml
└── README.md