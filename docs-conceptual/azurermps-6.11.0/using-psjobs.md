---
title: Równoczesne uruchamianie poleceń cmdlet przy użyciu zadań programu PowerShell
description: Sposób równoległego uruchamiania poleceń cmdlet za pomocą parametru -AsJob.
author: sptramer
ms.author: sttramer
manager: carmonm
ms.devlang: powershell
ms.topic: conceptual
ms.date: 09/11/2018
ms.openlocfilehash: 85e4612146c07b963ca51a7203ea7782d058b93d
ms.sourcegitcommit: 5f946a535eccca0b3ddf3db8f617b32564a88938
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/25/2018
ms.locfileid: "50001273"
---
# <a name="running-cmdlets-in-parallel-using-powershell-jobs"></a><span data-ttu-id="c6fc8-103">Równoczesne uruchamianie poleceń cmdlet przy użyciu zadań programu PowerShell</span><span class="sxs-lookup"><span data-stu-id="c6fc8-103">Running cmdlets in parallel using PowerShell jobs</span></span>

<span data-ttu-id="c6fc8-104">Program PowerShell obsługuje akcję asynchroniczną przy użyciu [zadań programu PowerShell](/powershell/module/microsoft.powershell.core/about/about_jobs).</span><span class="sxs-lookup"><span data-stu-id="c6fc8-104">PowerShell supports asynchronous action with [PowerShell Jobs](/powershell/module/microsoft.powershell.core/about/about_jobs).</span></span>
<span data-ttu-id="c6fc8-105">Program Azure PowerShell w znacznej mierze zależy od wykonywania wywołań sieci do platformy Azure i oczekiwania na nie.</span><span class="sxs-lookup"><span data-stu-id="c6fc8-105">Azure PowerShell is heavily dependent on making, and waiting for, network calls to Azure.</span></span> <span data-ttu-id="c6fc8-106">Często okazuje się, że musisz wykonywać wywołania niepowodujące blokowania.</span><span class="sxs-lookup"><span data-stu-id="c6fc8-106">You may often find yourself needing to make non-blocking calls.</span></span> <span data-ttu-id="c6fc8-107">Aby zaspokoić tę potrzebę, program Azure PowerShell oferuje najwyższej jakości obsługę zadań [PSJob](/powershell/module/microsoft.powershell.core/about/about_jobs).</span><span class="sxs-lookup"><span data-stu-id="c6fc8-107">To address this need, Azure PowerShell provides first-class [PSJob](/powershell/module/microsoft.powershell.core/about/about_jobs) support.</span></span>

## <a name="context-persistence-and-psjobs"></a><span data-ttu-id="c6fc8-108">Stan trwały kontekstu i zadania PSJob</span><span class="sxs-lookup"><span data-stu-id="c6fc8-108">Context Persistence and PSJobs</span></span>

<span data-ttu-id="c6fc8-109">Ponieważ zadania PSJob są uruchamiane jako oddzielne procesy, połączenie platformy Azure musi być współdzielone z nimi.</span><span class="sxs-lookup"><span data-stu-id="c6fc8-109">Since PSJobs are run as separate processes, your Azure connection must be shared with them.</span></span> <span data-ttu-id="c6fc8-110">Po zalogowaniu się do konta platformy Azure za pomocą polecenia `Connect-AzureRmAccount` przekaż kontekst do zadania.</span><span class="sxs-lookup"><span data-stu-id="c6fc8-110">After signing in to your Azure account with `Connect-AzureRmAccount`, pass the context to a job.</span></span>

```azurepowershell-interactive
$creds = Get-Credential
$job = Start-Job { param($context,$vmadmin) New-AzureRmVM -Name MyVm -AzureRmContext $context -Credential $vmadmin} -Arguments (Get-AzureRmContext),$creds
```

<span data-ttu-id="c6fc8-111">Jeśli jednak kontekst ma być zapisywany automatycznie przy użyciu polecenia `Enable-AzureRmContextAutosave`, będzie on automatycznie udostępniany wszystkim tworzonym zadaniom.</span><span class="sxs-lookup"><span data-stu-id="c6fc8-111">However, if you have chosen to have your context automatically saved with `Enable-AzureRmContextAutosave`, the context is automatically shared with any jobs you create.</span></span>

```azurepowershell-interactive
Enable-AzureRmContextAutosave
$creds = Get-Credential
$job = Start-Job { param($vmadmin) New-AzureRmVM -Name MyVm -Credential $vmadmin} -Arguments $creds
```

