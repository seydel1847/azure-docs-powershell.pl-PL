---
title: Instalowanie i konfigurowanie programu Azure PowerShell | Microsoft Docs
description: "Jak zainstalować i skonfigurować program Azure PowerShell do pierwszego użycia."
services: azure
author: sdwheeler
ms.author: sewhee
manager: carmonm
ms.product: azure
ms.service: azure-powershell
ms.devlang: powershell
ms.topic: conceptual
ms.date: 08/31/2017
ms.openlocfilehash: 0e560332c87fdcc8b7365f2271de24481003a4d6
ms.sourcegitcommit: b256bf48e15ee98865de0fae50e7b81878b03a54
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/03/2017
---
# <a name="install-and-configure-azure-powershell"></a><span data-ttu-id="68f50-103">Instalowanie i konfigurowanie programu Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="68f50-103">Install and configure Azure PowerShell</span></span>

<span data-ttu-id="68f50-104">W tym artykule opisano kroki instalowania modułów programu Azure PowerShell w środowisku systemu Windows.</span><span class="sxs-lookup"><span data-stu-id="68f50-104">This article explains the steps to install the Azure PowerShell modules in a Windows environment.</span></span>
<span data-ttu-id="68f50-105">Jeśli chcesz korzystać z programu Azure PowerShell w systemie macOS lub Linux, zobacz następujący artykuł: [Instalowanie i konfigurowanie programu Azure PowerShell w systemach macOS i Linux](install-azurermps-maclinux.md).</span><span class="sxs-lookup"><span data-stu-id="68f50-105">If you want to use Azure PowerShell on macOS or Linux, see the following article: [Install and configure Azure PowerShell on macOS and Linux](install-azurermps-maclinux.md).</span></span>

<span data-ttu-id="68f50-106">Instalowanie programu Azure PowerShell z Galerii programu PowerShell jest preferowaną metodą instalacji.</span><span class="sxs-lookup"><span data-stu-id="68f50-106">Installing Azure PowerShell from the PowerShell Gallery is the preferred method of installation.</span></span>

## <a name="step-1-install-powershellget"></a><span data-ttu-id="68f50-107">Krok 1. Zainstaluj moduł PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="68f50-107">Step 1: Install PowerShellGet</span></span>

<span data-ttu-id="68f50-108">Instalowanie elementów z Galerii programu PowerShell wymaga modułu PowerShellGet.</span><span class="sxs-lookup"><span data-stu-id="68f50-108">Installing items from the PowerShell Gallery requires the PowerShellGet module.</span></span> <span data-ttu-id="68f50-109">Upewnij się, że masz odpowiednią wersję modułu PowerShellGet oraz spełnione inne wymagania systemowe.</span><span class="sxs-lookup"><span data-stu-id="68f50-109">Make sure you have the appropriate version of PowerShellGet and other system requirements.</span></span> <span data-ttu-id="68f50-110">Uruchom następujące polecenie, aby sprawdzić, czy w Twoim systemie został zainstalowany moduł PowerShellGet.</span><span class="sxs-lookup"><span data-stu-id="68f50-110">Run the following command to see if you have PowerShellGet installed on your system.</span></span>

```powershell
Get-Module PowerShellGet -list | Select-Object Name,Version,Path
```

<span data-ttu-id="68f50-111">Powinny zostać wyświetlone dane wyjściowe podobne do poniższych:</span><span class="sxs-lookup"><span data-stu-id="68f50-111">You should see something similar to the following output:</span></span>

```Output
Name          Version Path
----          ------- ----
PowerShellGet 1.0.0.1 C:\Program Files\WindowsPowerShell\Modules\PowerShellGet\1.0.0.1\PowerShellGet.psd1
```

