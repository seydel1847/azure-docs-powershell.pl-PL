---
title: Rozpoczynanie pracy z programem Azure PowerShell
description: ''
author: sptramer
ms.author: sttramer
manager: carmonm
ms.devlang: powershell
ms.topic: get-started-article
ms.date: 09/11/2018
ms.openlocfilehash: 5378cdb9d70aa0d2dc617d06d3c887ec20eb7767
ms.sourcegitcommit: 5f946a535eccca0b3ddf3db8f617b32564a88938
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/25/2018
ms.locfileid: "50000678"
---
# <a name="get-started-with-azure-powershell"></a><span data-ttu-id="e051b-102">Rozpoczynanie pracy z programem Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="e051b-102">Get started with Azure PowerShell</span></span>

<span data-ttu-id="e051b-103">Program Azure PowerShell jest przeznaczony do zarządzania i administrowania zasobami platformy Azure przy użyciu wiersza polecenia oraz do tworzenia skryptów automatyzacji, które pozwalają obsługiwać usługę Azure Resource Manager.</span><span class="sxs-lookup"><span data-stu-id="e051b-103">Azure PowerShell is designed for managing and administering Azure resources from the command line, and for building automation scripts that work against the Azure Resource Manager.</span></span> <span data-ttu-id="e051b-104">Można go używać w przeglądarce dzięki usłudze [Azure Cloud Shell](/azure/cloud-shell/overview) albo można go zainstalować na maszynie lokalnej.</span><span class="sxs-lookup"><span data-stu-id="e051b-104">You can use it in your browser with [Azure Cloud Shell](/azure/cloud-shell/overview) or you install it on your local machine.</span></span> <span data-ttu-id="e051b-105">W tym artykule przedstawiono podstawowe pojęcia związane z programem Azure PowerShell, które ułatwiają rozpoczęcie korzystania z niego.</span><span class="sxs-lookup"><span data-stu-id="e051b-105">This article helps get you started with Azure PowerShell and teaches the core concepts behind it.</span></span>

## <a name="install-azure-powershell"></a><span data-ttu-id="e051b-106">Instalowanie programu Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="e051b-106">Install Azure PowerShell</span></span>

<span data-ttu-id="e051b-107">Pierwszym krokiem jest upewnienie się, że jest zainstalowana najnowsza wersja programu Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e051b-107">The first step is to make sure you have the latest version of the Azure PowerShell installed.</span></span> <span data-ttu-id="e051b-108">Aby uzyskać informacje o najnowszej wersji, zobacz [informacje o wersji](./release-notes-azureps.md).</span><span class="sxs-lookup"><span data-stu-id="e051b-108">For information about the latest release, see the [release notes](./release-notes-azureps.md).</span></span>

1. <span data-ttu-id="e051b-109">[Zainstalowanie programu Azure PowerShell](install-azurerm-ps.md).</span><span class="sxs-lookup"><span data-stu-id="e051b-109">[Install Azure PowerShell](install-azurerm-ps.md).</span></span>

2. <span data-ttu-id="e051b-110">Aby sprawdzić, czy instalacja się powiodła, uruchom polecenie `Get-Module AzureRM -ListAvailable` w wierszu polecenia.</span><span class="sxs-lookup"><span data-stu-id="e051b-110">To verify the installation was successful, run `Get-Module AzureRM -ListAvailable` from your command line.</span></span>

## <a name="azure-cloud-shell"></a><span data-ttu-id="e051b-111">Azure Cloud Shell</span><span class="sxs-lookup"><span data-stu-id="e051b-111">Azure Cloud Shell</span></span>

<span data-ttu-id="e051b-112">Najprostszym sposobem na rozpoczęcie pracy jest [uruchomienie usługi Cloud Shell](/azure/cloud-shell/quickstart).</span><span class="sxs-lookup"><span data-stu-id="e051b-112">The simplest way to get started is to [launch Cloud Shell](/azure/cloud-shell/quickstart).</span></span>

1. <span data-ttu-id="e051b-113">Uruchom usługę Cloud Shell z górnego obszaru nawigacyjnego witryny Azure Portal.</span><span class="sxs-lookup"><span data-stu-id="e051b-113">Launch Cloud Shell from the top navigation of the Azure portal.</span></span>

   ![Ikona powłoki](~/media/get-started-azureps/shell-icon.png)

2. <span data-ttu-id="e051b-115">Wybierz subskrypcję, której chcesz użyć, a następnie utwórz konto magazynu.</span><span class="sxs-lookup"><span data-stu-id="e051b-115">Choose the subscription you want to use and create a storage account.</span></span>

   ![Tworzenie konta magazynu](~/media/get-started-azureps/storage-prompt.png)

<span data-ttu-id="e051b-117">Po utworzeniu magazynu usługa Cloud Shell otworzy sesję programu PowerShell w przeglądarce.</span><span class="sxs-lookup"><span data-stu-id="e051b-117">Once your storage has been created, the Cloud Shell will open a PowerShell session in the browser.</span></span>