## <a name="automatic-jobs-with--asjob"></a><span data-ttu-id="c6fc8-112">Zadania automatyczne z parametrem `-AsJob`</span><span class="sxs-lookup"><span data-stu-id="c6fc8-112">Automatic Jobs with `-AsJob`</span></span>

<span data-ttu-id="c6fc8-113">Dla wygody w przypadku niektórych długotrwałych poleceń cmdlet program Azure PowerShell oferuje również przełącznik `-AsJob`.</span><span class="sxs-lookup"><span data-stu-id="c6fc8-113">As a convenience, Azure PowerShell also provides an `-AsJob` switch on some long-running cmdlets.</span></span>
<span data-ttu-id="c6fc8-114">Przełącznik `-AsJob` sprawia, że tworzenie zadań PSJob jest jeszcze łatwiejsze.</span><span class="sxs-lookup"><span data-stu-id="c6fc8-114">The `-AsJob` switch makes creating PSJobs even easier.</span></span>

```azurepowershell-interactive
$creds = Get-Credential
$job = New-AzureRmVM -Name MyVm -Credential $creds -AsJob
```

<span data-ttu-id="c6fc8-115">W dowolnym momencie można przeprowadzić inspekcję zadania i postępu przy użyciu poleceń `Get-Job` i `Get-AzureRmVM`.</span><span class="sxs-lookup"><span data-stu-id="c6fc8-115">You can inspect the job and progress at any time with `Get-Job` and `Get-AzureRmVM`.</span></span>

```azurepowershell-interactive
Get-Job $job
Get-AzureRmVM MyVm
```

```output
Id Name                                       PSJobTypeName         State   HasMoreData Location  Command
-- ----                                       -------------         -----   ----------- --------  -------
1  Long Running Operation for 'New-AzureRmVM' AzureLongRunningJob`1 Running True        localhost New-AzureRmVM

ResourceGroupName    Name Location          VmSize  OsType     NIC ProvisioningState Zone
-----------------    ---- --------          ------  ------     --- ----------------- ----
MyVm                 MyVm   eastus Standard_DS1_v2 Windows    MyVm          Creating
```

<span data-ttu-id="c6fc8-116">Po wykonaniu zadania pobierz jego wynik za pomocą polecenia `Receive-Job`.</span><span class="sxs-lookup"><span data-stu-id="c6fc8-116">When the job completes, get the result of the job with `Receive-Job`.</span></span>

> [!NOTE]
> <span data-ttu-id="c6fc8-117">Polecenie `Receive-Job` zwraca wynik z polecenia cmdlet tak, jakby flaga `-AsJob` nie istniała.</span><span class="sxs-lookup"><span data-stu-id="c6fc8-117">`Receive-Job` returns the result from the cmdlet as if the `-AsJob` flag were not present.</span></span>
> <span data-ttu-id="c6fc8-118">Na przykład wynik polecenia `Receive-Job` dla polecenia `Do-Action -AsJob` jest taki sam jak wynik polecenia `Do-Action`.</span><span class="sxs-lookup"><span data-stu-id="c6fc8-118">For example, the `Receive-Job` result of `Do-Action -AsJob` is of the same type as the result of `Do-Action`.</span></span>

```azurepowershell-interactive
$vm = Receive-Job $job
$vm
```

```output
ResourceGroupName        : MyVm
Id                       : /subscriptions/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX/resourceGroups/MyVm/providers/Microsoft.Compute/virtualMachines/MyVm
VmId                     : dff1f79e-a8f7-4664-ab72-0ec28b9fbb5b
Name                     : MyVm
Type                     : Microsoft.Compute/virtualMachines
Location                 : eastus
Tags                     : {}
HardwareProfile          : {VmSize}
NetworkProfile           : {NetworkInterfaces}
OSProfile                : {ComputerName, AdminUsername, WindowsConfiguration, Secrets}
ProvisioningState        : Succeeded
StorageProfile           : {ImageReference, OsDisk, DataDisks}
FullyQualifiedDomainName : myvmmyvm.eastus.cloudapp.azure.com
```

## <a name="example-scenarios"></a><span data-ttu-id="c6fc8-119">Przykładowe scenariusze</span><span class="sxs-lookup"><span data-stu-id="c6fc8-119">Example Scenarios</span></span>

<span data-ttu-id="c6fc8-120">Tworzenie kilku maszyn wirtualnych jednocześnie:</span><span class="sxs-lookup"><span data-stu-id="c6fc8-120">Create several VMs at once:</span></span>

```azurepowershell-interactive
$creds = Get-Credential
# Create 10 jobs.
for($k = 0; $k -lt 10; $k++) {
    New-AzureRmVm -Name MyVm$k  -Credential $creds -AsJob
}

