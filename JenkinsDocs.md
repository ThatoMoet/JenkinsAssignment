# Jenkins Pipeline Documentation

## Overview
This pipeline automates the build, test, and deployment of a simple Java application using Jenkins and Maven.

## Stages

### 1. Build
- Compiles source code using `mvn clean compile`
- Uses OpenJDK 11 and Maven 3.8.6 (pre-configured in Jenkins)

### 2. Test
- Runs JUnit tests with `mvn test`
- Publishes test results in JUnit XML format for visualization
- Pipeline fails immediately if any test fails

### 3. Deploy
- Simulates deployment with echo statements
- In production, this would deploy to servers, containers, or cloud platforms

### 4. Cleanup (Post-build)
- Uses `cleanWs()` to remove all workspace files after execution
- Ensures no leftover artifacts consume disk space

## Requirements
- Jenkins with **Workspace Cleanup Plugin** (for `cleanWs`)
- JDK 11 and Maven 3.8.6 configured in **Global Tool Configuration**
- Git repository access

## Visualization
Jenkins automatically displays:
- Stage status (success/failure)
- Test result trends
- Console logs for each step