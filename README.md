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
- Java 21
- Maven
- Git

### Build and Test
```bash
mvn clean test
