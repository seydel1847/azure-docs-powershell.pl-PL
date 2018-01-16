---
title: Dziennik zmian w programie Azure PowerShell | Microsoft Docs
description: Jest to historia zmian wprowadzonych w programie Azure PowerShell w jego najnowszej wersji.
services: azure
author: sdwheeler
ms.author: sewhee
manager: carmonm
ms.service: azure-resource-manager
ms.product: azure
ms.devlang: powershell
ms.topic: conceptual
ms.workload: 
ms.date: 05/18/2017
ms.openlocfilehash: 5c8fa2a5a8f94cd24b66f42c237749a7b89af3b3
ms.sourcegitcommit: ec0b3565264ff7c9f03315ded182f3d5cce534fc
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/13/2017
---
# <a name="release-notes"></a><span data-ttu-id="2e1a0-103">Informacje o wersji</span><span class="sxs-lookup"><span data-stu-id="2e1a0-103">Release notes</span></span>

<span data-ttu-id="2e1a0-104">To jest lista zmian wprowadzonych w programie Azure PowerShell w tym wydaniu.</span><span class="sxs-lookup"><span data-stu-id="2e1a0-104">This is a list of changes made to Azure PowerShell in this release.</span></span>

## <a name="version-400"></a><span data-ttu-id="2e1a0-105">Wersja 4.0.0</span><span class="sxs-lookup"><span data-stu-id="2e1a0-105">Version 4.0.0</span></span>

