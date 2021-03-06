---
title: Rozpoczynanie pracy z programem Azure PowerShell
description: ''
author: sptramer
ms.author: sttramer
manager: carmonm
ms.devlang: powershell
ms.topic: get-started-article
ms.date: 01/14/2019
ms.openlocfilehash: 483e74d7d047562b1c170c3767495161b9c5eb2f
ms.sourcegitcommit: c6fd0e490fa0e33b8b768b679682a47d8faae1cf
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/16/2019
ms.locfileid: "54342138"
---
# <a name="get-started-with-azure-powershell"></a>Rozpoczynanie pracy z programem Azure PowerShell

Program Azure PowerShell jest przeznaczony do zarządzania i administrowania zasobami platformy Azure z wiersza polecenia. Za pomocą programu Azure PowerShell możesz tworzyć zautomatyzowane narzędzia korzystające z modelu usługi Azure Resource Manager.
Wypróbuj go w przeglądarce przy użyciu [usługi Azure Cloud Shell](/azure/cloud-shell/overview) lub zainstaluj go na komputerze lokalnym.

W tym artykule przedstawiono podstawowe pojęcia związane z programem Azure PowerShell, które ułatwiają rozpoczęcie korzystania z niego.

## <a name="install-or-run-in-azure-cloud-shell"></a>Instalowanie lub uruchamianie w usłudze Azure Cloud Shell

Najprostszym sposobem rozpoczęcia pracy z programem Azure PowerShell jest wypróbowanie go w środowisku usługi Azure Cloud Shell.
Aby rozpocząć pracę z usługą Cloud Shell, zobacz [Przewodnik Szybki start dotyczący programu PowerShell w usłudze Azure Cloud Shell](/azure/cloud-shell/quickstart-powershell).
Usługa Cloud Shell uruchamia program PowerShell 6 w kontenerze systemu Linux, więc funkcje specyficzne dla systemu Windows są niedostępne.

Jeśli chcesz zainstalować program Azure PowerShell na komputerze lokalnym, wykonaj instrukcje podane w temacie [Instalowanie modułu Azure PowerShell](install-az-ps.md).

## <a name="sign-in-to-azure"></a>Logowanie do platformy Azure

Zaloguj się interakcyjnie przy użyciu polecenia cmdlet `Connect-AzAccount`. Pomiń ten krok, jeśli korzystasz z usługi Cloud Shell: Sesja usługi Azure Cloud Shell jest już uwierzytelniona dla danego środowiska, subskrypcji i dzierżawy, w których uruchomiono sesję usługi Cloud Shell.

```azurepowershell-interactive
Connect-AzAccount
```

Jeśli jesteś w regionie innym niż Stany Zjednoczone, użyj parametru `-Environment`, aby się zalogować. Uzyskaj nazwę środowiska dla swojego regionu, używając polecenia cmdlet [Get-AzEnvironment](/powershell/module/Az.Accounts/Get-AzEnvironment). Aby na przykład zalogować się do platformy Azure w Chinach — 21Vianet:

```azurepowershell-interactive
Connect-AzAccount -Environment AzureChinaCloud
```

Uzyskasz token do użycia w witrynie https://microsoft.com/devicelogin. Otwórz tę stronę w przeglądarce i wprowadź token, a następnie zaloguj się przy użyciu swoich poświadczeń platformy Azure i autoryzuj program Azure PowerShell. 

Po zalogowaniu użyj poleceń cmdlet programu Azure PowerShell, aby uzyskiwać dostęp do zasobów w subskrypcji i zarządzać nimi. Aby dowiedzieć się więcej na temat procesu logowania i metod uwierzytelniania, zobacz [Logowanie się w programie Azure PowerShell](authenticate-azureps.md).

## <a name="find-commands"></a>Znajdowanie poleceń

Polecenia cmdlet programu Azure PowerShell używają standardowej konwencji nazewnictwa dla programu PowerShell: `VERB-NOUN`. Czasownik opisuje akcję (przykłady: `Create`, `Get`, `Set`, `Delete`), a rzeczownik opisuje typ zasobu (przykłady: `AzVM`, `AzKeyVaultCertificate`, `AzFirewall`, `AzVirtualNetworkGateway`). Rzeczowniki w programie Azure PowerShell zawsze rozpoczynają się prefiksem `Az`. Aby uzyskać pełną listę standardowych czasowników, zobacz [Approved verbs for PowerShell Commands](/powershell/developer/cmdlet/approved-verbs-for-windows-powershell-commands) (Zatwierdzone czasowniki dla poleceń programu PowerShell).

