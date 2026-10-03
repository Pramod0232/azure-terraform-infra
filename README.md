# Azure-terraform-infra

Terraform code to provision a complete Azure network with VNet, NSG, Public IP, NIC, and a Linux VM running Nginx.

---

## Azure Infrastructure with Terraform (Project 3)

This project demonstrates Infrastructure as Code (IaC) using Terraform to provision a complete Azure environment in the Central India region.

---

### 🏗️ Architecture Overview

The Terraform script provisions the following Azure resources:

- **Resource Group** — Container for all Azure resources (`rg-terraform-demo`)
- **Virtual Network** — Isolated network with address space `10.0.0.0/16`
- **Subnet** — Dedicated subnet for the VM (`10.0.1.0/24`)
- **Network Security Group** — Firewall with inbound rules for SSH (22) and HTTP (80)
- **Public IP** — Static, Standard SKU public address
- **Network Interface** — VM's NIC attached to the subnet and public IP
- **Linux VM** — Ubuntu 22.04 LTS (`Standard_B2ats_v2`) with Nginx auto-installed via cloud-init

---

### 🛠️ Technologies Used

| Category | Technology |
|----------|------------|
| Infrastructure as Code | Terraform |
| Cloud | Microsoft Azure (Central India) |
| Compute | Azure Linux VM (Ubuntu 22.04) |
| Web Server | Nginx (via cloud-init) |
| Networking | VNet, Subnet, NSG, Public IP |

---

### 📂 Project Structure
azure-terraform-infra/
├── main.tf # Main Terraform configuration
├── variables.tf # Input variables (region, RG name, SSH key path)
├── outputs.tf # Outputs (Public IP, SSH command, HTTP URL)
├── .gitignore # Excludes state files and .terraform cache
├── README.md # This documentation
├── azure-vm-nginx.png.png # Nginx welcome page screenshot
├── azure-portal-rg.png.png # Azure Portal resource view
└── terraform-apply.png.png # Terraform apply output


### 🚀 Deployment Instructions

To deploy this infrastructure yourself:

1. Clone the repository: git clone https://github.com/Pramod0232/azure-terraform-infra.git
cd azure-terraform-infra

2. Login to Azure: az login
3. Initialize Terraform: terraform init
4. Preview the infrastructure: terraform plan
5. Deploy the infrastructure: terraform apply -auto-approve
6. Access the web server: http_url      = "http://<PUBLIC_IP>"
                          public_ip     = "<PUBLIC_IP>"
                          ssh_command   = "ssh azureuser@<PUBLIC_IP>"
 Open your browser and visit http://<PUBLIC_IP> to see the live Nginx server.
7. Clean up: terraform destroy -auto-approve

### Terraform Apply — Deployment Output
<img src="https://raw.githubusercontent.com/Pramod0232/azure-terraform-infra/main/terraform-apply.png" alt="Terraform Apply Output" width="900">

### Azure Portal — All Provisioned Resources
<img src="https://raw.githubusercontent.com/Pramod0232/azure-terraform-infra/main/azure-portal-rg.png" alt="Azure Portal Resource Group" width="900">

### Live Nginx Web Server on Azure VM
<img src="https://raw.githubusercontent.com/Pramod0232/azure-terraform-infra/main/azure-vm-nginx.png" alt="Nginx Welcome Page" width="900">

