---
title: Inne metody instalacji programu Azure PowerShell
description: Jak zainstalować program Azure PowerShell bez modułu PowerShellGet za pomocą instalatora MSI
author: sptramer
ms.author: sttramer
manager: carmonm
ms.devlang: powershell
ms.topic: conceptual
ms.date: 09/11/2018
ms.openlocfilehash: 52bcbe3f91600c96546c7d8ff5648977a7917ff9
ms.sourcegitcommit: 5f946a535eccca0b3ddf3db8f617b32564a88938
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/25/2018
ms.locfileid: "50001715"
---
# <a name="install-azure-powershell-on-windows-with-msi"></a><span data-ttu-id="252bc-103">Instalowanie programu Azure PowerShell w systemie Windows za pomocą instalatora MSI</span><span class="sxs-lookup"><span data-stu-id="252bc-103">Install Azure PowerShell on Windows with MSI</span></span>

<span data-ttu-id="252bc-104">W tym artykule opisano sposób instalowania programu Azure PowerShell w systemie Windows przy użyciu instalatora MSI.</span><span class="sxs-lookup"><span data-stu-id="252bc-104">This article explains how to install Azure PowerShell on Windows using an MSI installer.</span></span>  
<span data-ttu-id="252bc-105">Tych metod instalacji należy używać tylko wtedy, gdy są one niezbędne w danym systemie.</span><span class="sxs-lookup"><span data-stu-id="252bc-105">Use these installation methods only if they're necessary for your system.</span></span> <span data-ttu-id="252bc-106">Zalecaną metodą instalacji programu Azure PowerShell w systemie Windows jest moduł PowerShellGet.</span><span class="sxs-lookup"><span data-stu-id="252bc-106">The recommended way to install Azure PowerShell on Windows is with PowerShellGet.</span></span> <span data-ttu-id="252bc-107">Aby uzyskać instrukcje dotyczące instalowania programu Azure PowerShell przy użyciu modułu PowerShellGet, zobacz [Instalowanie programu Azure PowerShell za pomocą modułu PowerShellGet](install-azurerm-ps.md).</span><span class="sxs-lookup"><span data-stu-id="252bc-107">For instructions on using PowerShellGet to install Azure PowerShell, see [Install Azure PowerShell with PowerShellGet](install-azurerm-ps.md).</span></span>

> [!NOTE]
> <span data-ttu-id="252bc-108">Instalacja za pomocą Instalatora platformy internetowej nie jest już dostępna dla programu Azure PowerShell w wersji 6.x lub nowszej.</span><span class="sxs-lookup"><span data-stu-id="252bc-108">The Web Platform Installer method of installation is no longer available for versions of Azure PowerShell 6.x and higher.</span></span> <span data-ttu-id="252bc-109">Jeśli jest wymagane użycie Instalatora platformy internetowej, rozważ użycie zamiast niego instalatora MSI lub zainstaluj starszą wersję programu Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="252bc-109">If you require use of the Web Platform Installer please consider using the MSI instead, or you can install an earlier version of Azure PowerShell.</span></span>

<span data-ttu-id="252bc-110">Aby zainstalować w środowiskach Linux lub macOS, zobacz [Instalowanie programu Azure PowerShell w systemie macOS lub Linux](install-azurermps-maclinux.md).</span><span class="sxs-lookup"><span data-stu-id="252bc-110">To install on Linux or macOS environments, see [Install Azure PowerShell on macOS or Linux](install-azurermps-maclinux.md).</span></span>

## <a name="install-or-update-on-windows-using-the-msi-package"></a><span data-ttu-id="252bc-111">Instalowanie lub aktualizowanie w systemie Windows za pomocą pakietu MSI</span><span class="sxs-lookup"><span data-stu-id="252bc-111">Install or update on Windows using the MSI Package</span></span>

<span data-ttu-id="252bc-112">Program Azure PowerShell można zainstalować za pomocą pliku MSI dostępnego w witrynie [GitHub](https://github.com/Azure/azure-powershell/releases/latest).</span><span class="sxs-lookup"><span data-stu-id="252bc-112">Azure PowerShell can be installed using the MSI file available from [GitHub](https://github.com/Azure/azure-powershell/releases/latest).</span></span> <span data-ttu-id="252bc-113">Jeśli zainstalowano wcześniejsze wersje modułów platformy Azure za pomocą pakietu MSI, instalator automatycznie je usuwa.</span><span class="sxs-lookup"><span data-stu-id="252bc-113">If you have installed previous versions of Azure modules as an MSI, the installer automatically removes them.</span></span> <span data-ttu-id="252bc-114">Pakiet MSI instaluje moduły w lokalizacji `${env:ProgramFiles}\WindowsPowerShell\Modules`.</span><span class="sxs-lookup"><span data-stu-id="252bc-114">The MSI package installs modules in `${env:ProgramFiles}\WindowsPowerShell\Modules`.</span></span> <span data-ttu-id="252bc-115">Zostaną zainstalowane moduły `AzureRM` i `Azure`.</span><span class="sxs-lookup"><span data-stu-id="252bc-115">Both the `AzureRM` and `Azure` modules are installed.</span></span>

> [!NOTE]
> <span data-ttu-id="252bc-116">Używaj modułu `Azure` tylko wtedy, gdy pracujesz z klasycznym modelem wdrażania platformy Azure.</span><span class="sxs-lookup"><span data-stu-id="252bc-116">Only use the `Azure` module if you are working with the Azure classic deployment model.</span></span>

<span data-ttu-id="252bc-117">Aby rozpocząć pracę z programem Azure PowerShell, musisz załadować moduł `AzureRM` w bieżącej sesji programu PowerShell przy użyciu polecenia cmdlet [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module), a następnie zaloguj się przy użyciu swoich poświadczeń platformy Azure.</span><span class="sxs-lookup"><span data-stu-id="252bc-117">To start working with Azure PowerShell, you need to load `AzureRM` into your current PowerShell session with the [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) cmdlet, and then sign in with your Azure credentials.</span></span>

```powershell
# Import the module into the PowerShell session
Import-Module AzureRM
# Connect to Azure with an interactive dialog for sign-in
Connect-AzureRmAccount
```

<span data-ttu-id="252bc-118">Musisz powtórzyć te kroki dla każdej nowej sesji programu PowerShell, którą rozpoczniesz.</span><span class="sxs-lookup"><span data-stu-id="252bc-118">You'll need to repeat these steps for every new PowerShell session you start.</span></span> <span data-ttu-id="252bc-119">Automatyczne zaimportowanie modułu `AzureRM` wymaga skonfigurowania profilu programu PowerShell — więcej informacji na ten temat można znaleźć na stronie [About Profiles (Informacje o profilach)](/powershell/module/microsoft.powershell.core/about/about_profiles).</span><span class="sxs-lookup"><span data-stu-id="252bc-119">Automatically importing the `AzureRM` module requires setting up a PowerShell profile, which you can learn about in [About Profiles](/powershell/module/microsoft.powershell.core/about/about_profiles).</span></span>
<span data-ttu-id="252bc-120">Aby dowiedzieć się, jak można utrwalić logowanie się do swojego konta platformy Azure w wielu sesjach, zobacz [Utrwalanie poświadczeń użytkownika między sesjami programu PowerShell](context-persistence.md).</span><span class="sxs-lookup"><span data-stu-id="252bc-120">To learn how to persist your Azure sign-in across sessions, see [Persist user credentials across PowerShell sessions](context-persistence.md).</span></span>