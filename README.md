# azure-iac-templates
This repository provides reusable Infrastructure-as-Code templates for deploying common Azure resources including Virtual Machines, AKS clusters, and Web Apps. It supports three formats: **Bicep**, **Terraform**, and **ARM templates**, enabling teams to adopt IaC best practices across different tooling preferences.
Azure Template
## 🧭 Folder Structure
## 📁 Template Types

- **Virtual Machines**: Templates for deploying Ubuntu-based VMs
- **AKS Clusters**: Production-ready Kubernetes cluster configurations
- **Web Apps**: Deploy Azure App Services with optional Hosting Plan settings
- ## 🛡️ Best Practices

### 🔒 Security
- Use Azure Key Vault to store secrets securely
- Enable NSGs and diagnostic logging
- Prefer Managed Identity for authentication

### 📐 Naming Conventions
- Use prefixes (`vm-`, `aks-`, `web-`)
- Include environment codes (`dev`, `prod`) and region identifiers

### 📈 Scalability
- AKS node pools with autoscaling
- App Service plans configured for scaling
- Templates support parameter-based environments

## 🚀 Usage Instructions

### Bicep Deployment
```bash
az deployment group create \
  --resource-group <your-rg> \
  --template-file bicep/vm.bicep

## Terraform Deployment
cd terraform/aks/
terraform init
terraform apply

## ARM Deployment
az deployment group create \
  --resource-group <your-rg> \
  --template-file arm/webapp.json \
  --parameters webAppName=<name> hostingPlanId=<id>
