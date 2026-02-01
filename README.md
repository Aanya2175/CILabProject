# CILabProject

This repository contains a Java Maven project integrated with Jenkins for Continuous Integration.

## Repository Structure
- `src/main/java/com/muj/ci/Calculator.java` : Main source code
- `src/test/java/com/muj/ci/CalculatorTest.java` : Unit tests (JUnit)
- `src/main/resources/` : Resources folder
- `pom.xml` : Maven build configuration
- `Jenkinsfile` : Multibranch pipeline definition
- `docker/Dockerfile` : Docker packaging file
- `scripts/build.bat` : Build script for Windows
- `scripts/deploy.sh` : Dummy deploy script
- `docs/` : Installation guide, user manual, troubleshooting

## How to Run Locally
### Requirements
- Java (JDK 11+ recommended, Java 21 supported)
- Maven
- Git
- Jenkins LTS

### 1) Clone Repository
```bash
git clone https://github.com/Aanya2175/CILabProject.git
cd CILabProject
```

### 2) Build and Run Tests
```bash
mvn clean test
```

## Jenkins Setup Summary

### Job 1: Freestyle Project
- GitHub configured as SCM
- Triggers: Poll SCM and/or GitHub webhook
- Build steps: `mvn clean test` + optional script execution from `/scripts`
- Post-build: Archive artifacts + Publish JUnit test reports

### Job 2: Multibranch Pipeline
- Automatic branch discovery from GitHub
- Pipeline execution using `Jenkinsfile`
- Branch-specific behaviour for:
  - `main`
  - `feature/*`
  - `release/*`

## Documentation
- [Installation Guide](docs/InstallationGuide.md)
- [User Manual](docs//UserManual.md)
- [Troubleshooting Guide](docs/TroubleshootingGuide.md)

