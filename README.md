# Azure Infrastructure with Terraform

Terraform configuration to provision a complete Azure environment from scratch —
Resource Group, Virtual Network, Subnet, Network Security Group, Public IP, Network
Interface, and a Linux VM running Nginx.

## Architecture
Resource Group (rg-terraform-demo)
├── Virtual Network (vnet-demo) 10.0.0.0/16
│ └── Subnet (subnet-demo) 10.0.1.0/24
├── Network Security Group (nsg-demo)
│ ├── Inbound rule: SSH (port 22)
│ └── Inbound rule: HTTP (port 80)
├── Public IP (pip-demo) Static, Standard SKU
├── Network Interface (nic-demo)
└── Linux VM (vm-demo)
├── Ubuntu 22.04 LTS
├── Size: Standard_B2ats_v2
└── Nginx auto-installed via cloud-init