![Usługa Cloud Shell dla programu PowerShell](~/media/get-started-azureps/cloud-powershell.png)

<span data-ttu-id="e051b-119">Program Azure PowerShell można również zainstalować i używać lokalnie w sesji programu PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e051b-119">You can also install Azure PowerShell and use it locally in a PowerShell session.</span></span>

## <a name="sign-in-to-azure"></a><span data-ttu-id="e051b-120">Logowanie do platformy Azure</span><span class="sxs-lookup"><span data-stu-id="e051b-120">Sign in to Azure</span></span>

<span data-ttu-id="e051b-121">Logowanie interaktywne:</span><span class="sxs-lookup"><span data-stu-id="e051b-121">Sign on interactively:</span></span>

1. <span data-ttu-id="e051b-122">Wpisz polecenie `Connect-AzureRmAccount`.</span><span class="sxs-lookup"><span data-stu-id="e051b-122">Type `Connect-AzureRmAccount`.</span></span> <span data-ttu-id="e051b-123">Zostanie wyświetlone okno dialogowe z monitem o podanie poświadczeń platformy Azure.</span><span class="sxs-lookup"><span data-stu-id="e051b-123">You'll get a dialog box asking for your Azure credentials.</span></span> <span data-ttu-id="e051b-124">Opcja „-Environment” pozwala uwierzytelnić się na platformie Azure (Chiny) lub Azure (Niemcy).</span><span class="sxs-lookup"><span data-stu-id="e051b-124">Option '-Environment' can let you authenticate for Azure China or Azure Germany.</span></span>

   <span data-ttu-id="e051b-125">na przykład Connect-AzureRmAccount -Environment AzureChinaCloud</span><span class="sxs-lookup"><span data-stu-id="e051b-125">for example, Connect-AzureRmAccount -Environment AzureChinaCloud</span></span>

2. <span data-ttu-id="e051b-126">Wpisz adres e-mail i hasło skojarzone z kontem.</span><span class="sxs-lookup"><span data-stu-id="e051b-126">Type the email address and password associated with your account.</span></span> <span data-ttu-id="e051b-127">Nastąpi uwierzytelnienie i zapisanie informacji o poświadczeniach na platformie Azure, a następnie zamknięcie okna.</span><span class="sxs-lookup"><span data-stu-id="e051b-127">Azure authenticates and saves the credential information, and then closes the window.</span></span>

<span data-ttu-id="e051b-128">Po zalogowaniu się do konta platformy Azure można korzystać z poleceń cmdlet programu Azure PowerShell w celu uzyskania dostępu do zasobów subskrypcji i zarządzania nimi.</span><span class="sxs-lookup"><span data-stu-id="e051b-128">Once you have signed in to an Azure account, you can use the Azure PowerShell cmdlets to access and manage the resources in your subscription.</span></span>

## <a name="create-a-windows-virtual-machine-using-simple-defaults"></a><span data-ttu-id="e051b-129">Tworzenie maszyny wirtualnej z systemem Windows przy użyciu prostych wartości domyślnych</span><span class="sxs-lookup"><span data-stu-id="e051b-129">Create a Windows virtual machine using simple defaults</span></span>

<span data-ttu-id="e051b-130">Polecenie cmdlet `New-AzureRmVM` udostępnia uproszczoną składnię, co ułatwia utworzenie nowej maszyny wirtualnej.</span><span class="sxs-lookup"><span data-stu-id="e051b-130">The `New-AzureRmVM` cmdlet provides a simplified syntax making it easy to create a new virtual machine.</span></span> <span data-ttu-id="e051b-131">Trzeba podać jedynie dwie wartości parametrów: nazwę maszyny wirtualnej i zestaw poświadczeń dla lokalnego konta administratora na maszynie wirtualnej.</span><span class="sxs-lookup"><span data-stu-id="e051b-131">There are only two parameter values you must provide: the name of the VM and a set of credentials for the local administrator account on the VM.</span></span>

<span data-ttu-id="e051b-132">Najpierw utwórz obiekt poświadczeń.</span><span class="sxs-lookup"><span data-stu-id="e051b-132">First, create the credential object.</span></span>

```azurepowershell-interactive
$cred = Get-Credential -Message "Enter a username and password for the virtual machine."
```

```output
Windows PowerShell credential request.
Enter a username and password for the virtual machine.
User: localAdmin
Password for user localAdmin: *********
```

<span data-ttu-id="e051b-133">Następnie utwórz maszynę wirtualną.</span><span class="sxs-lookup"><span data-stu-id="e051b-133">Next, create the VM.</span></span>

```azurepowershell-interactive
New-AzureRmVM -Name SampleVM -Credential $cred
```