<span data-ttu-id="68f50-112">Jeśli nie masz zainstalowanego modułu PowerShellGet, zobacz sekcję [Jak uzyskać moduł PowerShellGet](#how-to-get-powershellget) w niniejszym artykule.</span><span class="sxs-lookup"><span data-stu-id="68f50-112">If you do not have PowerShellGet installed, see the [How to get PowerShellGet](#how-to-get-powershellget) section of this article.</span></span>

> [!NOTE]
> <span data-ttu-id="68f50-113">Korzystanie z modułu PowerShellGet wymaga zasad wykonania pozwalających uruchamiać skrypty.</span><span class="sxs-lookup"><span data-stu-id="68f50-113">Using PowerShellGet requires an Execution Policy that allows you to run scripts.</span></span> <span data-ttu-id="68f50-114">Aby uzyskać więcej informacji na temat zasad wykonania programu PowerShell, zobacz [Informacje o zasadach wykonania](/powershell/module/microsoft.powershell.core/about/about_execution_policies).</span><span class="sxs-lookup"><span data-stu-id="68f50-114">For more information about PowerShell's Execution Policy, see [About Execution Policies](/powershell/module/microsoft.powershell.core/about/about_execution_policies).</span></span>

## <a name="step-2-install-azure-powershell"></a><span data-ttu-id="68f50-115">Krok 2. Zainstaluj program Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="68f50-115">Step 2: Install Azure PowerShell</span></span>

<span data-ttu-id="68f50-116">Instalacja programu Azure PowerShell z Galerii programu PowerShell wymaga podniesionych uprawnień.</span><span class="sxs-lookup"><span data-stu-id="68f50-116">Installing Azure PowerShell from the PowerShell Gallery requires elevated privileges.</span></span> <span data-ttu-id="68f50-117">Uruchom następujące polecenie z sesji programu PowerShell z podwyższonym poziomem uprawnień:</span><span class="sxs-lookup"><span data-stu-id="68f50-117">Run the following command from an elevated PowerShell session:</span></span>

```powershell
# Install the Azure Resource Manager modules from the PowerShell Gallery
Install-Module AzureRM -AllowClobber
```

<span data-ttu-id="68f50-118">Galeria programu PowerShell domyślnie nie jest skonfigurowana jako zaufane repozytorium modułu PowerShellGet.</span><span class="sxs-lookup"><span data-stu-id="68f50-118">By default, the PowerShell gallery is not configured as a Trusted repository for PowerShellGet.</span></span> <span data-ttu-id="68f50-119">Po pierwszym użyciu Galerii programu PowerShell zostanie wyświetlony następujący komunikat:</span><span class="sxs-lookup"><span data-stu-id="68f50-119">The first time you use the PSGallery you see the following prompt:</span></span>

```Output
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the Set-PSRepository cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"): Y
```

<span data-ttu-id="68f50-120">Wybierz odpowiedź „Tak” lub „Tak na wszystkie”, aby kontynuować instalację.</span><span class="sxs-lookup"><span data-stu-id="68f50-120">Answer 'Yes' or 'Yes to All' to continue with the installation.</span></span>

> [!NOTE]
> <span data-ttu-id="68f50-121">Jeśli masz wersję pakietu NuGet starszą niż 2.8.5.201, zostanie wyświetlony monit o pobranie i zainstalowanie najnowszej wersji pakietu NuGet.</span><span class="sxs-lookup"><span data-stu-id="68f50-121">If you have a version older than 2.8.5.201 of NuGet, you are prompted to download and install the latest version of NuGet.</span></span>

<span data-ttu-id="68f50-122">Moduł AzureRM to zbiorczy moduł poleceń cmdlet usługi Azure Resource Manager.</span><span class="sxs-lookup"><span data-stu-id="68f50-122">The AzureRM module is a rollup module for the Azure Resource Manager cmdlets.</span></span> <span data-ttu-id="68f50-123">Po zainstalowaniu modułu AzureRM każdy moduł programu Azure PowerShell, który nie został wcześniej zainstalowany, zostanie pobrany i zainstalowany z Galerii programu PowerShell.</span><span class="sxs-lookup"><span data-stu-id="68f50-123">When you install the AzureRM module, any Azure PowerShell module not previously installed is downloaded and from the PowerShell Gallery.</span></span>

<span data-ttu-id="68f50-124">Jeśli masz zainstalowaną poprzednią wersję programu Azure PowerShell, może wystąpić błąd.</span><span class="sxs-lookup"><span data-stu-id="68f50-124">If you have a previous version of Azure PowerShell installed you may receive an error.</span></span> <span data-ttu-id="68f50-125">Aby rozwiązać ten problem, zobacz [Aktualizowanie do nowej wersji programu Azure PowerShell](#update-azps) w dalszej części tego artykułu.</span><span class="sxs-lookup"><span data-stu-id="68f50-125">To resolve this issue, see the [Updating to a new version of Azure PowerShell](#update-azps) section of this article.</span></span>

## <a name="step-3-load-the-azurerm-module"></a><span data-ttu-id="68f50-126">Krok 3. Załaduj moduł AzureRM</span><span class="sxs-lookup"><span data-stu-id="68f50-126">Step 3: Load the AzureRM module</span></span>
<span data-ttu-id="68f50-127">Gdy moduł jest zainstalowany, musisz załadować moduł do swojej sesji programu PowerShell.</span><span class="sxs-lookup"><span data-stu-id="68f50-127">Once the module is installed, you need to load the module into your PowerShell session.</span></span> <span data-ttu-id="68f50-128">Należy to zrobić w ramach normalnej sesji programu PowerShell (bez podwyższonego poziomu uprawnień).</span><span class="sxs-lookup"><span data-stu-id="68f50-128">You should do this in a normal (non-elevated) PowerShell session.</span></span> <span data-ttu-id="68f50-129">Moduły są w następujący sposób ładowane przy użyciu polecenia cmdlet `Import-Module`:</span><span class="sxs-lookup"><span data-stu-id="68f50-129">Modules are loaded using the `Import-Module` cmdlet, as follows:</span></span>

```powershell
Import-Module AzureRM
```

## <a name="next-steps"></a><span data-ttu-id="68f50-130">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="68f50-130">Next Steps</span></span>

<span data-ttu-id="68f50-131">Aby uzyskać więcej informacji o korzystaniu z programu Azure PowerShell, zobacz następujące artykuły:</span><span class="sxs-lookup"><span data-stu-id="68f50-131">For more information about using Azure PowerShell, see the following articles:</span></span>

* [<span data-ttu-id="68f50-132">Rozpoczynanie pracy z programem Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="68f50-132">Get started with Azure PowerShell</span></span>](get-started-azureps.md)

## <a name="reporting-issues-and-feedback"></a><span data-ttu-id="68f50-133">Zgłaszanie problemów i przesyłanie opinii</span><span class="sxs-lookup"><span data-stu-id="68f50-133">Reporting issues and feedback</span></span>

<span data-ttu-id="68f50-134">Jeśli występują jakiekolwiek problemy związane z narzędziem, prześlij zgłoszenie do sekcji [Problemy](https://github.com/Azure/azure-powershell/issues) repozytorium GitHub.</span><span class="sxs-lookup"><span data-stu-id="68f50-134">If you encounter any bugs with the tool, file an issue in the [Issues](https://github.com/Azure/azure-powershell/issues) section of our GitHub repo.</span></span> <span data-ttu-id="68f50-135">Aby przekazać opinię z wiersza polecenia, użyj polecenia cmdlet `Send-Feedback`.</span><span class="sxs-lookup"><span data-stu-id="68f50-135">To provide feedback from the command line, use the `Send-Feedback` cmdlet.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="68f50-136">Często zadawane pytania</span><span class="sxs-lookup"><span data-stu-id="68f50-136">Frequently asked questions</span></span>

### <a name="how-to-get-powershellget"></a><span data-ttu-id="68f50-137">Jak uzyskać moduł PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="68f50-137">How to get PowerShellGet</span></span>

|<span data-ttu-id="68f50-138">Wersja systemu operacyjnego</span><span class="sxs-lookup"><span data-stu-id="68f50-138">OS Version</span></span>|<span data-ttu-id="68f50-139">Instrukcje dotyczące instalacji</span><span class="sxs-lookup"><span data-stu-id="68f50-139">Install instructions</span></span>|
|---|---|
|<span data-ttu-id="68f50-140">Mam system Windows 10 lub Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="68f50-140">I have Windows 10 or Windows Server 2016</span></span>|<span data-ttu-id="68f50-141">Wbudowane w platformę Windows Management Framework (WMF) 5.0 zawartą w systemie operacyjnym</span><span class="sxs-lookup"><span data-stu-id="68f50-141">Built into Windows Management Framework (WMF) 5.0 included in the OS</span></span>|
|<span data-ttu-id="68f50-142">Chcę przeprowadzić uaktualnienie do programu PowerShell 5</span><span class="sxs-lookup"><span data-stu-id="68f50-142">I want to upgrade to PowerShell 5</span></span>|[<span data-ttu-id="68f50-143">Zainstaluj najnowszą wersję platformy WMF</span><span class="sxs-lookup"><span data-stu-id="68f50-143">Install the latest version of WMF</span></span>](https://www.microsoft.com/en-us/download/details.aspx?id=54616)|
|<span data-ttu-id="68f50-144">Używam wersji systemu Windows mającej program PowerShell 3 lub 4</span><span class="sxs-lookup"><span data-stu-id="68f50-144">I am running on a version of Windows with PowerShell 3 or PowerShell 4</span></span>|[<span data-ttu-id="68f50-145">Pobierz moduły PackageManagement</span><span class="sxs-lookup"><span data-stu-id="68f50-145">Get the PackageManagement modules</span></span>](http://go.microsoft.com/fwlink/?LinkID=746217)|

<a id="helpmechoose"></a>
### <a name="checking-the-version-of-azure-powershell"></a><span data-ttu-id="68f50-146">Sprawdzanie wersji programu Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="68f50-146">Checking the version of Azure PowerShell</span></span>

<span data-ttu-id="68f50-147">Chociaż zachęcamy do jak najszybszego uaktualnienia do najnowszej wersji, różne wersje programu Azure PowerShell są nadal obsługiwane.</span><span class="sxs-lookup"><span data-stu-id="68f50-147">Although we encourage you to upgrade to the latest version as early as possible, several versions of Azure PowerShell are supported.</span></span> <span data-ttu-id="68f50-148">Aby ustalić zainstalowaną wersję programu Azure PowerShell, uruchom polecenie `Get-Module AzureRM` z wiersza polecenia.</span><span class="sxs-lookup"><span data-stu-id="68f50-148">To determine the version of Azure PowerShell you have installed, run `Get-Module AzureRM` from your command line.</span></span>

```powershell
Get-Module AzureRM -list | Select-Object Name,Version,Path
```

### <a name="support-for-classic-deployment-methods"></a><span data-ttu-id="68f50-149">Obsługa klasycznych metod wdrażania</span><span class="sxs-lookup"><span data-stu-id="68f50-149">Support for classic deployment methods</span></span>

<span data-ttu-id="68f50-150">Jeśli masz wdrożenia korzystające z klasycznego modelu wdrażania, możesz zainstalować wersję zarządzania usługą programu Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="68f50-150">If you have deployments that use the classic deployment model you can install the Service Management version of Azure PowerShell.</span></span> <span data-ttu-id="68f50-151">Aby uzyskać więcej informacji, zobacz [Instalowanie modułu zarządzania usługami programu Azure PowerShell](/powershell/azure/servicemanagement/install-azure-ps).</span><span class="sxs-lookup"><span data-stu-id="68f50-151">For more information, see [Install the Azure PowerShell Service Management module](/powershell/azure/servicemanagement/install-azure-ps).</span></span> <span data-ttu-id="68f50-152">Moduły Azure i AzureRM mają wspólne zależności.</span><span class="sxs-lookup"><span data-stu-id="68f50-152">The Azure and AzureRM modules share common dependencies.</span></span> <span data-ttu-id="68f50-153">Jeśli korzystasz z modułów Azure i AzureRM, należy zainstalować tę samą wersję każdego pakietu.</span><span class="sxs-lookup"><span data-stu-id="68f50-153">If you use both the Azure and AzureRM modules, you should install the same version of each package.</span></span>

### <span data-ttu-id="68f50-154"><a id="update-azps"></a>Aktualizowanie do nowej wersji programu Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="68f50-154"><a id="update-azps"></a>Updating to a new version of Azure PowerShell</span></span>

<span data-ttu-id="68f50-155">Jeśli masz zainstalowaną poprzednią wersję programu Azure PowerShell obejmującą moduł zarządzania usługami, może wystąpić następujący błąd:</span><span class="sxs-lookup"><span data-stu-id="68f50-155">If you have a previous version of Azure PowerShell installed that includes the Service Management module, you may receive the following error:</span></span>

```Output
PackageManagement\Install-Package : A command with name 'Get-AzureStorageContainerAcl' is already
available on this system. This module 'Azure.Storage' may override the existing commands. If you
still want to install this module 'Azure.Storage', use -AllowClobber parameter.

At C:\Program Files\WindowsPowerShell\Modules\PowerShellGet\1.0.0.1\PSModule.psm1:1772 char:21
+ ...          $null = PackageManagement\Install-Package @PSBoundParameters
+                      ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (Microsoft.Power....InstallPackage:InstallPackage) [Install-Package], Exception
    + FullyQualifiedErrorId : CommandAlreadyAvailable,Validate-ModuleCommandAlreadyAvailable,Microsoft.PowerShell.PackageManagement.Cmdlets.InstallPackage
```

<span data-ttu-id="68f50-156">Zgodnie z treścią komunikatu o błędzie trzeba zainstalować moduł, podając parametr -AllowClobber.</span><span class="sxs-lookup"><span data-stu-id="68f50-156">As the error message states, you need to use the -AllowClobber parameter to install the module.</span></span> <span data-ttu-id="68f50-157">Użyj następującego polecenia:</span><span class="sxs-lookup"><span data-stu-id="68f50-157">Use the following command:</span></span>

```powershell
# Install the Azure Resource Manager modules from the PowerShell Gallery
Install-Module AzureRM -AllowClobber
```

<span data-ttu-id="68f50-158">Aby uzyskać więcej informacji, zobacz temat pomocy dotyczący parametru [Install-Module](https://msdn.microsoft.com/powershell/reference/5.1/PowerShellGet/install-module).</span><span class="sxs-lookup"><span data-stu-id="68f50-158">For more information, see the help topic for [Install-Module](https://msdn.microsoft.com/powershell/reference/5.1/PowerShellGet/install-module).</span></span>

### <a name="installing-module-versions-side-by-side"></a><span data-ttu-id="68f50-159">Instalowanie wersji modułu obok siebie</span><span class="sxs-lookup"><span data-stu-id="68f50-159">Installing module versions side by side</span></span>

<span data-ttu-id="68f50-160">Metoda instalacji PowerShellGet jest jedyną metodą, która obsługuje instalowanie wielu wersji.</span><span class="sxs-lookup"><span data-stu-id="68f50-160">The PowerShellGet method of installation is the only method that supports the installation of multiple versions.</span></span> <span data-ttu-id="68f50-161">Na przykład możesz mieć skrypty napisane przy użyciu poprzedniej wersji programu Azure PowerShell, do aktualizacji której nie masz czasu lub zasobów.</span><span class="sxs-lookup"><span data-stu-id="68f50-161">For example, you may have scripts written using a previous version of Azure PowerShell that you don't have the time or resources to updated.</span></span> <span data-ttu-id="68f50-162">Następujące polecenia przedstawiają sposób instalowania wielu wersji programu Azure PowerShell:</span><span class="sxs-lookup"><span data-stu-id="68f50-162">The following commands illustrate how to install multiple versions of Azure PowerShell:</span></span>

```powershell
Install-Module -Name AzureRM -RequiredVersion 3.7.0
Install-Module -Name AzureRM -RequiredVersion 1.2.9
```

<span data-ttu-id="68f50-163">Tylko jedna wersja modułu może zostać załadowana w sesji programu PowerShell.</span><span class="sxs-lookup"><span data-stu-id="68f50-163">Only one version of the module can be loaded in a PowerShell session.</span></span> <span data-ttu-id="68f50-164">Musisz otworzyć nowe okno programu PowerShell i użyć polecenia `Import-Module`, aby zaimportować określoną wersję poleceń cmdlet modułu AzureRM:</span><span class="sxs-lookup"><span data-stu-id="68f50-164">You must open a new PowerShell window and use `Import-Module` to import a specific version of the AzureRM cmdlets:</span></span>

```powershell
Import-Module AzureRM -RequiredVersion 1.2.9
```

> [!NOTE]
> <span data-ttu-id="68f50-165">Wersja 2.1.0 i wersja 1.2.6 to pierwsze wersje modułu przeznaczone do instalacji i używania obok siebie.</span><span class="sxs-lookup"><span data-stu-id="68f50-165">Version 2.1.0 and version 1.2.6 are the first module versions designed to be installed and used side by side.</span></span> <span data-ttu-id="68f50-166">Załadowanie starszej wersji programu Azure PowerShell powoduje załadowanie niezgodnych wersji modułu **AzureRM.Profile**.</span><span class="sxs-lookup"><span data-stu-id="68f50-166">When loading an earlier version of the Azure PowerShell, incompatible versions of the **AzureRM.Profile** module are loaded.</span></span> <span data-ttu-id="68f50-167">W wyniku tego każde wykonanie polecenia cmdlet powoduje wyświetlenie polecenia cmdlet z monitem o zalogowanie się.</span><span class="sxs-lookup"><span data-stu-id="68f50-167">This results in the cmdlets prompting you to log in whenever you execute a cmdlet.</span></span>

### <a name="other-installation-methods"></a><span data-ttu-id="68f50-168">Inne metody instalacji</span><span class="sxs-lookup"><span data-stu-id="68f50-168">Other installation methods</span></span>

<span data-ttu-id="68f50-169">Aby uzyskać informacje o instalowaniu za pomocą Instalatora platformy sieci Web lub pakietu MSI, zobacz [Inne metody instalacji](other-install.md)</span><span class="sxs-lookup"><span data-stu-id="68f50-169">For information about installing using the Web Platform Installer or the MSI Package, see [Other installation methods](other-install.md)</span></span>