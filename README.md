# SonarQube_POC
POC to set up SonarQube locally using Docker, analyze a sample project, and view results on the SonarQube dashboard

## Prerequisites
- Java 11+
- Docker & Docker Compose
- SonarScanner

## Start SonarQube with Docker

Create a `docker-compose.yml` file (already provided) and run:
```
docker-compose up -d
```

## Analyze the Java Sample Project

Clone the example Maven project:
```
git clone https://github.com/SonarSource/sonar-scanning-examples.git
cd sonar-scanning-examples/sonarqube-scanner-maven/
```

## Generate a SonarQube token:

Go to My Account > Security > Generate Token in the SonarQube UI.

Run the analysis:
```
mvn clean verify sonar:sonar \
  -Dsonar.projectKey=sample-java \
  -Dsonar.host.url=http://localhost:9000 \
  -Dsonar.login=<YOUR_TOKEN>
```

## View Results
Go to http://localhost:9000 and check the project dashboard.

You should see the sample-java project with metrics like:
Vulnerabilities
Bugs
Code Smells
Security Hotspots



<img width="1470" alt="image" src="https://github.com/user-attachments/assets/8d2450a7-c964-4874-873d-a404c33183ec" />

