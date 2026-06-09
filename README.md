# sysadmin-automation-scripts

Automated deployment of a secure, multi-tier corporate infrastructure using Azure and Terraform.

## Table of Contents

- [Features](#features)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Usage](#usage)
- [Project Structure](#project-structure)
- [Configuration](#configuration)
- [Contributing](#contributing)
- [License](#license)
- [Support](#support)

## Features

- 🏗️ **Infrastructure as Code**: Complete Azure infrastructure defined in Terraform
- 🔐 **Security-First Design**: Multi-tier architecture with network segmentation
- 🚀 **Automated Deployment**: One-command infrastructure provisioning
- 📊 **Multi-Tier Architecture**: Separate web, application, and database tiers
- 🔄 **Repeatable & Idempotent**: Consistent deployments across environments
- 📝 **Fully Documented**: Clear configuration and deployment guidelines

## Prerequisites

Before you begin, ensure you have the following installed:

- **Terraform** (v1.0 or later) - [Install](https://www.terraform.io/downloads)
- **Azure CLI** (v2.0 or later) - [Install](https://learn.microsoft.com/en-us/cli/azure/install-azure-cli)
- **Git** - [Install](https://git-scm.com/downloads)
- **Azure Account** - Active Azure subscription with appropriate permissions
- **Bash/Shell** - For running automation scripts (Linux, macOS, or Windows with WSL)

## Installation

### 1. Clone the Repository

```bash
git clone https://github.com/roman-malter/sysadmin-automation-scripts.git
cd sysadmin-automation-scripts
az login
az account set --subscription "<your-subscription-id>"
cd terraform
terraform init
cp terraform/terraform.tfvars.example terraform/terraform.tfvars
# Edit terraform/terraform.tfvars with your specific configuration
cd terraform
terraform plan    # Review what will be created
terraform apply   # Deploy the infrastructure
cd terraform
terraform destroy  # Remove all created resources
terraform state list
terraform state show
terraform apply -target=resource_type.resource_name
sysadmin-automation-scripts/
├── terraform/
│   ├── main.tf              # Main infrastructure definition
│   ├── variables.tf         # Variable declarations
│   ├── outputs.tf           # Output values
│   ├── terraform.tfvars     # Variable values (customize this)
│   ├── terraform.tfvars.example  # Example configuration
│   └── modules/             # Reusable Terraform modules
├── scripts/
│   ├── deploy.sh            # Main deployment script
│   ├── validate.sh          # Validation and pre-checks
│   └── utils/               # Utility scripts
├── docs/                    # Additional documentation
├── config/                  # Configuration templates
├── .gitignore              # Git ignore rules
├── LICENSE                 # MIT License
└── README.md               # This file
