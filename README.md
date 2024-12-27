# GitHub Actions Practice Repository

This repository contains a basic GitHub Actions workflow that demonstrates key CI/CD (Continuous Integration/Continuous Deployment) practices. The workflow includes steps for testing and deploying a Node.js project.

## Workflow Description

### **Workflow Name:** `Test`

The workflow is triggered on:
- Push events to the repository.
- Manual execution via the `workflow_dispatch` event.

### **Jobs Included:**

#### **1. Test**
This job ensures the project passes all tests before proceeding to deployment.
- **Runs-on:** `ubuntu-24.04`
- **Steps:**
  1. **Checkout Code:** Pulls the latest version of the repository.
     - Uses: `actions/checkout@v3`
  2. **Set Up Node.js:** Configures Node.js version `18` for the environment.
     - Uses: `actions/setup-node@v3`
  3. **Install Dependencies:** Installs all necessary project dependencies.
     - Command: `npm ci`
  4. **Run Tests:** Executes the project's test suite to ensure functionality.
     - Command: `npm test`

#### **2. Deploy**
This job builds and deploys the project, but only after the `test` job is successful.
- **Runs-on:** `ubuntu-24.04`
- **Depends-on:** `test`
- **Steps:**
  1. **Checkout Code:** Pulls the latest version of the repository.
     - Uses: `actions/checkout@v3`
  2. **Set Up Node.js:** Configures Node.js version `18` for the environment.
     - Uses: `actions/setup-node@v3`
  3. **Install Dependencies:** Installs all necessary project dependencies.
     - Command: `npm ci`
  4. **Build Project:** Builds the project using the defined build script.
     - Command: `npm run build`
  5. **Deploy Project:** Simulates a deployment process with a placeholder command.
     - Command: `echo "Deploying..."`

## Purpose of the Repository

This repository serves as a hands-on example of setting up a GitHub Actions workflow for:
- Automating testing and deployment processes.
- Practicing CI/CD workflows with Node.js projects.

## How to Use

1. Clone this repository.
2. Modify the workflow file `.github/workflows/test.yml` as needed for your project.
3. Push your changes to trigger the workflow.

## Key Learnings

- Setting up workflows for testing and deployment.
- Configuring GitHub Actions with Node.js projects.
- Using multiple jobs with dependencies.

Feel free to customize this workflow for your own projects!
