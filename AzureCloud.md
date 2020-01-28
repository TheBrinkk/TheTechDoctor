# Cloud Hosting

# Summary

I have seen 2 different options, manually through Microsoft Azure using the portal or can be done programmatically using Azure Powershell/CLI. 

With Azure, the Azure portal is used manually to create what you need. I am not sure about how the resource management/billing would work out but im sure it would be reported. 



## Goal
> Have a virtual machine/network to remote into. goal is to leverage the cloud instead of hardware.  


# Azure
> How to manage VMs with Azure, manual or through code
* [Azure fundamentals](https://docs.microsoft.com/en-us/learn/paths/azure-fundamentals/)
* [Options available to create and manage an Azure Virtual Machine](https://docs.microsoft.com/en-us/learn/modules/intro-to-azure-virtual-machines/4-describe-other-create-vm-options)

* [Virtual Network](https://azure.microsoft.com/en-us/services/virtual-network/)
    * [Virtual Network documentation](https://docs.microsoft.com/en-us/azure/virtual-network/)
    * [Azure-Samples/network-dotnet-manage-virtual-network-with-site-to-site-vpn-connection](https://github.com/Azure-Samples/network-dotnet-manage-virtual-network-with-site-to-site-vpn-connection)

    

* [VPN Gateway](https://azure.microsoft.com/en-us/services/vpn-gateway/)
    * [Create a Site-to-Site connection in the Azure portal](https://docs.microsoft.com/en-us/azure/vpn-gateway/vpn-gateway-howto-site-to-site-resource-manager-portal)
    * [VPN Pricing](https://azure.microsoft.com/en-us/pricing/details/vpn-gateway/)


## Azure PowerShell
## [Azure PowerShell documentation](https://docs.microsoft.com/en-us/powershell/azure/?view=azps-3.3.0)

## [Azure Virtual Machine PowerShell samples](https://docs.microsoft.com/en-us/azure/virtual-machines/windows/powershell-samples?toc=%2fpowershell%2fmodule%2ftoc.json)

* [Create a fully configured virtual machine with PowerShell](https://docs.microsoft.com/en-us/azure/virtual-machines/scripts/virtual-machines-windows-powershell-sample-create-vm?toc=%2fazure%2fvirtual-machines%2fwindows%2ftoc.json)

[Create a virtual machine Tutorial](https://docs.microsoft.com/en-us/powershell/azure/azureps-vm-tutorial?tutorial-step=4&view=azps-3.3.0)

```powershell
$vmParams = @{
  ResourceGroupName = 'TutorialResources'
  Name = 'TutorialVM1'
  Location = 'eastus'
  ImageName = 'Win2016Datacenter'
  PublicIpAddressName = 'tutorialPublicIp'
  Credential = $cred
  OpenPorts = 3389
}
$newVM1 = New-AzVM @vmParams
```

```powershell
$publicIp = Get-AzPublicIpAddress -Name tutorialPublicIp -ResourceGroupName TutorialResources

$publicIp | Select-Object Name,IpAddress,@{label='FQDN';expression={$_.DnsSettings.Fqdn}}
```
[PowerShell Tutorial Summary](https://docs.microsoft.com/en-us/powershell/azure/azureps-vm-tutorial?tutorial-step=8&view=azps-3.3.0)

## Powershell cmdlets
* [New-AzVM](https://docs.microsoft.com/en-us/powershell/module/Az.compute/new-Azvm?view=azps-3.3.0)
* [New-AzResourceGroup](https://docs.microsoft.com/en-us/powershell/module/az.resources/new-azresourcegroup?view=azps-3.3.0)

## Azure CLI
## [Azure CLI Samples for Windows virtual machines](https://docs.microsoft.com/en-us/azure/virtual-machines/windows/cli-samples)

```bash
#!/bin/bash

# Update for your admin password
AdminPassword=ChangeYourAdminPassword1

# Create a resource group.
az group create --name myResourceGroup --location westeurope

# Create a virtual network.
az network vnet create --resource-group myResourceGroup --name myVnet --subnet-name mySubnet

# Create a public IP address.
az network public-ip create --resource-group myResourceGroup --name myPublicIP

# Create a network security group.
az network nsg create --resource-group myResourceGroup --name myNetworkSecurityGroup

# Create a virtual network card and associate with public IP address and NSG.
az network nic create \
  --resource-group myResourceGroup \
  --name myNic \
  --vnet-name myVnet \
  --subnet mySubnet \
  --network-security-group myNetworkSecurityGroup \
  --public-ip-address myPublicIP

# Create a virtual machine. 
az vm create \
    --resource-group myResourceGroup \
    --name myVM \
    --location westeurope \
    --nics myNic \
    --image win2016datacenter \
    --admin-username azureuser \
    --admin-password $AdminPassword

# Open port 3389 to allow RDP traffic to host.
az vm open-port --port 3389 --resource-group myResourceGroup --name myVM
```

## General
[Remote Desktop Web Client - Microsoft Docs](https://docs.microsoft.com/en-us/windows-server/remote/remote-desktop-services/clients/remote-desktop-web-client)

[MarkDown Cheat Sheet](https://www.markdownguide.org/cheat-sheet/)

[How to Migrate QuickBooks to Azure in a Single Afternoon Using Nerdio for Azure Professional](https://getnerdio.com/academy/migrate-quickbooks-to-azure/)


[Understanding important PowerShell (windows) concepts](https://docs.microsoft.com/en-us/powershell/scripting/learn/understanding-important-powershell-concepts?view=powershell-7)

[Advanced Tools & Scripting with PowerShell (windows) 3.0 Jump Start](https://channel9.msdn.com/Series/Advanced-Tools-and-Scripting-with-PowerShell-3.0-Jump-Start)



### ~~Azure Stack~~ ( I dont think we need this)

Azure Stack is Infrastructure-as-a-Service and provides a portal to setup plans and offers and etc. This would allow a customer to setup/signup and manage plans 
as  well as their users and permissions.
It is basically a SDK for creating VMs and etc on the fly but also has its drawbacks, it is basically a private cloud network.


[Azure Stack](https://azure.microsoft.com/en-us/overview/azure-stack/)
* [Azure Stack IaaS - Blog Post](https://azure.microsoft.com/en-us/blog/azure-stack-iaas-part-one/)
* [Tutorial: Offer a service to users](https://docs.microsoft.com/en-us/azure-stack/operator/tutorial-offer-services?view=azs-1910)
* [Install Azure Stack Development Kit](https://docs.microsoft.com/en-us/azure-stack/asdk/asdk-install?view=azs-1910)
* [Azure Stack Hub VM features](https://docs.microsoft.com/en-us/azure-stack/user/azure-stack-vm-considerations?view=azs-1910)~~