# Get all jobs and wait on them.
Get-Job | Wait-Job
"All jobs completed"
Get-AzureRmVM
```

<span data-ttu-id="c6fc8-121">W tym przykładzie polecenie cmdlet `Wait-Job` powoduje wstrzymanie skryptu w czasie działania zadań.</span><span class="sxs-lookup"><span data-stu-id="c6fc8-121">In this example, the `Wait-Job` cmdlet causes the script to pause while jobs run.</span></span> <span data-ttu-id="c6fc8-122">Wykonywanie skryptu jest kontynuowane po ukończeniu wszystkich zadań.</span><span class="sxs-lookup"><span data-stu-id="c6fc8-122">The script continues executing once all of the jobs have completed.</span></span> <span data-ttu-id="c6fc8-123">Kilka zadań jest wykonywanych równolegle, a skrypt czeka na ich ukończenie przed kontynuowaniem.</span><span class="sxs-lookup"><span data-stu-id="c6fc8-123">Several jobs run in parallel then the script waits for completion before continuing.</span></span>

```output
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
2      Long Running... AzureLongRun... Running       True            localhost            New-AzureRmVM
3      Long Running... AzureLongRun... Running       True            localhost            New-AzureRmVM
4      Long Running... AzureLongRun... Running       True            localhost            New-AzureRmVM
5      Long Running... AzureLongRun... Running       True            localhost            New-AzureRmVM
6      Long Running... AzureLongRun... Running       True            localhost            New-AzureRmVM
7      Long Running... AzureLongRun... Running       True            localhost            New-AzureRmVM
8      Long Running... AzureLongRun... Running       True            localhost            New-AzureRmVM
9      Long Running... AzureLongRun... Running       True            localhost            New-AzureRmVM
10     Long Running... AzureLongRun... Running       True            localhost            New-AzureRmVM
11     Long Running... AzureLongRun... Running       True            localhost            New-AzureRmVM
2      Long Running... AzureLongRun... Completed     True            localhost            New-AzureRmVM
3      Long Running... AzureLongRun... Completed     True            localhost            New-AzureRmVM
4      Long Running... AzureLongRun... Completed     True            localhost            New-AzureRmVM
5      Long Running... AzureLongRun... Completed     True            localhost            New-AzureRmVM
6      Long Running... AzureLongRun... Completed     True            localhost            New-AzureRmVM
7      Long Running... AzureLongRun... Completed     True            localhost            New-AzureRmVM
8      Long Running... AzureLongRun... Completed     True            localhost            New-AzureRmVM
9      Long Running... AzureLongRun... Completed     True            localhost            New-AzureRmVM
10     Long Running... AzureLongRun... Completed     True            localhost            New-AzureRmVM
11     Long Running... AzureLongRun... Completed     True            localhost            New-AzureRmVM
All Jobs completed.

ResourceGroupName        Name   Location          VmSize  OsType           NIC ProvisioningState Zone
-----------------        ----   --------          ------  ------           --- ----------------- ----
MYVM                     MyVm     eastus Standard_DS1_v2 Windows          MyVm         Succeeded
MYVM0                   MyVm0     eastus Standard_DS1_v2 Windows         MyVm0         Succeeded
MYVM1                   MyVm1     eastus Standard_DS1_v2 Windows         MyVm1         Succeeded
MYVM2                   MyVm2     eastus Standard_DS1_v2 Windows         MyVm2         Succeeded
MYVM3                   MyVm3     eastus Standard_DS1_v2 Windows         MyVm3         Succeeded
MYVM4                   MyVm4     eastus Standard_DS1_v2 Windows         MyVm4         Succeeded
MYVM5                   MyVm5     eastus Standard_DS1_v2 Windows         MyVm5         Succeeded
MYVM6                   MyVm6     eastus Standard_DS1_v2 Windows         MyVm6         Succeeded
MYVM7                   MyVm7     eastus Standard_DS1_v2 Windows         MyVm7         Succeeded
MYVM8                   MyVm8     eastus Standard_DS1_v2 Windows         MyVm8         Succeeded
MYVM9                   MyVm9     eastus Standard_DS1_v2 Windows         MyVm9         Succeeded
```