```output
ResourceGroupName        : SampleVM
Id                       : /subscriptions/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX/resourceGroups/SampleVM/providers/Microsoft.Compute/virtualMachines/SampleVM
VmId                     : 43f6275d-ce50-49c8-a831-5d5974006e63
Name                     : SampleVM
Type                     : Microsoft.Compute/virtualMachines
Location                 : eastus
Tags                     : {}
HardwareProfile          : {VmSize}
NetworkProfile           : {NetworkInterfaces}
OSProfile                : {ComputerName, AdminUsername, WindowsConfiguration, Secrets}
ProvisioningState        : Succeeded
StorageProfile           : {ImageReference, OsDisk, DataDisks}
FullyQualifiedDomainName : samplevm-2c0867.eastus.cloudapp.azure.com
```

<span data-ttu-id="e051b-134">Możesz się zastanawiać, co jeszcze jest tworzone i w jaki sposób maszyna wirtualna jest konfigurowana.</span><span class="sxs-lookup"><span data-stu-id="e051b-134">You may wonder what else is created and how is the VM configured.</span></span> <span data-ttu-id="e051b-135">Najpierw przyjrzyjmy się grupom zasobów.</span><span class="sxs-lookup"><span data-stu-id="e051b-135">First, let's look at our resource groups.</span></span>

```azurepowershell-interactive
Get-AzureRmResourceGroup | Select-Object ResourceGroupName,Location
```

```output
ResourceGroupName          Location
-----------------          --------
cloud-shell-storage-westus westus
SampleVM                   eastus
```

<span data-ttu-id="e051b-136">Grupa zasobów **cloud-shell-storage-westus** jest tworzona przy pierwszym użyciu usługi Cloud Shell.</span><span class="sxs-lookup"><span data-stu-id="e051b-136">The **cloud-shell-storage-westus** resource group is created the first time you use the Cloud Shell.</span></span> <span data-ttu-id="e051b-137">Grupa zasobów **SampleVM** została utworzona przez polecenie cmdlet `New-AzureRmVM`.</span><span class="sxs-lookup"><span data-stu-id="e051b-137">The **SampleVM** resource group was created by the `New-AzureRmVM` cmdlet.</span></span>

<span data-ttu-id="e051b-138">Jakie inne zasoby zostały utworzone w tej nowej grupie zasobów?</span><span class="sxs-lookup"><span data-stu-id="e051b-138">Now, what other resources were created in this new resource group?</span></span>

```azurepowershell-interactive
Get-AzureRmResource |
  Where ResourceGroupName -eq SampleVM |
    Select-Object ResourceGroupName,Location,ResourceType,Name
```

```output
ResourceGroupName          Location ResourceType                            Name
-----------------          -------- ------------                            ----
SAMPLEVM                   eastus   Microsoft.Compute/disks                 SampleVM_OsDisk_1_9b286c54b168457fa1f8c47...
SampleVM                   eastus   Microsoft.Compute/virtualMachines       SampleVM
SampleVM                   eastus   Microsoft.Network/networkInterfaces     SampleVM
SampleVM                   eastus   Microsoft.Network/networkSecurityGroups SampleVM
SampleVM                   eastus   Microsoft.Network/publicIPAddresses     SampleVM
SampleVM                   eastus   Microsoft.Network/virtualNetworks       SampleVM
```

<span data-ttu-id="e051b-139">Uzyskajmy trochę więcej szczegółowych informacji o maszynie wirtualnej.</span><span class="sxs-lookup"><span data-stu-id="e051b-139">Let's get some more details about the VM.</span></span> <span data-ttu-id="e051b-140">Poniższy przykład pokazuje, jak pobrać informacje o obrazie systemu operacyjnego użytym do utworzenia maszyny wirtualnej.</span><span class="sxs-lookup"><span data-stu-id="e051b-140">This example shows how to retrieve information about the OS Image used to create the VM.</span></span>

```azurepowershell-interactive
Get-AzureRmVM -Name SampleVM -ResourceGroupName SampleVM |
  Select-Object -ExpandProperty StorageProfile |
    Select-Object -ExpandProperty ImageReference
```

```output
Publisher : MicrosoftWindowsServer
Offer     : WindowsServer
Sku       : 2016-Datacenter
Version   : latest
Id        :
```

## <a name="create-a-fully-configured-linux-virtual-machine"></a><span data-ttu-id="e051b-141">Tworzenie w pełni skonfigurowanej maszyny wirtualnej z systemem Linux</span><span class="sxs-lookup"><span data-stu-id="e051b-141">Create a fully configured Linux Virtual Machine</span></span>

