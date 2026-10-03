# azure-terraform-infra

Terraform code to provision a complete Azure network with VNet, NSG, Public IP, NIC, and a Linux VM running Nginx.

## Azure Infrastructure with Terraform (Project 3)

This project demonstrates Infrastructure as Code (IaC) using Terraform to provision a complete Azure environment in the Central India region.

### 🏗️ Architecture Overview

The Terraform script provisions the following Azure resources:

- **Resource Group**: Container for all Azure resources (`rg-terraform-demo`).
- **Virtual Network**: Isolated network with address space `10.0.0.0/16`.
- **Subnet**: Dedicated subnet for the VM (`10.0.1.0/24`).
- **Network Security Group**: Firewall with inbound rules for SSH (22) and HTTP (80).
- **Public IP**: Static, Standard SKU public address.
- **Network Interface**: VM's NIC attached to the subnet and public IP.
- **Linux VM**: Ubuntu 22.04 LTS (`Standard_B2ats_v2`) with Nginx auto-installed via cloud-init.

### 🛠️ Technologies Used

- **Infrastructure as Code**: Terraform
- **Cloud**: Microsoft Azure (Central India)
- **Compute**: Azure Linux VM (Ubuntu 22.04)
- **Web Server**: Nginx (provisioned via cloud-init)
- **Networking**: VNet, Subnet, NSG, Public IP

### 📂 Project Structure
