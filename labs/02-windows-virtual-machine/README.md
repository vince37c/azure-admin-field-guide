# Lab 02: Create a Windows Virtual Machine

## Objective
Deploy a Windows virtual machine in Azure and review the resources automatically created during deployment. Validate networking configuration and confirm the VM is running.

## Resources Created
- Virtual Machine  
- Network Interface (NIC)  
- Public IP Address  
- Network Security Group (NSG)  
- OS Disk

## Prerequisites
- Existing Azure tenant + subscription
- Contributor permissions
- Existing Virtual Network + Subnet from the previous lab

## Naming Used (Examples)
- Resource Group: vm-rg
- Virtual Machine: vm1
- Virtual Network: lab-vnet
- Subnet: default

## Build Steps (Azure Portal)

1. Navigate to **Virtual machines**.
2. Click **Create** → **Azure virtual machine**.
3. On the **Basics** tab:
   - Select subscription.
   - Select an existing resource group or create a new one.
   - Enter a VM name (example: win-vm).
   - Choose a region that matches the virtual network region.
   - Choose an image (example: Windows Server 2022).
   - Select a VM size (example: a small/budget-friendly size for labs).
   - Create an administrator username and password (do not store these in GitHub).
   - Set **Public inbound ports** to **None** initially (recommended).
4. On the **Disks** tab:
   - Keep defaults or choose a disk type based on cost/performance (example: Standard SSD for labs).
5. On the **Networking** tab:
   - Select the existing Virtual Network.
   - Select the target subnet.
   - Public IP:
     - Option A (recommended): No public IP, use Bastion/VPN later.
     - Option B: Create a public IP for learning purposes.
   - NIC network security group:
     - Basic or Advanced.
   - If using public access, allow only required ports (example: RDP 3389) and restrict source IP where possible.
6. Keep remaining tabs at default unless you are testing a specific feature.
7. Click **Review + create**, then **Create**.

## Validation
- Confirm the VM deployment completed successfully.
- Confirm the VM status shows Running.
- Confirm the VM and supporting resources appear in the resource group.
- Confirm a Public IP and Network Security Group were created.

## Screenshots to Capture
- VM deployment completed → 01-vm-deployment-success.png
- Resource group overview showing created resources → 02-resource-group-resources.png
- Virtual machine running in Azure portal → 03-virtual-machine-running.png

## Cleanup
Option A (cleanest):
1. Delete the VM resource group (removes VM, NIC, NSG, disk, public IP).

Option B (manual):
1. Delete the VM.
2. Delete the NIC.
3. Delete the Public IP (if created).
4. Delete the OS disk (if not removed automatically).
5. Delete the NSG (if not used elsewhere).

## Notes / What I Learned
- VM creation automatically provisions dependent resources like NIC and OS disk.
- A VM must be deployed in the same region as the virtual network it connects to.
- Azure automatically creates dependent resources like NICs and OS disks during deployment.
- Public access requires a public IP and an NSG rule; least privilege matters even in labs.
- Small VM sizes are useful for learning while controlling cost.