<span data-ttu-id="e051b-142">W powyższym przykładzie użyto uproszczonej składni i domyślnych wartości parametrów do utworzenia maszyny wirtualnej z systemem Windows.</span><span class="sxs-lookup"><span data-stu-id="e051b-142">The previous example used the simplified syntax and default parameter values to create a Windows virtual machine.</span></span> <span data-ttu-id="e051b-143">W tym przykładzie podajemy wartości dla wszystkich opcji maszyny wirtualnej.</span><span class="sxs-lookup"><span data-stu-id="e051b-143">In this example, we provide values for all options of the virtual machine.</span></span>

### <a name="create-a-resource-group"></a><span data-ttu-id="e051b-144">Tworzenie grupy zasobów</span><span class="sxs-lookup"><span data-stu-id="e051b-144">Create a resource group</span></span>

<span data-ttu-id="e051b-145">W tym przykładzie chcemy utworzyć grupę zasobów.</span><span class="sxs-lookup"><span data-stu-id="e051b-145">In this example, we want to create a Resource Group.</span></span> <span data-ttu-id="e051b-146">Grupy zasobów na platformie Azure umożliwiają zarządzanie wieloma zasobami, które chcesz logicznie pogrupować razem.</span><span class="sxs-lookup"><span data-stu-id="e051b-146">Resource Groups in Azure provide a way to manage multiple resources that you want to logically group together.</span></span> <span data-ttu-id="e051b-147">Możesz na przykład utworzyć grupę zasobów dla aplikacji lub projektu i dodać do niej maszynę wirtualną, bazę danych i usługę CDN.</span><span class="sxs-lookup"><span data-stu-id="e051b-147">For example, you might create a Resource Group for an application or project and add a virtual machine, a database and a CDN service within it.</span></span>

<span data-ttu-id="e051b-148">Utworzymy grupę zasobów o nazwie „MyResourceGroup” w regionie westeurope świadczenia usługi Azure.</span><span class="sxs-lookup"><span data-stu-id="e051b-148">Let's create a resource group named "MyResourceGroup" in the westeurope region of Azure.</span></span> <span data-ttu-id="e051b-149">W tym celu wpisz następujące polecenie:</span><span class="sxs-lookup"><span data-stu-id="e051b-149">To do so type the following command:</span></span>

```azurepowershell-interactive
New-AzureRmResourceGroup -Name 'myResourceGroup' -Location 'westeurope'
```

```output
ResourceGroupName : myResourceGroup
Location          : westeurope
ProvisioningState : Succeeded
Tags              :
ResourceId        : /subscriptions/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX/resourceGroups/myResourceGroup
```

<span data-ttu-id="e051b-150">W tej nowej grupie zasobów zostaną umieszczone wszystkie zasoby niezbędne dla nowej maszyny wirtualnej, którą utworzymy.</span><span class="sxs-lookup"><span data-stu-id="e051b-150">This new resource group will be used to contain all of the resources needed for the new VM we create.</span></span> <span data-ttu-id="e051b-151">Aby utworzyć nową maszynę wirtualną z systemem Linux, musimy najpierw utworzyć inne wymagane zasoby i przypisać je do konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="e051b-151">To create a new Linux VM, we must first create the other required resources and assign them to a configuration.</span></span> <span data-ttu-id="e051b-152">Następnie możemy użyć tej konfiguracji do utworzenia maszyny wirtualnej.</span><span class="sxs-lookup"><span data-stu-id="e051b-152">Then we can use that configuration to create the VM.</span></span> <span data-ttu-id="e051b-153">Ponadto w katalogu ssh profilu użytkownika musi znajdować się klucz publiczny SSH o nazwie `id_rsa.pub`.</span><span class="sxs-lookup"><span data-stu-id="e051b-153">Also, you will need to have an SSH public key named `id_rsa.pub` in the .ssh directory of your user profile.</span></span>

#### <a name="create-the-required-network-resources"></a><span data-ttu-id="e051b-154">Tworzenie wymaganych zasobów sieciowych</span><span class="sxs-lookup"><span data-stu-id="e051b-154">Create the required network resources</span></span>

<span data-ttu-id="e051b-155">Najpierw musimy utworzyć konfigurację podsieci, która będzie używana w procesie tworzenia sieci wirtualnej.</span><span class="sxs-lookup"><span data-stu-id="e051b-155">First we need to create a subnet configuration to be used with the virtual network creation process.</span></span> <span data-ttu-id="e051b-156">Musimy również utworzyć publiczny adres IP umożliwiający nawiązywanie połączeń z tą maszyną wirtualną.</span><span class="sxs-lookup"><span data-stu-id="e051b-156">We also create a public IP address so that we can connect to this VM.</span></span> <span data-ttu-id="e051b-157">Dostęp do publicznego adresu zostanie zabezpieczony przy użyciu sieciowej grupy zabezpieczeń.</span><span class="sxs-lookup"><span data-stu-id="e051b-157">We create a network security group to secure access to the public address.</span></span> <span data-ttu-id="e051b-158">Na koniec za pomocą wszystkich wymienionych zasobów utworzymy wirtualną kartę sieciową.</span><span class="sxs-lookup"><span data-stu-id="e051b-158">Finally we create the virtual NIC using all of the previous resources.</span></span>

