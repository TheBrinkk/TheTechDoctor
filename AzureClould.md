# Cloud Hosting

# Summary
## Goal
> Have a virtual machine/network to remote into. goal is to make dumb terminals that can use the cloud instead of hardware. Quickbooks in the cloud is also another priority. 

I have seen 2 different options, manually through Microsoft Azure using the portal or can be done programmatically but for such custom solutions i dont see a reason to automate it yet. 

With Azure, the Azure portal is used manually to create what you need. I am not sure about how the resource management/billing would work out but im sure it would be reported. 

Azure Stack is Infrastructure-as-a-Service and provides a portal to setup plans and offers and etc. This would allow a customer to setup/signup and manage plans as well as their users and permissions.
It is basically a SDK for creating VMs and etc on the fly but also has its drawbacks, it is basically a private cloud network. 


# Links

## Research

### Azure
> How to manage VMs with Azure, manual or through code



* [Azure fundamentals](https://docs.microsoft.com/en-us/learn/paths/azure-fundamentals/)
* [Options available to create and manage an Azure Virtual Machine](https://docs.microsoft.com/en-us/learn/modules/intro-to-azure-virtual-machines/4-describe-other-create-vm-options)
* [Virtual Network](https://azure.microsoft.com/en-us/services/virtual-network/)
    * [Virtual Network documentation](https://docs.microsoft.com/en-us/azure/virtual-network/)
    * [Azure-Samples/network-dotnet-manage-virtual-network-with-site-to-site-vpn-connection](https://github.com/Azure-Samples/network-dotnet-manage-virtual-network-with-site-to-site-vpn-connection)
* [Windows Virtual Desktop](https://azure.microsoft.com/en-us/services/virtual-desktop/)
    * [Scale session hosts dynamically (script)](https://docs.microsoft.com/en-us/azure/virtual-desktop/set-up-scaling-script)
    * [Windows Virtual Desktop environment Concepts](https://docs.microsoft.com/en-us/azure/virtual-desktop/environment-setup)
* [VPN Gateway](https://azure.microsoft.com/en-us/services/vpn-gateway/)
    * [Create a Site-to-Site connection in the Azure portal](https://docs.microsoft.com/en-us/azure/vpn-gateway/vpn-gateway-howto-site-to-site-resource-manager-portal)
    * [VPN Pricing](https://azure.microsoft.com/en-us/pricing/details/vpn-gateway/)



### Azure Stack
[Azure Stack](https://azure.microsoft.com/en-us/overview/azure-stack/)
* [Azure Stack IaaS - Blog Post](https://azure.microsoft.com/en-us/blog/azure-stack-iaas-part-one/)
* [Tutorial: Offer a service to users](https://docs.microsoft.com/en-us/azure-stack/operator/tutorial-offer-services?view=azs-1910)
* [Install Azure Stack Development Kit](https://docs.microsoft.com/en-us/azure-stack/asdk/asdk-install?view=azs-1910)
* [Azure Stack Hub VM features](https://docs.microsoft.com/en-us/azure-stack/user/azure-stack-vm-considerations?view=azs-1910)
* 

## General
[Remote Desktop Web Client - Microsoft Docs](https://docs.microsoft.com/en-us/windows-server/remote/remote-desktop-services/clients/remote-desktop-web-client)

[MarkDown Cheat Sheet](https://www.markdownguide.org/cheat-sheet/)

[How to Migrate QuickBooks to Azure in a Single Afternoon Using Nerdio for Azure Professional](https://getnerdio.com/academy/migrate-quickbooks-to-azure/)
