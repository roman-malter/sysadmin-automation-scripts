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
```

### 2. Authenticate with Azure

```bash
az login
az account set --subscription "<your-subscription-id>"
```

### 3. Initialize Terraform

```bash
cd terraform
terraform init
```

### 4. Configure Variables

Copy the example variables file and update with your values:

```bash
cp terraform/terraform.tfvars.example terraform/terraform.tfvars
# Edit terraform/terraform.tfvars with your specific configuration
```

## Usage

### Deploy Infrastructure

```bash
cd terraform
terraform plan    # Review what will be created
terraform apply   # Deploy the infrastructure
```

### Destroy Infrastructure

```bash
cd terraform
terraform destroy  # Remove all created resources
```

### Common Tasks

#### List Deployed Resources
```bash
terraform state list
```

#### View Current Infrastructure State
```bash
terraform state show
```

#### Update Specific Resources
```bash
terraform apply -target=resource_type.resource_name
```

## Project Structure

```
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
```

## Configuration

### Terraform Variables

Key variables you'll need to configure in `terraform.tfvars`:

- `resource_group_name` - Azure resource group name
- `location` - Azure region (e.g., "East US")
- `environment` - Environment name (dev, staging, prod)
- `vm_size` - Azure VM size for compute tier
- `database_version` - Database version for the data tier

### Azure Resources

This infrastructure deploys:

- **Web Tier**: Application Gateway + Virtual Machines
- **Application Tier**: VM Scale Sets for load balancing
- **Database Tier**: Azure Database for secure data storage
- **Networking**: VNets, Subnets, NSGs for security

## Contributing

Contributions are welcome! Please follow these guidelines:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/your-feature`)
3. Make your changes
4. Test your Terraform configuration
5. Submit a pull request with a clear description

### Code Style

- Use consistent formatting in Terraform files
- Add comments for complex configurations
- Follow Azure naming conventions

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Support

For issues, questions, or suggestions:

- Open an [Issue](https://github.com/roman-malter/sysadmin-automation-scripts/issues) on GitHub
- Check existing documentation in the `docs/` folder
- Review Terraform and Azure CLI documentation

---

**Last Updated**: June 9, 2026
