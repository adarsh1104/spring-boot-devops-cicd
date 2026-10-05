\# Employee Service – DevOps CI/CD Project



A containerized Spring Boot Employee Service deployed using a DevOps CI/CD workflow with Docker, Jenkins, Kubernetes and AWS.



\## Architecture / Technology Stack



\- Java 17

\- Spring Boot

\- Spring Data JPA

\- MySQL

\- Maven

\- Docker

\- Jenkins

\- Kubernetes

\- Amazon ECR

\- Amazon EKS

\- AWS Application Load Balancer

\- Prometheus

\- Grafana

\- Elasticsearch

\- Kibana

\- Filebeat



\## CI/CD Pipeline



The Jenkins pipeline covers the application delivery workflow:



1\. Checkout source code from GitHub

2\. Build the Spring Boot application

3\. Run tests

4\. Build the Docker image

5\. Push the Docker image to Amazon ECR

6\. Validate Kubernetes resources

7\. Support controlled deployment to EKS



Docker images are tagged using Jenkins build numbers for traceability.



Example:



`employee-service:build-11`



\## Containerization



The application is packaged as a Docker image using Java 17.



The runtime image uses:



`eclipse-temurin:17-jre`



The JRE-based image reduces the runtime footprint compared with using a full JDK image.



\## Kubernetes



The application is deployed to Kubernetes using:



\- Deployment

\- Service

\- Ingress

\- Liveness probe

\- Readiness probe



The application is exposed through an AWS Application Load Balancer using Kubernetes Ingress.



\## Monitoring and Logging



The project also includes Kubernetes manifests for monitoring and logging components:



\- Prometheus

\- Grafana

\- Elasticsearch

\- Kibana

\- Filebeat



These components provide a foundation for application monitoring, metrics visualization and centralized log collection.



\## AWS



The project uses AWS services including:



\- Amazon EKS

\- Amazon ECR

\- Application Load Balancer

\- IAM



The container image is stored in Amazon ECR and can be deployed to the EKS environment through the CI/CD workflow.



\## Repository Structure



```text

.

├── k8s/

│   ├── employee-deployment.yaml

│   ├── employee-service.yaml

│   ├── employee-ingress.yaml

│   └── monitoring manifests

├── src/

├── Dockerfile

├── Jenkinsfile

├── docker-compose.yml

├── pom.xml

└── README.md

