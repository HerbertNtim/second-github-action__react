# GitHub Actions Practice Repository

![GitHub Actions](https://img.shields.io/badge/-GitHub%20Actions-2088FF?style=flat&logo=github-actions&logoColor=white)

This repository contains a basic **GitHub Actions** workflow that demonstrates key CI/CD (Continuous Integration/Continuous Deployment) practices. The workflow includes steps for testing and deploying a Node.js project.

## Workflow Description

### 🛠 **Workflow Name:** `Test`

The workflow is triggered on:
- **Push events** to the repository.
- **Manual execution** via the `workflow_dispatch` event.

### 🚀 **Jobs Included:**

#### 1. **Test**
This job ensures the project passes all tests before proceeding to deployment.

- **Runs-on:** `ubuntu-24.04`
- **Steps:**
  - 📥 **Checkout Code:** Pulls the latest version of the repository.
    - Uses: `actions/checkout@v3`
  - 🖥 **Set Up Node.js:** Configures Node.js version `18` for the environment.
    - Uses: `actions/setup-node@v3`
  - 📦 **Install Dependencies:** Installs all necessary project dependencies.
    - Command: `npm ci`
  - ✅ **Run Tests:** Executes the project's test suite to ensure functionality.
    - Command: `npm test`

#### 2. **Deploy**
This job builds and deploys the project, but only after the `test` job is successful.

- **Runs-on:** `ubuntu-24.04`
- **Depends-on:** `test`
- **Steps:**
  - 📥 **Checkout Code:** Pulls the latest version of the repository.
    - Uses: `actions/checkout@v3`
  - 🖥 **Set Up Node.js:** Configures Node.js version `18` for the environment.
    - Uses: `actions/setup-node@v3`
  - 📦 **Install Dependencies:** Installs all necessary project dependencies.
    - Command: `npm ci`
  - 🛠 **Build Project:** Builds the project using the defined build script.
    - Command: `npm run build`
  - 🚀 **Deploy Project:** Simulates a deployment process with a placeholder command.
    - Command: `echo "Deploying..."`

## Purpose of the Repository

This repository serves as a hands-on example of setting up a **GitHub Actions workflow** for:
- Automating **testing** and **deployment** processes.
- Practicing **CI/CD workflows** with Node.js projects.

## How to Use

1. Clone this repository to your local machine:
   ```bash
   git clone https://github.com/your-username/your-repo.git