* <span data-ttu-id="2e1a0-106">Niniejsza wersja zawiera istotne zmiany.</span><span class="sxs-lookup"><span data-stu-id="2e1a0-106">This release contains breaking changes.</span></span> <span data-ttu-id="2e1a0-107">Aby uzyskać szczegółowe informacje o zmianach i ich wpływie na istniejące skrypty, zobacz [przewodnik po migracji](https://aka.ms/azps-migration-guide).</span><span class="sxs-lookup"><span data-stu-id="2e1a0-107">Please see [the migration guide](https://aka.ms/azps-migration-guide) for change details and the impact on existing scripts.</span></span>
* <span data-ttu-id="2e1a0-108">ApiManagement</span><span class="sxs-lookup"><span data-stu-id="2e1a0-108">ApiManagement</span></span>
  - <span data-ttu-id="2e1a0-109">Dodano obsługę konfigurowania grup zewnętrznych w poleceniu New-AzureRmApiManagementGroup.</span><span class="sxs-lookup"><span data-stu-id="2e1a0-109">Added support for configuring external groups in New-AzureRmApiManagementGroup.</span></span>
* <span data-ttu-id="2e1a0-110">Rozliczenia</span><span class="sxs-lookup"><span data-stu-id="2e1a0-110">Billing</span></span>
  - <span data-ttu-id="2e1a0-111">Nowe polecenie cmdlet Get-AzureRmBillingPeriod</span><span class="sxs-lookup"><span data-stu-id="2e1a0-111">New Cmdlet Get-AzureRmBillingPeriod</span></span>
    + <span data-ttu-id="2e1a0-112">Polecenie cmdlet do pobierania okresów rozliczeniowych subskrypcji platformy Azure.</span><span class="sxs-lookup"><span data-stu-id="2e1a0-112">cmdlet to retrieve azure billing periods of the subscription.</span></span>
  - <span data-ttu-id="2e1a0-113">Aktualizacja polecenia cmdlet Get-AzureRmBillingInvoice</span><span class="sxs-lookup"><span data-stu-id="2e1a0-113">Update Cmdlet Get-AzureRmBillingInvoice</span></span>
  - <span data-ttu-id="2e1a0-114">Nowa właściwość BillingPeriodNames</span><span class="sxs-lookup"><span data-stu-id="2e1a0-114">new property BillingPeriodNames</span></span>
  - <span data-ttu-id="2e1a0-115">Dane wyjściowe w widoku listy</span><span class="sxs-lookup"><span data-stu-id="2e1a0-115">output in list view</span></span>
* <span data-ttu-id="2e1a0-116">Wystąpienia obliczeniowe</span><span class="sxs-lookup"><span data-stu-id="2e1a0-116">Compute</span></span>
  - <span data-ttu-id="2e1a0-117">Zaktualizowano polecenia cmdlet Set-AzureRmVMAEMExtension i Test-AzureRmVMAEMExtension o obsługę dysków zarządzanych w warstwie Premium</span><span class="sxs-lookup"><span data-stu-id="2e1a0-117">Updated Set-AzureRmVMAEMExtension and Test-AzureRmVMAEMExtension cmdlets to support Premium managed disks</span></span>
  - <span data-ttu-id="2e1a0-118">Ustawienia szyfrowania kopii zapasowych maszyn wirtualnych IaaS oraz przywracanie po awarii</span><span class="sxs-lookup"><span data-stu-id="2e1a0-118">Backup encryption settings for IaaS VMs and restore on failure</span></span>
  - <span data-ttu-id="2e1a0-119">Zmieniono nazwę opcji ChefServiceInterval na ChefDaemonInterval.</span><span class="sxs-lookup"><span data-stu-id="2e1a0-119">ChefServiceInterval option is renamed to ChefDaemonInterval now.</span></span> <span data-ttu-id="2e1a0-120">Stara opcja będzie jednak nadal działać.</span><span class="sxs-lookup"><span data-stu-id="2e1a0-120">Old one will continue to work however.</span></span>
  - <span data-ttu-id="2e1a0-121">Usunięto zduplikowane właściwości DataDiskNames i NetworkInterfaceIDs z obiektu maszyny wirtualnej w programie PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2e1a0-121">Remove duplicated DataDiskNames and NetworkInterfaceIDs properties from PS VM object.</span></span>
  - <span data-ttu-id="2e1a0-122">Zmieniono parametry DataDiskNames i NetworkInterfaceIDs odpowiednio w poleceniach Remove-AzureRmVMDataDisk i Remove-AzureRmVMNetworkInterface na opcjonalne.</span><span class="sxs-lookup"><span data-stu-id="2e1a0-122">Make DataDiskNames and NetworkInterfaceIDs parameters optional in Remove-AzureRmVMDataDisk and Remove-AzureRmVMNetworkInterface, respectively.</span></span>
  - <span data-ttu-id="2e1a0-123">Naprawiono problem z potokami poleceń cmdlet zawierających wartość Get, który występował, gdy polecenia cmdlet zwracały obiekt listy.</span><span class="sxs-lookup"><span data-stu-id="2e1a0-123">Fix the piping issue of Get cmdlets when the Get cmdlets return a list object.</span></span>
  - <span data-ttu-id="2e1a0-124">Zmieniono nazwy poleceń cmdlet powodujących konflikt z poleceniami cmdlet frontonu RedDog.</span><span class="sxs-lookup"><span data-stu-id="2e1a0-124">Cmdlets that conflicted with RDFE cmdlets have been renamed.</span></span> <span data-ttu-id="2e1a0-125">Aby uzyskać szczegółowe informacje, zobacz opis problemu na stronie https://github.com/Azure/azure-powershell/issues/2917</span><span class="sxs-lookup"><span data-stu-id="2e1a0-125">See issue https://github.com/Azure/azure-powershell/issues/2917 for more details</span></span>
    + <span data-ttu-id="2e1a0-126">Zmieniono nazwę polecenia `New-AzureVMSqlServerAutoBackupConfig` na `New-AzureRmVMSqlServerAutoBackupConfig`</span><span class="sxs-lookup"><span data-stu-id="2e1a0-126">`New-AzureVMSqlServerAutoBackupConfig` has been renamed to `New-AzureRmVMSqlServerAutoBackupConfig`</span></span>
    + <span data-ttu-id="2e1a0-127">Zmieniono nazwę polecenia `New-AzureVMSqlServerAutoPatchingConfig` na `New-AzureRmVMSqlServerAutoPatchingConfig`</span><span class="sxs-lookup"><span data-stu-id="2e1a0-127">`New-AzureVMSqlServerAutoPatchingConfig` has been renamed to `New-AzureRmVMSqlServerAutoPatchingConfig`</span></span>
    + <span data-ttu-id="2e1a0-128">Zmieniono nazwę polecenia `New-AzureVMSqlServerKeyVaultCredentialConfig` na `New-AzureRmVMSqlServerKeyVaultCredentialConfig`</span><span class="sxs-lookup"><span data-stu-id="2e1a0-128">`New-AzureVMSqlServerKeyVaultCredentialConfig` has been renamed to `New-AzureRmVMSqlServerKeyVaultCredentialConfig`</span></span>
* <span data-ttu-id="2e1a0-129">Zużycie</span><span class="sxs-lookup"><span data-stu-id="2e1a0-129">Consumption</span></span>
  - <span data-ttu-id="2e1a0-130">Dodano nowe polecenie cmdlet Get-AzureRmConsumptionUsageDetail</span><span class="sxs-lookup"><span data-stu-id="2e1a0-130">New Cmdlet Get-AzureRmConsumptionUsageDetail</span></span>
    + <span data-ttu-id="2e1a0-131">Polecenie cmdlet do pobierania szczegółów użycia w ramach subskrypcji.</span><span class="sxs-lookup"><span data-stu-id="2e1a0-131">cmdlet to retrieve usage details of the subscription.</span></span>
* <span data-ttu-id="2e1a0-132">ContainerRegistry</span><span class="sxs-lookup"><span data-stu-id="2e1a0-132">ContainerRegistry</span></span>
  - <span data-ttu-id="2e1a0-133">Dodano polecenia cmdlet programu PowerShell dla usługi Azure Container Registry</span><span class="sxs-lookup"><span data-stu-id="2e1a0-133">Add PowerShell cmdlets for Azure Container Registry</span></span>
    + <span data-ttu-id="2e1a0-134">New-AzureRmContainerRegistry</span><span class="sxs-lookup"><span data-stu-id="2e1a0-134">New-AzureRmContainerRegistry</span></span>
    + <span data-ttu-id="2e1a0-135">Get-AzureRmContainerRegistry</span><span class="sxs-lookup"><span data-stu-id="2e1a0-135">Get-AzureRmContainerRegistry</span></span>
    + <span data-ttu-id="2e1a0-136">Update-AzureRmContainerRegistry</span><span class="sxs-lookup"><span data-stu-id="2e1a0-136">Update-AzureRmContainerRegistry</span></span>
    + <span data-ttu-id="2e1a0-137">Remove-AzureRmContainerRegistry</span><span class="sxs-lookup"><span data-stu-id="2e1a0-137">Remove-AzureRmContainerRegistry</span></span>
    + <span data-ttu-id="2e1a0-138">Get-AzureRmContainerRegistryCredential</span><span class="sxs-lookup"><span data-stu-id="2e1a0-138">Get-AzureRmContainerRegistryCredential</span></span>
    + <span data-ttu-id="2e1a0-139">Update-AzureRmContainerRegistryCredential</span><span class="sxs-lookup"><span data-stu-id="2e1a0-139">Update-AzureRmContainerRegistryCredential</span></span>
    + <span data-ttu-id="2e1a0-140">Test-AzureRmContainerRegistryNameAvailability</span><span class="sxs-lookup"><span data-stu-id="2e1a0-140">Test-AzureRmContainerRegistryNameAvailability</span></span>
* <span data-ttu-id="2e1a0-141">DataLakeAnalytics</span><span class="sxs-lookup"><span data-stu-id="2e1a0-141">DataLakeAnalytics</span></span>
  - <span data-ttu-id="2e1a0-142">Dodano obsługę pobierania i wyświetlania listy pakietu wykazu</span><span class="sxs-lookup"><span data-stu-id="2e1a0-142">Add support for catalog package get and list</span></span>
  - <span data-ttu-id="2e1a0-143">Dodano obsługę wyświetlania listy poniższych elementów wykazu z głębszych elementów nadrzędnych:</span><span class="sxs-lookup"><span data-stu-id="2e1a0-143">Add support for listing the following catalog items from deeper ancestors:</span></span>
    + <span data-ttu-id="2e1a0-144">Tabela</span><span class="sxs-lookup"><span data-stu-id="2e1a0-144">Table</span></span>
    + <span data-ttu-id="2e1a0-145">Funkcja TVF</span><span class="sxs-lookup"><span data-stu-id="2e1a0-145">TVF</span></span>
    + <span data-ttu-id="2e1a0-146">Widok</span><span class="sxs-lookup"><span data-stu-id="2e1a0-146">View</span></span>
    + <span data-ttu-id="2e1a0-147">Statystyki</span><span class="sxs-lookup"><span data-stu-id="2e1a0-147">Statistics</span></span>
* <span data-ttu-id="2e1a0-148">DataLakeStore</span><span class="sxs-lookup"><span data-stu-id="2e1a0-148">DataLakeStore</span></span>
  - <span data-ttu-id="2e1a0-149">Dla poleceń `Import-AzureRMDataLakeStoreItem` i `Export-AzureRMDataLakeStoreItem` domyślnie wyłączono rejestrowanie śledzenia, aby poprawić wydajność.</span><span class="sxs-lookup"><span data-stu-id="2e1a0-149">For `Import-AzureRMDataLakeStoreItem` and `Export-AzureRMDataLakeStoreItem` trace logging has been disabled by default to improve performance.</span></span> <span data-ttu-id="2e1a0-150">Aby włączyć rejestrowanie śledzenia, należy użyć parametrów `-DiagnosticLogLevel` i `-DiagnosticLogPath`</span><span class="sxs-lookup"><span data-stu-id="2e1a0-150">If trace logging is desired please use the `-DiagnosticLogLevel` and `-DiagnosticLogPath` parameters</span></span>
  - <span data-ttu-id="2e1a0-151">Naprawiono usterkę, która czasami powodowała awarię programu PowerShell podczas przekazywania wielu małych plików do usługi ADLS.</span><span class="sxs-lookup"><span data-stu-id="2e1a0-151">Fixed a bug that would sometimes cause PowerShell to crash when uploading lots of small file to ADLS.</span></span>
* <span data-ttu-id="2e1a0-152">EventHub</span><span class="sxs-lookup"><span data-stu-id="2e1a0-152">EventHub</span></span>
  - <span data-ttu-id="2e1a0-153">Poprawka usterki:</span><span class="sxs-lookup"><span data-stu-id="2e1a0-153">Bug fix :</span></span>
    + <span data-ttu-id="2e1a0-154">Poprawka błędu dotyczącego polecenia cmdlet Set-AzureRmEventHubNamespace: element „Tier” nie może mieć wartości null, gdy powinien mieć wartość „SkuName”</span><span class="sxs-lookup"><span data-stu-id="2e1a0-154">Fix for Set-AzureRmEventHubNamespace cmdlet error  - 'Tier' cannot be null, where it should be 'SkuName'</span></span>
    + <span data-ttu-id="2e1a0-155">Set-AzureRmEventHub: poprawka dla błędu „Odwołanie do obiektu nie zostało ustawione na wystąpienie obiektu” wyświetlanego podczas aktualizowania usługi EventHub</span><span class="sxs-lookup"><span data-stu-id="2e1a0-155">Set-AzureRmEventHub - Fix 'Object reference not set to an instance of an object' error while updating EventHub</span></span>
* <span data-ttu-id="2e1a0-156">Insights</span><span class="sxs-lookup"><span data-stu-id="2e1a0-156">Insights</span></span>
  - <span data-ttu-id="2e1a0-157">Add-AzureRm*AlertRule</span><span class="sxs-lookup"><span data-stu-id="2e1a0-157">Add-AzureRm*AlertRule</span></span>
    + <span data-ttu-id="2e1a0-158">Zwraca pojedynczy obiekt: newResource, statusCode, requestId</span><span class="sxs-lookup"><span data-stu-id="2e1a0-158">Returns a single object: newResource, statusCode, requestId</span></span>
  - <span data-ttu-id="2e1a0-159">Get-AzureRmAlertRule</span><span class="sxs-lookup"><span data-stu-id="2e1a0-159">Get-AzureRmAlertRule</span></span>
    + <span data-ttu-id="2e1a0-160">Dane wyjściowe są teraz wyliczane, a nie traktowane jako pojedynczy obiekt.</span><span class="sxs-lookup"><span data-stu-id="2e1a0-160">The output is now enumerated instead of considered a single object.</span></span> <span data-ttu-id="2e1a0-161">Ich typ nie uległ zmianie. Nadal jest to lista.</span><span class="sxs-lookup"><span data-stu-id="2e1a0-161">Its type did not change, it is still a list.</span></span>
  - <span data-ttu-id="2e1a0-162">Remove-AzureRmAlertRule</span><span class="sxs-lookup"><span data-stu-id="2e1a0-162">Remove-AzureRmAlertRule</span></span>
    + <span data-ttu-id="2e1a0-163">Po kodzie stanu zwróconym przez żądanie jest wyświetlana wartość „statusCode”. Wcześniej był to zawsze ciąg „OK”.</span><span class="sxs-lookup"><span data-stu-id="2e1a0-163">The statusCode follows the status code returned by the request, before it was Ok always.</span></span>
  - <span data-ttu-id="2e1a0-164">Add-AzureRmAutoscaleSetting</span><span class="sxs-lookup"><span data-stu-id="2e1a0-164">Add-AzureRmAutoscaleSetting</span></span>
    + <span data-ttu-id="2e1a0-165">Zwraca teraz pojedynczy obiekt (a nie listę, jak wcześniej) zawierający wartości statusCode, requestId oraz nowo utworzony/zaktualizowany zasób.</span><span class="sxs-lookup"><span data-stu-id="2e1a0-165">Returns now a single object (not a list as before) containing statusCode, requestId, and the newly created/updated resource.</span></span>
    + <span data-ttu-id="2e1a0-166">Po stanie zwróconym przez żądanie jest wyświetlany kod stanu. Wcześniej był to zawsze ciąg „OK”.</span><span class="sxs-lookup"><span data-stu-id="2e1a0-166">The status code follows the status returned by the request, before it was always Ok.</span></span>
  - <span data-ttu-id="2e1a0-167">New-AzureRmAutoscaleRule</span><span class="sxs-lookup"><span data-stu-id="2e1a0-167">New-AzureRmAutoscaleRule</span></span>
    + <span data-ttu-id="2e1a0-168">Parametr ScaleActionType został rozszerzony. Otrzymuje teraz następujące wartości: ChangeCount, PercentChangeCount, ExactCount.</span><span class="sxs-lookup"><span data-stu-id="2e1a0-168">The parameter ScaleActionType has been extended, it receives the following values now: ChangeCount, PercentChangeCount, ExactCount.</span></span>
  - <span data-ttu-id="2e1a0-169">Remove-AzureRmAutoscaleSetting</span><span class="sxs-lookup"><span data-stu-id="2e1a0-169">Remove-AzureRmAutoscaleSetting</span></span>
    + <span data-ttu-id="2e1a0-170">W danych wyjściowych po wartości statusCode zwróconej przez żądanie jest wyświetlany ciąg statusCode.</span><span class="sxs-lookup"><span data-stu-id="2e1a0-170">The statusCode in the output follows the statusCode returned by the request.</span></span> <span data-ttu-id="2e1a0-171">Wcześniej był to zawsze ciąg OK.</span><span class="sxs-lookup"><span data-stu-id="2e1a0-171">Before it was always Ok.</span></span>
  - <span data-ttu-id="2e1a0-172">Get-AzureRMLogProfile</span><span class="sxs-lookup"><span data-stu-id="2e1a0-172">Get-AzureRMLogProfile</span></span>
    + <span data-ttu-id="2e1a0-173">Dane wyjściowe są teraz wyliczane.</span><span class="sxs-lookup"><span data-stu-id="2e1a0-173">The output is now enumerated.</span></span> <span data-ttu-id="2e1a0-174">Wcześniej były traktowane jako pojedynczy obiekt.</span><span class="sxs-lookup"><span data-stu-id="2e1a0-174">Before it was considered a single object.</span></span> <span data-ttu-id="2e1a0-175">Typ danych wyjściowych to nadal lista, tak jak wcześniej.</span><span class="sxs-lookup"><span data-stu-id="2e1a0-175">The type of the output remains a list as before.</span></span>
  - <span data-ttu-id="2e1a0-176">Remove-AzureRmLogProfile</span><span class="sxs-lookup"><span data-stu-id="2e1a0-176">Remove-AzureRmLogProfile</span></span>
    + <span data-ttu-id="2e1a0-177">Zaimplementowano parametr PassThru.</span><span class="sxs-lookup"><span data-stu-id="2e1a0-177">The PassThru parameter has been implemented.</span></span>
  - <span data-ttu-id="2e1a0-178">Interfejs API metryk</span><span class="sxs-lookup"><span data-stu-id="2e1a0-178">Metrics API</span></span>
    + <span data-ttu-id="2e1a0-179">Zestaw SDK pobiera teraz metryki z usługi MDM.</span><span class="sxs-lookup"><span data-stu-id="2e1a0-179">The SDK now retrieves metrics from MDM.</span></span>
  - <span data-ttu-id="2e1a0-180">Get-AzureRmMetricDefinition</span><span class="sxs-lookup"><span data-stu-id="2e1a0-180">Get-AzureRmMetricDefinition</span></span>
    + <span data-ttu-id="2e1a0-181">Dane wyjściowe to nadal lista, ale struktura tej listy uległa zmianie.</span><span class="sxs-lookup"><span data-stu-id="2e1a0-181">The output is still a list, but the structure of the list changed.</span></span>
  - <span data-ttu-id="2e1a0-182">Get-AzureRmMetric</span><span class="sxs-lookup"><span data-stu-id="2e1a0-182">Get-AzureRmMetric</span></span>
    + <span data-ttu-id="2e1a0-183">Wywołanie uległo zmianie.</span><span class="sxs-lookup"><span data-stu-id="2e1a0-183">The call has changed.</span></span> <span data-ttu-id="2e1a0-184">Oto nowa składnia: Get-AzureRmMetric ResourceId [Nazwy_metryk [Ziarno_czasu] [Typ_agregacji] [Czas_rozpoczęcia] [Czas_zakończenia]] [Szczegółowe_dane_wyjściowe]</span><span class="sxs-lookup"><span data-stu-id="2e1a0-184">This is the new syntax: Get-AzureRmMetric ResourceId [MetricNames [TimeGrain] [AggregationType] [StartTime] [EndTime]] [DetailedOutput]</span></span>
    + <span data-ttu-id="2e1a0-185">Dane wyjściowe to lista, a struktura jej elementów uległa zmianie.</span><span class="sxs-lookup"><span data-stu-id="2e1a0-185">The output is a list, and the structure of its elements has changed.</span></span>
* <span data-ttu-id="2e1a0-186">KeyVault</span><span class="sxs-lookup"><span data-stu-id="2e1a0-186">KeyVault</span></span>
  - <span data-ttu-id="2e1a0-187">Dodano obsługę tworzenia/przywracania kopii zapasowych wpisów tajnych usługi KeyVault</span><span class="sxs-lookup"><span data-stu-id="2e1a0-187">Adding backup/restore support for KeyVault secrets</span></span>
    + <span data-ttu-id="2e1a0-188">Kopie zapasowe wpisów tajnych można tworzyć i przywracać, co zapewnia zgodność z funkcjami obecnie obsługiwanymi w przypadku kluczy</span><span class="sxs-lookup"><span data-stu-id="2e1a0-188">Secrets can be backed up and restored, matching the functionality currently supported for Keys</span></span>

  - <span data-ttu-id="2e1a0-189">Polecenia cmdlet kopii zapasowych dla kluczy i wpisów tajnych akceptują teraz odpowiedni obiekt jako parametr wejściowy</span><span class="sxs-lookup"><span data-stu-id="2e1a0-189">Backup cmdlets for Keys and Secrets now accept a corresponding object as an input parameter</span></span>
    + <span data-ttu-id="2e1a0-190">Obiekt wywołujący może tworzyć łańcuchy operacji pobierania i tworzenia kopii zapasowych: Get-AzureKeyVaultKey -VaultName mójMagazyn -Name mójKlucz | Backup-AzureKeyVaultKey</span><span class="sxs-lookup"><span data-stu-id="2e1a0-190">The caller may chain retrieval and backup operations: Get-AzureKeyVaultKey -VaultName myVault -Name myKey | Backup-AzureKeyVaultKey</span></span>

  - <span data-ttu-id="2e1a0-191">Polecenia cmdlet kopii zapasowych obsługują teraz przełącznik -Force umożliwiający zastąpienie istniejącego pliku</span><span class="sxs-lookup"><span data-stu-id="2e1a0-191">Backup cmdlets now support a -Force switch to overwrite an existing file</span></span>
    + <span data-ttu-id="2e1a0-192">Pamiętaj, że próba zastąpienia istniejącego pliku nie będzie już powodować zgłoszenia błędu. Zamiast tego będzie wyświetlany monit o wybranie działania.</span><span class="sxs-lookup"><span data-stu-id="2e1a0-192">Note that attempting to overwrite an existing file will no longer throw, and will instead prompt the user for a choice on how to proceed.</span></span>
* <span data-ttu-id="2e1a0-193">LogicApp</span><span class="sxs-lookup"><span data-stu-id="2e1a0-193">LogicApp</span></span>
  - <span data-ttu-id="2e1a0-194">Nowe parametry poleceń cmdlet odzyskiwania po awarii numeru kontrolnego wymiany:</span><span class="sxs-lookup"><span data-stu-id="2e1a0-194">New parameters for Interchange Control Number disaster recovery cmdlets:</span></span>
    + <span data-ttu-id="2e1a0-195">Opcjonalny parametr -AgreementType („X12” lub „Edifact”) umożliwiający określenie odpowiednich numerów kontrolnych</span><span class="sxs-lookup"><span data-stu-id="2e1a0-195">Optional -AgreementType parameter ("X12", or "Edifact") to specify the relevant control numbers</span></span>
* <span data-ttu-id="2e1a0-196">MachineLearning</span><span class="sxs-lookup"><span data-stu-id="2e1a0-196">MachineLearning</span></span>
  - <span data-ttu-id="2e1a0-197">Korzystanie z nowej wersji zestawu .NET SDK usługi Azure Machine Learning i dodanie nowego polecenia cmdlet</span><span class="sxs-lookup"><span data-stu-id="2e1a0-197">Consume new version of Azure Machine Learning .Net SDK and add a new cmdlet</span></span>
    + <span data-ttu-id="2e1a0-198">Add-AzureRmMlWebServiceRegionalProperty</span><span class="sxs-lookup"><span data-stu-id="2e1a0-198">Add-AzureRmMlWebServiceRegionalProperty</span></span>
  - <span data-ttu-id="2e1a0-199">Niewielkie poprawki tekstu pomocy.</span><span class="sxs-lookup"><span data-stu-id="2e1a0-199">Minor wording fixes in help text.</span></span>
* <span data-ttu-id="2e1a0-200">Sieć</span><span class="sxs-lookup"><span data-stu-id="2e1a0-200">Network</span></span>
  - <span data-ttu-id="2e1a0-201">Dodano polecenie cmdlet Test-AzureRmNetworkWatcherConnectivity</span><span class="sxs-lookup"><span data-stu-id="2e1a0-201">Added Test-AzureRmNetworkWatcherConnectivity cmdlet</span></span>
    + <span data-ttu-id="2e1a0-202">Zwraca informacje o łączności dla określonej źródłowej maszyny wirtualnej i określonego miejsca docelowego</span><span class="sxs-lookup"><span data-stu-id="2e1a0-202">Returns connectivity information for a specified source VM and a destination</span></span>
    + <span data-ttu-id="2e1a0-203">Jeśli nie można ustanowić łączności między miejscem źródłowym i docelowym, polecenie cmdlet zwraca szczegółowe informacje dotyczące problemu</span><span class="sxs-lookup"><span data-stu-id="2e1a0-203">If connectivity between the source and destination cannot be established, the cmdlet returns details about the issue</span></span>
* <span data-ttu-id="2e1a0-204">Profil</span><span class="sxs-lookup"><span data-stu-id="2e1a0-204">Profile</span></span>
  - <span data-ttu-id="2e1a0-205">Dodano polecenie cmdlet „Send-Feedback”, które pozwala użytkownikowi na zainicjowanie zestawu monitów w celu wysłania opinii do zespołu programu Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2e1a0-205">Added \`Send-Feedback' cmdlet: allows a user to initiate a set of prompts which sends feedback to the Azure PowerShell team.</span></span>
  - <span data-ttu-id="2e1a0-206">Następujące aliasy zostały usunięte, ponieważ powodowały konflikty z istniejącymi nazwami poleceń cmdlet w module platformy Azure:</span><span class="sxs-lookup"><span data-stu-id="2e1a0-206">The following aliases have been removed as they conflicted with existing cmdlet names in the Azure module:</span></span>
    + <span data-ttu-id="2e1a0-207">`Enable-AzureDataCollection` (obsługiwany przez `Enable-AzureRmDataCollection`)</span><span class="sxs-lookup"><span data-stu-id="2e1a0-207">`Enable-AzureDataCollection` (supported by `Enable-AzureRmDataCollection`)</span></span>
    + <span data-ttu-id="2e1a0-208">`Disable-AzureDataCollection` (obsługiwany przez `Disable-AzureRmDataCollection`)</span><span class="sxs-lookup"><span data-stu-id="2e1a0-208">`Disable-AzureDataCollection` (supported by `Disable-AzureRmDataCollection`)</span></span>
* <span data-ttu-id="2e1a0-209">Usługa Relay</span><span class="sxs-lookup"><span data-stu-id="2e1a0-209">Relay</span></span>
  - <span data-ttu-id="2e1a0-210">Dodano polecenia cmdlet dla usługi Azure Relay umożliwiające użytkownikom tworzenie wszystkich zasobów usługi Azure Relay i zarządzanie nimi.</span><span class="sxs-lookup"><span data-stu-id="2e1a0-210">Adds cmdlets for the Azure Relay which allows users to create and manage all Azure Relay resources.</span></span>
    + `New-AzureRmRelayNamespace`
    + `Get-AzureRmRelayNamespace`
    + `Set-AzureRmRelayNamespace`
    + `Remove-AzureRmRelayNamespace`
    + `New-AzureRmWcfRelay`
    + `Get-AzureRmWcfRelay`
    + `Set-AzureRmWcfRelay`
    + `Remove-AzureRmWcfRelay`
    + `New-AzureRmRelayHybridConnection`
    + `Get-AzureRmRelayHybridConnection`
    + `Set-AzureRmRelayHybridConnection`
    + `Remove-AzureRmRelayHybridConnection`
    + `Test-AzureRmRelayName`
    + `Get-AzureRmRelayOperation`
    + `New-AzureRmRelayKey`
    + `Get-AzureRmRelayKey`
    + `New-AzureRmRelayAuthorizationRule`
    + `Get-AzureRmRelayAuthorizationRule`
    + `Set-AzureRmRelayAuthorizationRule`
    + `Remove-AzureRmRelayAuthorizationRule`
* <span data-ttu-id="2e1a0-211">Zasoby</span><span class="sxs-lookup"><span data-stu-id="2e1a0-211">Resources</span></span>
  - <span data-ttu-id="2e1a0-212">Obsługa wdrożeń między grupami zasobów w poleceniu cmdlet New-AzureRmResourceGroupDeployment</span><span class="sxs-lookup"><span data-stu-id="2e1a0-212">Support cross-resource-group deployments for New-AzureRmResourceGroupDeployment</span></span>
    + <span data-ttu-id="2e1a0-213">Użytkownicy mogą teraz używać zagnieżdżonych wdrożeń w celu wdrażania w różnych grupach zasobów.</span><span class="sxs-lookup"><span data-stu-id="2e1a0-213">Users can now use nested deployments to deploy to different resource groups.</span></span>
* <span data-ttu-id="2e1a0-214">ServiceBus</span><span class="sxs-lookup"><span data-stu-id="2e1a0-214">ServiceBus</span></span>

  - <span data-ttu-id="2e1a0-215">Poprawka usterki: wartości właściwości obiektu kolejki ServiceBus zostały ustawione na null, obiekt jest używany jako parametr wejściowy w poleceniu cmdlet Set-AzureRmServiceBusQueue w celu zaktualizowania kolejki.</span><span class="sxs-lookup"><span data-stu-id="2e1a0-215">Bug Fix: ServiceBus Queue object property values were set to null, the object is used as input parameter in Set-AzureRmServiceBusQueue cmdlet to update Queue.</span></span>
   - <span data-ttu-id="2e1a0-216">Właściwości, których to dotyczy, to: LockDuration, EntityAvailabilityStatus, DuplicateDetectionHistoryTimeWindow, MaxDeliveryCount i MessageCount</span><span class="sxs-lookup"><span data-stu-id="2e1a0-216">Properties affected are LockDuration, EntityAvailabilityStatus, DuplicateDetectionHistoryTimeWindow, MaxDeliveryCount and MessageCount</span></span>
* <span data-ttu-id="2e1a0-217">ServiceFabric</span><span class="sxs-lookup"><span data-stu-id="2e1a0-217">ServiceFabric</span></span>

  - <span data-ttu-id="2e1a0-218">Dodano polecenia cmdlet dla usługi Service Fabric</span><span class="sxs-lookup"><span data-stu-id="2e1a0-218">Added cmdlets for service fabric</span></span>
    + <span data-ttu-id="2e1a0-219">Add-AzureRmServiceFabricApplicationCertificate       Dodaj certyfikat, który będzie używany jako certyfikat aplikacji</span><span class="sxs-lookup"><span data-stu-id="2e1a0-219">Add-AzureRmServiceFabricApplicationCertificate       Add a certificate which will be used as application certificate</span></span>
    + <span data-ttu-id="2e1a0-220">Add-AzureRmServiceFabricClientCertificate       Dodaj nazwę pospolitą lub odcisk palca do ustawień klastra na potrzeby uwierzytelniania klienta</span><span class="sxs-lookup"><span data-stu-id="2e1a0-220">Add-AzureRmServiceFabricClientCertificate       Add a common name or thumbprint to the cluster settings for client authentication</span></span>
    + <span data-ttu-id="2e1a0-221">Add-AzureRmServiceFabricClusterCertificate       Dodaj pomocniczy certyfikat do klastra na potrzeby wymiany istniejącego certyfikatu</span><span class="sxs-lookup"><span data-stu-id="2e1a0-221">Add-AzureRmServiceFabricClusterCertificate       Add a secondary cluster certificate to the cluster for rolling over the existing certificate</span></span>
    + <span data-ttu-id="2e1a0-222">Add-AzureRmServiceFabricNodes       Dodaj węzły/maszyny wirtualne o określonym typie węzła do klastra</span><span class="sxs-lookup"><span data-stu-id="2e1a0-222">Add-AzureRmServiceFabricNodes       Add nodes/VMs of a specific node type to a cluster</span></span>
    + <span data-ttu-id="2e1a0-223">Add-AzureRmServiceFabricNodeType       Dodaj maszyny wirtualne/typ węzła do istniejącego klastra</span><span class="sxs-lookup"><span data-stu-id="2e1a0-223">Add-AzureRmServiceFabricNodeType       Add a node type/VMs to an existing cluster</span></span>
    + <span data-ttu-id="2e1a0-224">Get-AzureRmServiceFabricCluster       Pobierz szczegóły zasobu klastra</span><span class="sxs-lookup"><span data-stu-id="2e1a0-224">Get-AzureRmServiceFabricCluster       Get the details of the cluster resource</span></span>
    + <span data-ttu-id="2e1a0-225">New-AzureRmServiceFabricCluster Utwórz nowy klaster ServiceFabric.</span><span class="sxs-lookup"><span data-stu-id="2e1a0-225">New-AzureRmServiceFabricCluster Create a new ServiceFabric cluster.</span></span> <span data-ttu-id="2e1a0-226">To polecenie ma wiele przeciążeń, aby obsłużyć różne scenariusze</span><span class="sxs-lookup"><span data-stu-id="2e1a0-226">This command has many overloads to cover various scenarios</span></span>
    + <span data-ttu-id="2e1a0-227">Remove-AzureRmServiceFabricClientCertificate       Usuń certyfikat klienta, aby nie był już używany w celu uzyskiwania dostępu do klastra</span><span class="sxs-lookup"><span data-stu-id="2e1a0-227">Remove-AzureRmServiceFabricClientCertificate       Remove a client certificate from being used to access a cluster</span></span>
    + <span data-ttu-id="2e1a0-228">Remove-AzureRmServiceFabricClusterCertificate       Usuń certyfikat klastra, aby nie był już używany do zabezpieczania klastra</span><span class="sxs-lookup"><span data-stu-id="2e1a0-228">Remove-AzureRmServiceFabricClusterCertificate       Remove a cluster certificate from being used for cluster security</span></span>
    + <span data-ttu-id="2e1a0-229">Remove-AzureRmServiceFabricNodes       Usuń z klastra węzły o określonym typie</span><span class="sxs-lookup"><span data-stu-id="2e1a0-229">Remove-AzureRmServiceFabricNodes       Remove nodes from a specific node type from a cluster</span></span>
    + <span data-ttu-id="2e1a0-230">Remove-AzureRmServiceFabricNodeType       Usuń z klastra typ węzła</span><span class="sxs-lookup"><span data-stu-id="2e1a0-230">Remove-AzureRmServiceFabricNodeType       Remove a node type from a cluster</span></span>
    + <span data-ttu-id="2e1a0-231">Remove-AzureRmServiceFabricSettings       Usuń z klastra co najmniej jedno ustawienie ServiceFabric</span><span class="sxs-lookup"><span data-stu-id="2e1a0-231">Remove-AzureRmServiceFabricSettings       Remove one or more ServiceFabric settings from a cluster</span></span>
    + <span data-ttu-id="2e1a0-232">Set-AzureRmServiceFabricSettings       Dodaj lub zaktualizuj co najmniej jedno ustawienie ServiceFabric klastra</span><span class="sxs-lookup"><span data-stu-id="2e1a0-232">Set-AzureRmServiceFabricSettings       Add or update one or more ServiceFabric settings of a cluster</span></span>
    + <span data-ttu-id="2e1a0-233">Set-AzureRmServiceFabricUpgradeType       Zmień typ uaktualnienia ServiceFabric klastra</span><span class="sxs-lookup"><span data-stu-id="2e1a0-233">Set-AzureRmServiceFabricUpgradeType       Change the ServiceFabric upgrade type of a cluster</span></span>
    + <span data-ttu-id="2e1a0-234">Update-AzureRmServiceFabricDurability       Zmień warstwę trwałości klastra</span><span class="sxs-lookup"><span data-stu-id="2e1a0-234">Update-AzureRmServiceFabricDurability       Change the durability tier of a cluster</span></span>
    + <span data-ttu-id="2e1a0-235">Update-AzureRmServiceFabricReliability       Zmień warstwę niezawodności klastra</span><span class="sxs-lookup"><span data-stu-id="2e1a0-235">Update-AzureRmServiceFabricReliability       Change the reliability tier of a cluster</span></span>
* <span data-ttu-id="2e1a0-236">Sql</span><span class="sxs-lookup"><span data-stu-id="2e1a0-236">Sql</span></span>
  - <span data-ttu-id="2e1a0-237">Dodano parametr -SampleName do polecenia New-AzureRmSqlDatabase</span><span class="sxs-lookup"><span data-stu-id="2e1a0-237">Added -SampleName parameter to New-AzureRmSqlDatabase</span></span>
  - <span data-ttu-id="2e1a0-238">Aktualizacje poleceń cmdlet grupy trybu failover</span><span class="sxs-lookup"><span data-stu-id="2e1a0-238">Updates to Failover Group cmdlets</span></span>
  - <span data-ttu-id="2e1a0-239">Usunięto parametry „Tag”</span><span class="sxs-lookup"><span data-stu-id="2e1a0-239">Remove 'Tag' parameters</span></span>
  - <span data-ttu-id="2e1a0-240">Usunięto parametry „PartnerResourceGroupName” i „PartnerServerName” z polecenia cmdlet Remove-AzureRmSqlDatabaseFailoverGroup</span><span class="sxs-lookup"><span data-stu-id="2e1a0-240">Remove 'PartnerResourceGroupName' and 'PartnerServerName' parameters from Remove-AzureRmSqlDatabaseFailoverGroup cmdlet</span></span>
  - <span data-ttu-id="2e1a0-241">Dodano parametr „GracePeriodWithDataLossHours” do poleceń cmdlet New- i Set-, który w przyszłości zastąpi parametr „GracePeriodWithDataLossHour”</span><span class="sxs-lookup"><span data-stu-id="2e1a0-241">Add 'GracePeriodWithDataLossHours' parameter to New- and Set- cmdlets, which shall eventually replace 'GracePeriodWithDataLossHour'</span></span>
  - <span data-ttu-id="2e1a0-242">Dopracowano i zaktualizowano dokumentację</span><span class="sxs-lookup"><span data-stu-id="2e1a0-242">Documentation has been fleshed out and updated</span></span>
  - <span data-ttu-id="2e1a0-243">Zmieniono formatowanie zwracanych obiektów i usunięto usterki, z powodu których pola nie zawsze były wypełniane</span><span class="sxs-lookup"><span data-stu-id="2e1a0-243">Change formatting of returned objects and fix some bugs where fields were not always populated</span></span>
  - <span data-ttu-id="2e1a0-244">Dodano właściwości „DatabaseNames” i „PartnerLocation” do obiektu grupy trybu failover</span><span class="sxs-lookup"><span data-stu-id="2e1a0-244">Add 'DatabaseNames' and 'PartnerLocation' properties to Failover Group object</span></span>
  - <span data-ttu-id="2e1a0-245">Naprawiono usterkę, z powodu której następował natychmiastowy powrót z polecenia cmdlet Switch-, zamiast poczekania na zakończenie operacji</span><span class="sxs-lookup"><span data-stu-id="2e1a0-245">Fix bug causing Switch- cmdlet to return immediately rather than waiting for operation to complete</span></span>
  - <span data-ttu-id="2e1a0-246">Naprawiono usterkę powodującą przekroczenie zakresu liczb całkowitych w przypadku użycia dużych wartości okresu prolongaty</span><span class="sxs-lookup"><span data-stu-id="2e1a0-246">Fix integer overflow bug when high grace period values are used</span></span>
  - <span data-ttu-id="2e1a0-247">Okres prolongaty będzie zmieniany na wartość minimalną (1 godzina), jeśli podano krótszy</span><span class="sxs-lookup"><span data-stu-id="2e1a0-247">Adjust grace period to a minimum of 1 hour if a lower one is provided</span></span>
  - <span data-ttu-id="2e1a0-248">Usunięto wartość „Usage_Anomaly” z listy akceptowanych wartości parametru „ExcludedDetectionType” poleceń cmdlet Set-AzureRmSqlDatabaseThreatDetectionPolicy i Set-AzureRmSqlServerThreatDetectionPolicy.</span><span class="sxs-lookup"><span data-stu-id="2e1a0-248">Remove "Usage_Anomaly" from the accepted values for "ExcludedDetectionType" parameter of Set-AzureRmSqlDatabaseThreatDetectionPolicy cmdlet and Set-AzureRmSqlServerThreatDetectionPolicy cmdlet.</span></span>
* <span data-ttu-id="2e1a0-249">Magazyn</span><span class="sxs-lookup"><span data-stu-id="2e1a0-249">Storage</span></span>
  - <span data-ttu-id="2e1a0-250">Uaktualniono zestaw SRP SDK do wersji 6.3.0</span><span class="sxs-lookup"><span data-stu-id="2e1a0-250">Upgrade SRP SDK to 6.3.0</span></span>
  - <span data-ttu-id="2e1a0-251">New/Set-AzureRmStorageAccount: dodano nowy parametr w celu obsługi atrybutu EnableHttpsTrafficOnly</span><span class="sxs-lookup"><span data-stu-id="2e1a0-251">New/Set-AzureRmStorageAccount:Add a new parameter to support EnableHttpsTrafficOnly</span></span>
  - <span data-ttu-id="2e1a0-252">New/Set/Get-AzureRmStorageAccount: zwracane konto magazynu zawiera nowy atrybut EnableHttpsTrafficOnly</span><span class="sxs-lookup"><span data-stu-id="2e1a0-252">New/Set/Get-AzureRmStorageAccount: Returned Storage Account contains a new attribute EnableHttpsTrafficOnly</span></span>
* <span data-ttu-id="2e1a0-253">Azure.Storage</span><span class="sxs-lookup"><span data-stu-id="2e1a0-253">Azure.Storage</span></span>
  - <span data-ttu-id="2e1a0-254">Uaktualniono bibliotekę klienta usługi Azure Storage do wersji 8.1.1 i bibliotekę przenoszenia danych usługi Azure Storage do wersji 0.5.1</span><span class="sxs-lookup"><span data-stu-id="2e1a0-254">Upgrade to Azure Storage Client Library 8.1.1 and Azure Storage DataMovement Library 0.5.1</span></span>
  - <span data-ttu-id="2e1a0-255">Dodano nowe polecenie cmdlet w celu obsługi funkcji przyrostowej kopii obiektu blob</span><span class="sxs-lookup"><span data-stu-id="2e1a0-255">Add a new cmdlet to support blob Incremental Copy feature</span></span>