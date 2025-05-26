# Terraform Azure Lab Repository

Welcome to the **Terraform Azure Lab** repository! This repo is designed for hands-on learning and mastery of Terraform with Azure. Each folder contains a self-contained lab or assignment focusing on a specific Terraform concept or Azure service.

---

## Table of Contents

- [Getting Started](#getting-started)
- [Labs and Assignments](#labs-and-assignments)
    - [1. Lab - Creating a Linux Virtual Machine](#1-lab---creating-a-linux-virtual-machine)
    - [2. The count meta argument](#2-the-count-meta-argument)
    - [3. Assignment - Creating multiple containers](#3-assignment---creating-multiple-containers)
    - [4. The for_each meta argument](#4-the-for_each-meta-argument)
    - [5. The for_each meta argument - blobs](#5-the-for_each-meta-argument---blobs)
    - [6. Lab - Creating multiple subnets](#6-lab---creating-multiple-subnets)
    - [7. Lab - Creating multiple subnets - Input](#7-lab---creating-multiple-subnets---input)
    - [8. Lab - Adding the network security group](#8-lab---adding-the-network-security-group)
    - [9. Lab - Creating the other dependent resources](#9-lab---creating-the-other-dependent-resources)
    - [10. Lab - Creating multiple machines](#10-lab---creating-multiple-machines)
    - [11. Lab - Availability sets](#11-lab---availability-sets)
    - [12. Using tfvars file](#12-using-tfvars-file)
    - [13. Lab - Availability Zones](#13-lab---availability-zones)
    - [15. Lab - Using the Azure Key Vault service](#15-lab---using-the-azure-key-vault-service)
    - [16. Lab - Data sources](#16-lab---data-sources)
    - [17. Lab - Azure Bastion](#17-lab---azure-bastion)
    - [19. Lab - Custom Script Extensions](#19-lab---custom-script-extensions)
    - [20. Assignment - Adding a NSG to the network interface](#20-assignment---adding-a-nsg-to-the-network-interface)
    - [22. Lab - Storage Accounts - Firewall](#22-lab---storage-accounts---firewall)
    - [23. Assignment - Creating an Azure DataLake Gen2 storage account](#23-assignment---creating-an-azure-datalake-gen2-storage-account)
    - [24. Debugging in Terraform](#24-debugging-in-terraform)
    - [26. Lab - Terraform functions](#26-lab---terraform-functions)
    - [27. Assignment - lower case function](#27-assignment---lower-case-function)
    - [28. for expression](#28-for-expression)
    - [29. Dynamic blocks](#29-dynamic-blocks)
    - [30. Terraform graph](#30-terraform-graph)
    - [31. Lab - Linux Virtual Machines - Cloud init](#31-lab---linux-virtual-machines---cloud-init)
    - [32. Lab - Using provisioners](#32-lab---using-provisioners)
    - [33. Using remote-exec](#33-using-remote-exec)
- [Cleanup](#cleanup)
- [Contributing](#contributing)
- [License](#license)

---

## Getting Started

1. **Install Prerequisites:**
    - [Terraform](https://terraform.io/downloads.html) (v1.0+ recommended)
    - [Azure CLI](https://docs.microsoft.com/en-us/cli/azure/install-azure-cli)
    - [Git](https://git-scm.com/)

2. **Clone this repository:**
    ```bash
    git clone https://github.com/Sunitha82/TerraformLab.git
    cd TerraformLab
    ```

3. **Set up Azure authentication:**
    - Login with `az login` and ensure your subscription is set.
    - Most labs assume provider authentication via environment variables or Azure CLI context.

4. **General Workflow for Each Lab:**
    ```bash
    cd "<lab-folder>"
    terraform init
    terraform plan
    terraform apply
    # ...follow specific lab instructions...
    terraform destroy
    ```

---

## Labs and Assignments

### 1. Lab - Creating a Linux Virtual Machine
- **Goal:** Deploy a Linux VM on Azure with SSH access.
- **Highlights:** Uses `azurerm_linux_virtual_machine`, creates resource group, VNet, NSG, public IP, and uses `tls_private_key` for SSH.
- **Instructions:** Update provider config, run `terraform apply`, connect using the generated SSH key.

---

### 2. The count meta argument
- **Goal:** Learn to use the `count` meta-argument to create multiple similar resources (e.g., storage accounts, VMs).
- **Instructions:** Edit the variable or resource using `count`, `terraform apply`, and observe multiple resources being provisioned.

---

### 3. Assignment - Creating multiple containers
- **Goal:** Practice using `count` or `for_each` to create multiple storage containers inside a storage account.

---

### 4. The for_each meta argument
- **Goal:** Use the `for_each` meta-argument for granular control when creating resources from a map or set.

---

### 5. The for_each meta argument - blobs
- **Goal:** Use `for_each` to create multiple blobs in a storage container.

---

### 6. Lab - Creating multiple subnets
- **Goal:** Deploy a virtual network with several subnets using `count` or `for_each`.

---

### 7. Lab - Creating multiple subnets - Input
- **Goal:** Take subnets as input variables and create them dynamically.

---

### 8. Lab - Adding the network security group
- **Goal:** Associate a Network Security Group (NSG) with a subnet or network interface.

---

### 9. Lab - Creating the other dependent resources
- **Goal:** Chain dependent resources (like IPs, NICs, NSGs) using `depends_on` and resource references.

---

### 10. Lab - Creating multiple machines
- **Goal:** Deploy multiple VMs in one go using `count` or `for_each`.

---

### 11. Lab - Availability sets
- **Goal:** Use Azure Availability Sets for VM high availability.

---

### 12. Using tfvars file
- **Goal:** Manage environment-specific settings using `.tfvars` files for variable values.

---

### 13. Lab - Availability Zones
- **Goal:** Deploy resources across multiple Azure Availability Zones for fault tolerance.

---

### 15. Lab - Using the Azure Key Vault service
- **Goal:** Deploy and use Azure Key Vault to manage secrets, keys, and certificates in Terraform.

---

### 16. Lab - Data sources
- **Goal:** Use Terraform data sources to reference existing Azure resources.

---

### 17. Lab - Azure Bastion
- **Goal:** Deploy Azure Bastion for secure VM access without public IPs.

---

### 19. Lab - Custom Script Extensions
- **Goal:** Use Azure Custom Script Extensions to run scripts on VMs post-provisioning.

---

### 20. Assignment - Adding a NSG to the network interface
- **Goal:** Attach an NSG directly to a VM's network interface.

---

### 22. Lab - Storage Accounts - Firewall
- **Goal:** Configure Storage Account firewalls and virtual network rules.

---

### 23. Assignment - Creating an Azure DataLake Gen2 storage account
- **Goal:** Deploy and configure a Gen2 DataLake storage account.

---

### 24. Debugging in Terraform
- **Goal:** Practice using Terraform debugging features, logs, and troubleshooting failed applies.

---

### 26. Lab - Terraform functions
- **Goal:** Use advanced Terraform functions (`join`, `substr`, etc.) for dynamic resource naming and configuration.

---

### 27. Assignment - lower case function
- **Goal:** Use the `lower()` function to enforce lowercase naming conventions.

---

### 28. for expression
- **Goal:** Use Terraform’s `for` expressions to transform and output lists/maps.

---

### 29. Dynamic blocks
- **Goal:** Use dynamic blocks for repeated nested blocks (like NSG rules or tags).

---

### 30. Terraform graph
- **Goal:** Generate and visualize the dependency graph for your Terraform configuration using `terraform graph`.

---

### 31. Lab - Linux Virtual Machines - Cloud init
- **Goal:** Use cloud-init with Azure Linux VMs to automate provisioning and configuration (e.g., installing packages via `cloud-config` script).

---

### 32. Lab - Using provisioners
- **Goal:** Use file and remote-exec provisioners to copy files and execute scripts on Azure VMs after deployment.

---

### 33. Using remote-exec
- **Goal:** Use the `remote-exec` provisioner to run remote commands (like updates or configuration) after VM creation.

---

## Cleanup

After completing each lab or assignment, always run:
```bash
terraform destroy
```
to avoid incurring unnecessary cloud charges.

---

## Contributing

Pull requests are welcome! Please open an issue to discuss any major changes or suggestions before submitting.

---

## License

This repository is licensed under the MIT License. See [LICENSE](LICENSE) for details.