```azurepowershell-interactive
# Variables for common values
$resourceGroup = "myResourceGroup"
$location = "westeurope"
$vmName = "myLinuxVM"

# Definer user name and blank password
$securePassword = ConvertTo-SecureString 'azurepassword' -AsPlainText -Force
$cred = New-Object System.Management.Automation.PSCredential ("azureuser", $securePassword)

# Create a subnet configuration
$subnetConfig = New-AzureRmVirtualNetworkSubnetConfig -Name mySubnet2 -AddressPrefix 192.168.2.0/24

# Create a virtual network
$vnet = New-AzureRmVirtualNetwork -ResourceGroupName $resourceGroup -Location $location `
  -Name MYvNET2 -AddressPrefix 192.168.0.0/16 -Subnet $subnetConfig

# Create a public IP address and specify a DNS name
$publicIp = New-AzureRmPublicIpAddress -ResourceGroupName $resourceGroup -Location $location `
  -Name "mypublicdns$(Get-Random)" -AllocationMethod Static -IdleTimeoutInMinutes 4
$publicIp | Select-Object Name,IpAddress

# Create an inbound network security group rule for port 22
$nsgRuleSSH = New-AzureRmNetworkSecurityRuleConfig -Name myNetworkSecurityGroupRuleSSH  -Protocol Tcp `
  -Direction Inbound -Priority 1000 -SourceAddressPrefix * -SourcePortRange * -DestinationAddressPrefix * `
  -DestinationPortRange 22 -Access Allow

# Create a network security group
$nsg = New-AzureRmNetworkSecurityGroup -ResourceGroupName $resourceGroup -Location $location `
  -Name myNetworkSecurityGroup2 -SecurityRules $nsgRuleSSH

# Create a virtual network card and associate with public IP address and NSG
$nic = New-AzureRmNetworkInterface -Name myNic2 -ResourceGroupName $resourceGroup -Location $location `
  -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $publicIp.Id -NetworkSecurityGroupId $nsg.Id
```

### <a name="create-the-vm-configuration"></a><span data-ttu-id="e051b-159">Tworzenie konfiguracji maszyny wirtualnej</span><span class="sxs-lookup"><span data-stu-id="e051b-159">Create the VM configuration</span></span>

<span data-ttu-id="e051b-160">Teraz, gdy mamy potrzebne zasoby, możemy utworzyć obiekt konfiguracji maszyny wirtualnej.</span><span class="sxs-lookup"><span data-stu-id="e051b-160">Now that we have the required resources we can create the VM configuration object.</span></span>

```azurepowershell-interactive
# Create a virtual machine configuration
$vmConfig = New-AzureRmVMConfig -VMName $vmName -VMSize Standard_D1 |
  Set-AzureRmVMOperatingSystem -Linux -ComputerName $vmName -Credential $cred -DisablePasswordAuthentication |
  Set-AzureRmVMSourceImage -PublisherName Canonical -Offer UbuntuServer -Skus 14.04.2-LTS -Version latest |
  Add-AzureRmVMNetworkInterface -Id $nic.Id

# Configure SSH Keys
$sshPublicKey = Get-Content -Raw "$env:USERPROFILE\.ssh\id_rsa.pub"
Add-AzureRmVMSshPublicKey -VM $vmConfig -KeyData $sshPublicKey -Path "/home/azureuser/.ssh/authorized_keys"
```

### <a name="create-the-virtual-machine"></a><span data-ttu-id="e051b-161">Tworzenie maszyny wirtualnej</span><span class="sxs-lookup"><span data-stu-id="e051b-161">Create the virtual machine</span></span>

<span data-ttu-id="e051b-162">Teraz możemy utworzyć maszynę wirtualną za pomocą obiektu konfiguracji maszyny wirtualnej.</span><span class="sxs-lookup"><span data-stu-id="e051b-162">Now we can create the VM using the VM configuration object.</span></span>

```azurepowershell-interactive
New-AzureRmVM -ResourceGroupName $resourceGroup -Location $location -VM $vmConfig
```

<span data-ttu-id="e051b-163">Teraz, gdy maszyna wirtualna została już utworzona, możesz zalogować się do swojej nowej maszyny wirtualnej z systemem Linux przy użyciu protokołu SSH i publicznego adresu IP utworzonej maszyny wirtualnej:</span><span class="sxs-lookup"><span data-stu-id="e051b-163">Now that the VM has been created, you can sign in to your new Linux VM using SSH with the public IP address of the VM you created:</span></span>

```bash
ssh xx.xxx.xxx.xxx
```

