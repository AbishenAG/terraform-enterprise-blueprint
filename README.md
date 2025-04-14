# Terraform Enterprise Blueprint with Terragrunt

This repository is a modular, production-grade Terraform setup using Terragrunt for managing infrastructure across multiple environments. It supports best practices for scalability, DRY principles, and infrastructure-as-code automation.

## 🌐 Cloud Provider

- Primary: **Azure**
- Optional: AWS and GCP structures are scaffolded for future expansion.

---

## 🗂️ Project Structure

```bash
terraform-enterprise-blueprint/
├── bootstrap/                   # One-time setup for backend storage (remote state)
│   ├── main.tf
│   ├── variables.tf
│   ├── outputs.tf
│   └── provider.tf
│
├── conventions/                # Shared configurations across modules
│   ├── terraform_backend.tf
│   ├── tags.tf
│   ├── locals.tf
│   └── variable_defaults.tf
│
├── modules/                    # Reusable resource modules
│   ├── networking/
│   ├── security/
│   ├── private_dns/
│   ├── compute/
│   ├── storage/
│   ├── databases/
│   ├── monitoring/
│   ├── devops/
│   ├── app_platform/
│   └── common/
│
├── providers/                 # Providers for different cloud vendors
│   ├── azure/
│   ├── aws/
│   └── gcp/
│
├── environments/              # Environment-specific live configurations
│   ├── dev/
│   │   └── terragrunt.hcl
│   ├── staging/
│   │   └── terragrunt.hcl
│   └── prod/
│       └── terragrunt.hcl
│
├── scripts/                   # Automation & pipeline scripts
│   ├── terraform-pipelines/
│   ├── automation-scripts/
│   └── terraform_destroy/
│
├── documentation/             # Design, architecture, and usage docs
│   └── ...
│
└── tests/                     # Testing folder
    ├── unit-test/
    │   └── plan/
    └── integration-test/
        └── ...
