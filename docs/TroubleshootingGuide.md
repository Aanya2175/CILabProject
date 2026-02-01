# Troubleshooting Guide

This guide lists common errors and their solutions when running Jenkins and building this Maven project.


## 1. Jenkins is not opening on localhost:8080

### Symptoms
- Browser shows “This site can’t be reached”
- Jenkins service is not running

### Fix
- Restart Jenkins service from Windows Services
- Check if another application is using port 8080


## 2. Maven command not found in Jenkins build

### Symptoms
- Console output shows:
  `mvn is not recognised`

### Fix
1. Go to:
   **Manage Jenkins → Tools**
2. Configure Maven properly
3. Use Jenkins Maven build step instead of a plain shell command


## 3. Git authentication failed

### Symptoms
- Jenkins cannot clone repository
- Error related to credentials

### Fix
- Create GitHub Personal Access Token (PAT)
- Add it in Jenkins:
  **Manage Jenkins → Credentials**
- Use the saved credentials inside job configuration


## 4. Build fails due to Java version mismatch

### Symptoms
- Compilation fails because Java version is unsupported

### Fix
- Set correct JDK in:
  **Manage Jenkins → Tools**
- Ensure the project `pom.xml` matches the installed JDK version


## 5. Tests are not showing in Jenkins

### Symptoms
- Build succeeds but test report is empty

### Fix
- Enable Post-build action:
  **Publish JUnit test report**
- Use test report path:
  `**/surefire-reports/*.xml`


## 6. Multibranch Pipeline is not detecting branches

### Symptoms
- Only one branch shows up or none are discovered

### Fix
- Confirm that `Jenkinsfile` exists at the root of repository
- Install plugin:
  GitHub Branch Source
- Click:
  **Scan Multibranch Pipeline Now**


## 7. Jenkinsfile pipeline failing

### Symptoms
- Pipeline starts but fails at stages

### Fix
- Check console output logs
- Ensure Maven works locally with:
  `mvn clean test`
- Verify correct tools installed in Jenkins (JDK + Maven + Git)