```output
Welcome to Ubuntu 14.04.4 LTS (GNU/Linux 3.19.0-65-generic x86_64)

 * Documentation:  https://help.ubuntu.com/

  System information as of Sun Feb 19 00:32:28 UTC 2017

  System load: 0.31              Memory usage: 3%   Processes:       89
  Usage of /:  39.6% of 1.94GB   Swap usage:   0%   Users logged in: 0

  Graph this data and manage this system at:
    https://landscape.canonical.com/

  Get cloud support with Ubuntu Advantage Cloud Guest:
    http://www.ubuntu.com/business/services/cloud

0 packages can be updated.
0 updates are security updates.



The programs included with the Ubuntu system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Ubuntu comes with ABSOLUTELY NO WARRANTY, to the extent permitted by
applicable law.

my-login@MyLinuxVM:../../..$
```

## <a name="creating-other-resources-in-azure"></a><span data-ttu-id="e051b-164">Tworzenie innych zasobów na platformie Azure</span><span class="sxs-lookup"><span data-stu-id="e051b-164">Creating other resources in Azure</span></span>

<span data-ttu-id="e051b-165">Omówiliśmy sposób tworzenia grupy zasobów, maszyny wirtualnej z systemem Linux i maszyny wirtualnej z systemem Windows Server.</span><span class="sxs-lookup"><span data-stu-id="e051b-165">We've now walked through how to create a Resource Group, a Linux VM, and a Windows Server VM.</span></span> <span data-ttu-id="e051b-166">Możesz również utworzyć wiele innych typów zasobów platformy Azure.</span><span class="sxs-lookup"><span data-stu-id="e051b-166">You can create many other types of Azure resources as well.</span></span>

<span data-ttu-id="e051b-167">Aby na przykład utworzyć moduł równoważenia obciążenia sieci platformy Azure, który można będzie potem skojarzyć z nowo utworzonymi maszynami wirtualnymi, możemy użyć następującego polecenia create:</span><span class="sxs-lookup"><span data-stu-id="e051b-167">For example, to create an Azure Network Load Balancer that we could then associate with our newly created VMs, we can use the following create command:</span></span>

```azurepowershell-interactive
New-AzureRmLoadBalancer -Name MyLoadBalancer -ResourceGroupName myResourceGroup -Location westeurope
```

<span data-ttu-id="e051b-168">Możemy także utworzyć nową prywatną sieć wirtualną (nazywaną „VNet” na platformie Azure) dla naszej infrastruktury, korzystając z następującego polecenia:</span><span class="sxs-lookup"><span data-stu-id="e051b-168">We could also create a new private Virtual Network (commonly referred to as a "VNet" within Azure) for our infrastructure using the following command:</span></span>

```azurepowershell-interactive
$subnetConfig = New-AzureRmVirtualNetworkSubnetConfig -Name mySubnet2 -AddressPrefix 10.0.0.0/16
$vnet = New-AzureRmVirtualNetwork -ResourceGroupName myResourceGroup -Location westeurope `
  -Name MYvNET3 -AddressPrefix 10.0.0.0/16 -Subnet $subnetConfig
```

<span data-ttu-id="e051b-169">Tym, co sprawia, że platforma Azure i program Azure PowerShell są tak przydatne, jest to, że możemy ich używać nie tylko do uzyskiwania infrastruktury opartej na chmurze, ale również do tworzenia zarządzanych usług platformy.</span><span class="sxs-lookup"><span data-stu-id="e051b-169">What makes Azure and the Azure PowerShell powerful is that we can use it not just to get cloud-based infrastructure but also to create managed platform services.</span></span> <span data-ttu-id="e051b-170">Zarządzane usługi platformy można również łączyć z infrastrukturą w celu tworzenia jeszcze bardziej zaawansowanych rozwiązań.</span><span class="sxs-lookup"><span data-stu-id="e051b-170">The managed platform services can also be combined with infrastructure to build even more powerful solutions.</span></span>

<span data-ttu-id="e051b-171">Możesz na przykład użyć programu Azure PowerShell do utworzenia usługi Azure App Service.</span><span class="sxs-lookup"><span data-stu-id="e051b-171">For example, you can use the Azure PowerShell to create an Azure AppService.</span></span> <span data-ttu-id="e051b-172">Usługa Azure App Service to zarządzana usługa platformy, która zapewnia doskonały sposób hostowania aplikacji internetowych bez konieczności troszczenia się o infrastrukturę.</span><span class="sxs-lookup"><span data-stu-id="e051b-172">Azure AppService is a managed platform service that provides a great way to host web apps without having to worry about infrastructure.</span></span> <span data-ttu-id="e051b-173">Po utworzeniu usługi Azure App Service możesz utworzyć dwie nowe aplikacje Azure Web Apps w ramach usługi App Service, korzystając z następujących poleceń:</span><span class="sxs-lookup"><span data-stu-id="e051b-173">After creating the Azure AppService, you can create two new Azure Web Apps within the AppService using the following commands:</span></span>

```azurepowershell-interactive
# Create an Azure AppService that we can host any number of web apps within
New-AzureRmAppServicePlan -Name MyAppServicePlan -Tier Basic -NumberofWorkers 2 -WorkerSize Small -ResourceGroupName myResourceGroup -Location westeurope

