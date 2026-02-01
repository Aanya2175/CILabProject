# Jenkins Installation Guide (Windows)

## 1. System Requirements
- Windows 10/11 (64-bit)
- Java JDK 11 or later
- Git for Windows
- Maven (for Java build)
- Jenkins LTS (Windows Installer)

## 2. Jenkins Installation (Windows)

1. Download Jenkins **LTS** version.
2. Install Jenkins using the Windows installer.
3. Jenkins usually runs at:

   `http://localhost:8080`

4. When Jenkins starts for the first time, it will ask for an **initial admin password**.

## 3. Initial Jenkins Setup

1. Open Jenkins in a browser:
   `http://localhost:8080`

2. Enter the initial admin password (available in the file shown by Jenkins).

3. Select:
   **Install suggested plugins**

4. Create an **Admin User**:
   - Username
   - Password
   - Full name
   - Email address

5. Confirm Jenkins URL:
   - `http://localhost:8080/`

## 4. Install Required Plugins

Go to:

**Manage Jenkins → Plugins**

Install these plugins (if not already installed):
- Pipeline
- Git
- GitHub Integration / GitHub Branch Source
- Maven Integration
- JUnit Plugin

## 5. Global Tool Configuration

Go to:

**Manage Jenkins → Tools**

Configure the following:

### JDK
- Add a JDK installation (JDK 11+ recommended)
- Ensure `JAVA_HOME` is configured correctly

### Git
- Ensure Git path is detected correctly

### Maven
- Add Maven installation (or use system Maven)
- Ensure Maven is available in PATH if required

## 6. Configure System Settings (Optional but Recommended)

Go to:

**Manage Jenkins → System**

Common configurations:
- System message (optional)
- Jenkins URL (already set in setup wizard)
- SMTP settings (optional for notifications)

## 7. Verify Jenkins is Working

1. From the Jenkins dashboard, create a sample job
2. Run a build
3. Ensure console output shows successful execution

Jenkins is now ready for CI pipelines.
