# User Manual 

This manual explains how to use the project locally and inside Jenkins.

## 1. Project Description

CILabProject is a Java Maven application that contains:
- A Calculator class (main program code)
- Unit tests written using JUnit
- Jenkins support using Freestyle Jobs and Multibranch Pipelines

The goal is to demonstrate Continuous Integration (CI) by automating:
- Code checkout from GitHub
- Build execution using Maven
- Unit testing
- Pipeline execution through Jenkins

## 2. Running the Project Locally

### Step 1: Clone the Repository
```bash
git clone https://github.com/Aanya2175/CILabProject.git
cd CILabProject
```

### Step 2: Run Maven Build and Tests
```bash
mvn clean test
```

### Expected Result:
- Maven compiles the project
- Unit tests run successfully
- Build output appears in the terminal


## 3. Freestyle Jenkins Job

### Steps to Configure:
1. Open Jenkins Dashboard
2. Click New Item
3. Select Freestyle Project
4. Under Source Code Management, select Git
5. Paste GitHub repository URL
6. Add credentials if needed

Build Triggers (choose any one or both):
- Poll SCM (example: * * * * *)
- GitHub webhook trigger (recommended)

Build Step:
- Invoke top-level Maven targets
  Goals: `clean test`

Post-build Actions:
- Publish JUnit test result report
  Pattern: **/surefire-reports/*.xml
- Archive artifacts (optional)

## 4. Multibranch Pipeline

### Steps to Configure:
1. Open Jenkins Dashboard
2. Click New Item
3. Select Multibranch Pipeline
4. Add GitHub repository source
5. Jenkins automatically scans branches
6. Builds are executed using the Jenkinsfile

Branch Handling:
- main: standard stable build + tests
- feature/*: build + tests for development branches
- release/*: build + tests for release preparation branches

## 5. Scripts Usage

### Windows Build Script
`scripts/build.bat` can be executed in Jenkins or locally to run the Maven build process.

### Deploy Script
`scripts/deploy.sh` is a dummy script included for demonstration purposes.

## 6. Output and Results

After a successful build, Jenkins displays:
- Console output logs
- Unit test reports (JUnit)
- Archived artifacts (if configured)