# Create Two Web Apps within the AppService (note: name param must be a unique DNS entry)
New-AzureRmWebApp -Name MyWebApp43432 -AppServicePlan MyAppServicePlan -ResourceGroupName myResourceGroup -Location westeurope
New-AzureRmWebApp -Name MyWebApp43433 -AppServicePlan MyAppServicePlan -ResourceGroupName myResourceGroup -Location westeurope
```

## <a name="listing-deployed-resources"></a><span data-ttu-id="e051b-174">Wyświetlanie listy wdrożonych zasobów</span><span class="sxs-lookup"><span data-stu-id="e051b-174">Listing deployed resources</span></span>

<span data-ttu-id="e051b-175">Listę zasobów uruchomionych na platformie Azure można wyświetlić za pomocą polecenia cmdlet `Get-AzureRmResource`.</span><span class="sxs-lookup"><span data-stu-id="e051b-175">You can use the `Get-AzureRmResource` cmdlet to list the resources running in Azure.</span></span> <span data-ttu-id="e051b-176">W poniższym przykładzie zostaną wyświetlone zasoby utworzone w nowej grupie zasobów.</span><span class="sxs-lookup"><span data-stu-id="e051b-176">The following example shows the resources we created in the new resource group.</span></span>

```azurepowershell-interactive
Get-AzureRmResource |
  Where-Object ResourceGroupName -eq myResourceGroup |
    Select-Object Name,Location,ResourceType
