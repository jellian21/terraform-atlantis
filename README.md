# Terraform + Atlantis on AWS

This project demonstrates how to deploy and manage AWS infrastructure using **Terraform** with **Atlantis** for pull request automation and infrastructure provisioning workflows.

Atlantis is deployed as a **Docker container** running on an **AWS EC2 instance**, enabling GitOps-style infrastructure management through GitHub pull requests.

---

## Architecture

```text
┌─────────────┐
│ Developer   │
└──────┬──────┘
       │ Git Push / Pull Request
       ▼
┌─────────────┐
│   GitHub    │
└──────┬──────┘
       │ Webhook
       ▼
┌─────────────────────────┐
│ AWS EC2 Instance        │
│                         │
│  ┌───────────────────┐  │
│  │ Atlantis Docker   │  │
│  │ Container         │  │
│  └─────────┬─────────┘  │
└────────────┼────────────┘
             │
             ▼
      ┌─────────────┐
      │ Terraform   │
      └──────┬──────┘
             │
             ▼
      ┌─────────────┐
      │ AWS Cloud   │
      └─────────────┘
```

---

## Features

* Infrastructure as Code (IaC) using Terraform
* Atlantis self-hosted on AWS EC2
* Atlantis deployed as a Docker container
* Automated Terraform plan execution on Pull Requests
* Terraform apply workflow through Atlantis commands
* Modular Terraform project structure
* GitOps-style infrastructure management
* AWS resource provisioning and management

---

## Technology Stack

| Component              | Technology |
| ---------------------- | ---------- |
| Infrastructure as Code | Terraform  |
| Automation             | Atlantis   |
| Cloud Platform         | AWS        |
| Compute                | EC2        |
| Containerization       | Docker     |
| Version Control        | GitHub     |

---

## Repository Structure

```text
.
├── modules/
│   └── s3_bucket/
│       ├── main.tf
│       ├── variables.tf
│       └── outputs.tf
│
├── main.tf
├── providers.tf
├── variables.tf
├── outputs.tf
├── versions.tf
└── README.md
```

---

## Example Atlantis Commands

Run a plan:

```text
atlantis plan
```

Run an apply:

```text
atlantis apply
```

Plan a specific directory:

```text
atlantis plan -d .
```

Apply a specific directory:

```text
atlantis apply -d .
```

---