Znajomość dostępnych rzeczowników, czasowników i modułów programu Azure PowerShell ułatwia znajdowanie poleceń za pomocą polecenia cmdlet [Get-Command](/powershell/module/microsoft.powershell.core/get-command). Aby na przykład znaleźć wszystkie polecenia dotyczące maszyn wirtualnych i używające czasownika `Get`:

```powershell-interactive
Get-Command -Verb Get -Noun AzVM* -Module Az.Compute
```

Aby ułatwić znajdowanie typowych poleceń, w poniższej tabeli podano typy zasobów, odpowiednie moduły programu Azure PowerShell i prefiksy rzeczowników do używania z poleceniem `Get-Command`:

| Typ zasobu | Moduł programu Azure PowerShell | Prefiks rzeczownika |
|---------------|-------------------------|----------------|
| [Grupa zasobów](/azure/azure-resource-manager/resource-group-overview) | [Az.Resources](/powershell/module/az.resources#resources) | `AzResourceGroup` |
| [Maszyny wirtualne](/azure/virtual-machines) | [Az.Compute](/powershell/module/az.compute#virtual_machines) | `AzVM` |
| [Konta magazynu](/azure/storage/common/storage-introduction) | [Az.Storage](/powershell/module/az.storage/) | `AzStorageAccount` |
| [Usługa Key Vault](/azure/key-vault/key-vault-whatis) | [Az.KeyVault](/powershell/module/az.keyvault) | `AzKeyVault` |
| [Aplikacje internetowe](/azure/app-service) | [Az.Websites](/powershell/module/az.websites) | `AzWebApp` |
| [Bazy danych SQL](/azure/sql-database) | [Az.Sql](/powershell/module/az.sql) | `AzSqlDatabase` |

Aby uzyskać pełną listę modułów w programie Azure PowerShell, zobacz [listę modułów programu Azure PowerShell](https://github.com/Azure/azure-powershell/blob/master/documentation/azure-powershell-modules.md) hostowaną w serwisie GitHub.

## <a name="learn-azure-powershell-basics-with-quickstarts-and-tutorials"></a>Nauka podstaw programu Azure PowerShell za pomocą samouczków i przewodników Szybki start

Aby rozpocząć pracę z programem Azure PowerShell, wypróbuj szczegółowy samouczek na temat konfigurowania maszyn wirtualnych i wykonywania dotyczących ich zapytań.

> [!div class="nextstepaction"]
> [Tworzenie maszyn wirtualnych przy użyciu programu Azure PowerShell](azureps-vm-tutorial.yml)

Dostępne są też przewodniki Szybki start dla programu Azure PowerShell dotyczące innych popularnych usług platformy Azure:

* [Tworzenie konta magazynu](/azure/storage/common/storage-quickstart-create-account?tabs=azure-powershell)
* [Transferowanie obiektów do i z usługi Azure Blob Storage](/azure/storage/blobs/storage-quickstart-blobs-powershell)
* [Tworzenie i pobieranie wpisów tajnych w usłudze Azure Key Vault](/azure/key-vault/quick-create-powershell)
* [Tworzenie bazy danych Azure SQL i zapory](/azure/sql-database/scripts/sql-database-create-and-configure-database-powershell)
* [Uruchamianie kontenera w usłudze Azure Container Instances](/azure/container-instances/container-instances-quickstart-powershell)
* [Tworzenie zestawu skalowania maszyn wirtualnych (VMSS)](/azure/virtual-machine-scale-sets/quick-create-powershell)
* [Tworzenie modułu równoważenia obciążenia w warstwie Standardowa](/azure/load-balancer/quickstart-create-standard-load-balancer-powershell)

## <a name="next-steps"></a>Następne kroki

* [Logowanie się w programie Azure PowerShell](authenticate-azureps.md)
* [Zarządzanie subskrypcjami platformy Azure za pomocą programu Azure PowerShell](manage-subscriptions-azureps.md)
* [Tworzenie jednostek usługi przy użyciu programu Azure PowerShell](create-azure-service-principal-azureps.md)
* Uzyskiwanie pomocy od społeczności:
  * [Forum platformy Azure w witrynie MSDN](http://go.microsoft.com/fwlink/p/?LinkId=320212)
  * [Serwis Stack Overflow](http://go.microsoft.com/fwlink/?LinkId=320213)