```

```output
Name                                                  Location   ResourceType
----                                                  --------   ------------
myLinuxVM_OsDisk_1_36ca038791f642ba91270879088c249a   westeurope Microsoft.Compute/disks
myWindowsVM_OsDisk_1_f627e6e2bb454c72897d72e9632adf9a westeurope Microsoft.Compute/disks
myLinuxVM                                             westeurope Microsoft.Compute/virtualMachines
myWindowsVM                                           westeurope Microsoft.Compute/virtualMachines
myWindowsVM/BGInfo                                    westeurope Microsoft.Compute/virtualMachines/extensions
myNic1                                                westeurope Microsoft.Network/networkInterfaces
myNic2                                                westeurope Microsoft.Network/networkInterfaces
myNetworkSecurityGroup1                               westeurope Microsoft.Network/networkSecurityGroups
myNetworkSecurityGroup2                               westeurope Microsoft.Network/networkSecurityGroups
mypublicdns245369171                                  westeurope Microsoft.Network/publicIPAddresses
mypublicdns779537141                                  westeurope Microsoft.Network/publicIPAddresses
MYvNET1                                               westeurope Microsoft.Network/virtualNetworks
MYvNET2                                               westeurope Microsoft.Network/virtualNetworks
micromyresomywi032907510                              westeurope Microsoft.Storage/storageAccounts
```

## <a name="deleting-resources"></a><span data-ttu-id="e051b-177">Usuwanie zasobów</span><span class="sxs-lookup"><span data-stu-id="e051b-177">Deleting resources</span></span>

<span data-ttu-id="e051b-178">Wyczyszczenie konta platformy Azure polega na usunięciu zasobów utworzonych w tym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="e051b-178">To clean up your Azure account, you want to remove the resources we created in this example.</span></span> <span data-ttu-id="e051b-179">Aby usunąć zasoby, które nie są już potrzebne, możesz użyć poleceń cmdlet `Remove-AzureRm*`.</span><span class="sxs-lookup"><span data-stu-id="e051b-179">You can use the `Remove-AzureRm*` cmdlets to delete the resources you no longer need.</span></span> <span data-ttu-id="e051b-180">Aby usunąć utworzoną maszynę wirtualną z systemem Windows, użyj następującego polecenia:</span><span class="sxs-lookup"><span data-stu-id="e051b-180">To remove the Windows VM we created, using the following command:</span></span>

```azurepowershell-interactive
Remove-AzureRmVM -Name myWindowsVM -ResourceGroupName myResourceGroup
```

<span data-ttu-id="e051b-181">Pojawi się monit o potwierdzenie usunięcia zasobu.</span><span class="sxs-lookup"><span data-stu-id="e051b-181">You'll be prompted to confirm that you want to remove the resource.</span></span>

```output
Confirm
Are you sure you want to remove resource group 'myResourceGroup'
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): Y
```

<span data-ttu-id="e051b-182">Można także usuwać wiele zasobów jednocześnie.</span><span class="sxs-lookup"><span data-stu-id="e051b-182">You can also delete many resources at once.</span></span> <span data-ttu-id="e051b-183">Na przykład następujące polecenie pozwala usunąć grupę zasobów „MyResourceGroup”, która była używana we wszystkich dotychczasowych przykładach.</span><span class="sxs-lookup"><span data-stu-id="e051b-183">For example, the following command deletes the resource group "MyResourceGroup" that we've used for all the samples so far.</span></span>
<span data-ttu-id="e051b-184">Zostaną również usunięte wszystkie zasoby w grupie.</span><span class="sxs-lookup"><span data-stu-id="e051b-184">All resources in the group are also deleted.</span></span>

```azurepowershell-interactive
Remove-AzureRmResourceGroup -Name myResourceGroup
```

```output
Confirm
Are you sure you want to remove resource group 'myResourceGroup'
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): Y
```

<span data-ttu-id="e051b-185">W zależności od liczby i typu zasobów wykonanie tego zadania może potrwać kilka minut.</span><span class="sxs-lookup"><span data-stu-id="e051b-185">The task can take several minutes to complete, depending on the number and type of resources.</span></span>

## <a name="get-samples"></a><span data-ttu-id="e051b-186">Pobieranie przykładów</span><span class="sxs-lookup"><span data-stu-id="e051b-186">Get samples</span></span>

<span data-ttu-id="e051b-187">Aby dowiedzieć się więcej o sposobach używania programu Azure PowerShell, zapoznaj się z naszymi najbardziej typowymi skryptami dla [maszyn wirtualnych z systemem Linux](/azure/virtual-machines/virtual-machines-linux-powershell-samples?toc=%2fpowershell%2fazure%%2ftoc.json), [maszyn wirtualnych z systemem Windows](/azure/virtual-machines/virtual-machines-windows-powershell-samples?toc=%2fpowershell%2fazure%%2ftoc.json), [aplikacji internetowych](/azure/app-service-web/app-service-powershell-samples?toc=%2fpowershell%2fazure%%2ftoc.json) i [baz danych SQL](/azure/sql-database/sql-database-powershell-samples?toc=%2fpowershell%2fazure%%2ftoc.json).</span><span class="sxs-lookup"><span data-stu-id="e051b-187">To learn more about ways to use the Azure PowerShell, check out our most common scripts for [Linux VMs](/azure/virtual-machines/virtual-machines-linux-powershell-samples?toc=%2fpowershell%2fazure%%2ftoc.json), [Windows VMs](/azure/virtual-machines/virtual-machines-windows-powershell-samples?toc=%2fpowershell%2fazure%%2ftoc.json), [Web Apps](/azure/app-service-web/app-service-powershell-samples?toc=%2fpowershell%2fazure%%2ftoc.json), and [SQL Databases](/azure/sql-database/sql-database-powershell-samples?toc=%2fpowershell%2fazure%%2ftoc.json).</span></span>

## <a name="next-steps"></a><span data-ttu-id="e051b-188">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="e051b-188">Next steps</span></span>

* [<span data-ttu-id="e051b-189">Logowanie się w programie Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="e051b-189">Sign in with Azure PowerShell</span></span>](authenticate-azureps.md)
* [<span data-ttu-id="e051b-190">Zarządzanie subskrypcjami platformy Azure za pomocą programu Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="e051b-190">Manage Azure subscriptions with Azure PowerShell</span></span>](manage-subscriptions-azureps.md)
* [<span data-ttu-id="e051b-191">Tworzenie jednostek usługi na platformie Azure przy użyciu programu Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="e051b-191">Create service principals in Azure using Azure PowerShell</span></span>](create-azure-service-principal-azureps.md)
* <span data-ttu-id="e051b-192">Przeczytaj informacje o wersji dotyczące migracji ze starszej wersji: [https://github.com/Azure/azure-powershell/tree/dev/documentation/release-notes](https://github.com/Azure/azure-powershell/tree/dev/documentation/release-notes).</span><span class="sxs-lookup"><span data-stu-id="e051b-192">Read the release notes about migrating from an older release: [https://github.com/Azure/azure-powershell/tree/dev/documentation/release-notes](https://github.com/Azure/azure-powershell/tree/dev/documentation/release-notes).</span></span>
* <span data-ttu-id="e051b-193">Uzyskiwanie pomocy od społeczności:</span><span class="sxs-lookup"><span data-stu-id="e051b-193">Get help from the community:</span></span>
  * [<span data-ttu-id="e051b-194">Forum platformy Azure w witrynie MSDN</span><span class="sxs-lookup"><span data-stu-id="e051b-194">Azure forum on MSDN</span></span>](http://go.microsoft.com/fwlink/p/?LinkId=320212)
  * [<span data-ttu-id="e051b-195">Witryna Stackoverflow</span><span class="sxs-lookup"><span data-stu-id="e051b-195">stackoverflow</span></span>](http://go.microsoft.com/fwlink/?LinkId=320213)