# Deploy CoreOS node with VSTS Agent (Docker container)
This is a template allows you to create a Virtual Machine in Azure running CoreOS (Stable) which starts four (4) VSTS Agents (Azure DevOps Agents?) using Docker Containers.

# Before deployment
Make sure you have the following parameters in the [azuredeploy.parameters.json](azuredeploy.parameters.json) file:
- adminPublicKey (SSH Public key)
- virtualNetworkRG (Existing resource group where the virtual network the node is being deployed to)
- virtualNetworkName (Existing virtual network in the above resource group)
- subnetName (Existing subnet in the above virtual network)
- VstsAccount (Account for VSTS / Azure DevOps)
- VstsToken (Token for VSTS / Azure DevOps)

The other parameters should be change to match your environment. If you are using the default values the following resources will be created:
- Virtual Machine: vm-we-dev-vsts01
- OS Disk: osdisk-vm-we-dev-vsts01
- NIC: nic-vm-we-dev-vsts01

To modify the naming, change the variables.

# For readability
The ignition configuration that is used in the customData can be found here:
[ignition.json](ignition.json)

The service definition in the ignition configuration can be found here:
[vsts-agentX.service](vsts-agentX.service)