# 🚀 GitHub Workflows Repository

This repository contains reusable GitHub Actions workflow templates for automating common tasks across our organization. ⚙️✨

## 📌 Available Workflow Templates

### 1. 🔁 Reusable Workflow: Connect to Google Cloud VM and Update Server

**📂 File:** `.github/workflows/ssh_vm_connection_and_update.yml`

**📝 Description:**
This reusable workflow establishes an SSH connection to a Google Cloud VM, authenticates using GCP credentials, and executes an update script remotely. It is designed for integration into other workflows. 🔄🔐

**🚀 Usage:**
To call this reusable workflow, include the following in your workflow file:

```yaml
jobs:
  connect-to-vm:
    uses: development-at-pixelfield/workflow-templates/.github/workflows/ssh_vm_connection_and_update.yml@master
    with:
      VM_ADDRESS: "your-vm-address"
      VM_PORT: "your-vm-port"
      VM_USERNAME: "your-vm-username"
      SCRIPT_PATH: "your-script-path"
    secrets:
      VM_PRIVATE_KEY: ${{ secrets.VM_PRIVATE_KEY }}
      GCP_CREDENTIALS: ${{ secrets.GCP_CREDENTIALS }}
```

**⚙️ Inputs:**

- `VM_ADDRESS` - (✅ Required) IP address or hostname of the VM.
- `VM_PORT` - (✅ Required) SSH port for the VM.
- `VM_USERNAME` - (✅ Required) Username to connect to the VM.
- `SCRIPT_PATH` - (✅ Required) Path to the script to be executed on the VM.

**🔑 Secrets:**

- `VM_PRIVATE_KEY` - (✅ Required) Private SSH key for secure authentication.
- `GCP_CREDENTIALS` - (✅ Required) Google Cloud authentication credentials.

### 2. 🐳 Reusable Workflow: Build and Push Docker Image to GAR

**📂 File:** `.github/workflows/dockerfile-compose-workflow.yml`

**📝 Description:**
This workflow builds a Docker image using Buildx, caches the layers for faster builds, and pushes the final image to Google Artifact Registry (GAR). 🏗️📦

**🚀 Usage:**
To call this reusable workflow, use the following configuration:

```yaml
jobs:
  build-and-push:
    uses: development-at-pixelfield/workflow-templates/.github/workflows/dockerfile-compose-workflow.yml@master
    with:
      GCLOUD_ZONE: "your-gcloud-zone"
      DOCKERFILE_PATH: "your-dockerfile-path"
      GCLOUD_DOCKER_FILE: "your-docker-repository-path"
    secrets:
      GCP_CREDENTIALS: ${{ secrets.GCP_CREDENTIALS }}
```

**⚙️ Inputs:**

- `GCLOUD_ZONE` - (✅ Required) The Google Cloud region for the artifact registry.
- `DOCKERFILE_PATH` - (✅ Required) Path to the Dockerfile.
- `GCLOUD_DOCKER_FILE` - (✅ Required) The full repository path for storing the image.

**🔑 Secrets:**

- `GCP_CREDENTIALS` - (✅ Required) Google Cloud authentication credentials.

## 🤝 How to Contribute

- 🗂️ If you need to add a new workflow template, place it inside `.github/workflows/`.
- 🛠️ Ensure the workflow is well-documented and tested before committing.
- 🔍 Open a pull request for review.

## 📜 License

This repository follows the company's standard licensing policy.

---

💬 For questions or support, reach out to the DevOps team. 🚀

