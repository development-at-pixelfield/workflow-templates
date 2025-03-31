# 🚀 GitHub Workflows Repository

This repository contains reusable GitHub Actions workflow templates for automating common tasks across our organization. ⚙️✨

## 📌 Available Workflow Templates

### 1. 🔄 Update Google Cloud VM
**📂 File:** `.github/workflows/ssh_vm_connection_and_update.yml`

**📝 Description:**
This workflow automates the process of updating a Google Cloud Virtual Machine (VM). It ensures that the instance is kept up to date with the latest software and configurations. ☁️💡

**🚀 Usage:**
To use this workflow in your repository, create a workflow file in `.github/workflows/` and include the following:

```yaml
jobs:
  update-gcloud-vm:
    uses: development-at-pixelfield/.github/workflows/ssh_vm_connection_and_update.yml@main
```

## 🤝 How to Contribute
- 🗂️ If you need to add a new workflow template, place it inside `.github/workflows/`.
- 🛠️ Ensure the workflow is well-documented and tested before committing.
- 🔍 Open a pull request for review.

## 📜 License
This repository follows the company's standard licensing policy.

---
💬 For questions or support, reach out to the DevOps team. 🚀

