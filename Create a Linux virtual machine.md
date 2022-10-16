# Create a Linux VM

## VM components
- **CPU + RAM**
- **Azure Storage** Account --> *OS disk and Temporary disk - HDD/SSD*
- **Azure Networking** Resources --> *VNet, NIC, Public IP*

## VM provisioning - ways
- Azure portal, Azure CLI, Azure PowerShell, ARM template

## VM provisioning - steps
- Choose VM image
- Choose VM size (CPU + RAM + Storage)
- Choose storage technology (HDD, SSD standard/premium) --> decide to store data with OS or on dedicated data disks
- Choose virtual network --> existing or new one

## VM virtual disks (VHD) - size
- 1 Gibibyte (GiB) = 1074 Gigabyte (GB)

## VM virtual disks (VHD) - unmanaged vs managed
- **Unmanaged** --> you manage storage account which holds VHDs
- **Managed** --> Azure manages storage account which holds VHDs --> security, backup, scaling, ...

## VM management
- Start/Stop VM from Azure portal or with Azure CLI

## VM connection
- Connect to VM using Secure Shell (SSH)
- To connect to the VM via SSH, you need the following items
  - Public IP address of the VM
  - Username of the local account on the VM
  - Public key configured in that account
  - Access to the corresponding private key
  - Port 22 open on the VM

## Secure Shell (SSH)
- Encrypted connection protocol to **connect to terminal shell from remote location** using network connection
- **Authentication methods**
  - **Username and password** --> less secure --> connect from more computers
  - **SSH public-private key pair (SSH keys)** --> more secure --> connect from a few computer
    - ... public key in placed on Linux VM and can be shared with anyone
    - ... private key is confidential and presented to verify your identity
      - ... it can be additionally protected with a passphrase --> necessary to use a private key

## Create SSH key pair in Azure Cloud Shell
- `ssh-keygen -m PEM -t rsa -b 4096` --> enter passphrase to protect private key
- This command creates two files: `id_rsa` and `id_rsa.pub` in `~/.ssh directory` --> files are overwritten if they exist
- Create SSH key pair will be stored in your private storage account
- Show generated public key --> `cat ~/.ssh/id_rsa.pub`
- Install the public key file, and authorize the user with the key --> `ssh-copy-id -i ~/.ssh/id_rsa.pub azureuser@vmname`
