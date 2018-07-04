---
title: Logowanie się w programie Azure PowerShell
description: Jak zalogować się w programie Azure PowerShell jako użytkownik albo za pomocą jednostki usługi lub tożsamości usługi zarządzanej.
author: sptramer
ms.author: sttramer
manager: carmonm
ms.devlang: powershell
ms.topic: conceptual
ms.date: 05/15/2017
ms.openlocfilehash: e2eb6767d16dd15529b35b7a4134f4dcdd257d60
ms.sourcegitcommit: 5a5b6dd216d5f805204244146cf6f88ad2f34fb4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/19/2018
ms.locfileid: "36237887"
---
# <a name="sign-in-with-azure-powershell"></a><span data-ttu-id="c7a3e-103">Logowanie się w programie Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="c7a3e-103">Sign in with Azure PowerShell</span></span>

<span data-ttu-id="c7a3e-104">Program Azure PowerShell obsługuje wiele metod logowania.</span><span class="sxs-lookup"><span data-stu-id="c7a3e-104">Azure PowerShell supports multiple login methods.</span></span> <span data-ttu-id="c7a3e-105">Najprostszym sposobem rozpoczęcia pracy jest interaktywne zalogowanie się w wierszu polecenia.</span><span class="sxs-lookup"><span data-stu-id="c7a3e-105">The simplest way to get started is to log in interactively at the command line.</span></span>

## <a name="sign-in-interactively"></a><span data-ttu-id="c7a3e-106">Logowanie interakcyjne</span><span class="sxs-lookup"><span data-stu-id="c7a3e-106">Sign in interactively</span></span>

<span data-ttu-id="c7a3e-107">Aby zalogować się interakcyjnie, skorzystaj z polecenia cmdlet [Connect-AzureRmAccount](/powershell/module/azurerm.profile/connect-azurermaccount).</span><span class="sxs-lookup"><span data-stu-id="c7a3e-107">To sign in interactively, use the [Connect-AzureRmAccount](/powershell/module/azurerm.profile/connect-azurermaccount) cmdlet.</span></span>

```azurepowershell
Connect-AzureRmAccount
```

<span data-ttu-id="c7a3e-108">Po uruchomieniu to polecenie cmdlet spowoduje otworzenie okna dialogowego z monitem o podanie adresu e-mail i hasła skojarzonego z kontem platformy Azure.</span><span class="sxs-lookup"><span data-stu-id="c7a3e-108">When run, this cmdlet will bring up a dialog box prompting you for your email address and password associated with your Azure account.</span></span> <span data-ttu-id="c7a3e-109">Po uwierzytelnieniu te informacje są zapisywane dla bieżącej sesji programu PowerShell, okno dialogowe jest zamykane i zapewniany jest dostęp do wszystkich poleceń cmdlet programu Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c7a3e-109">When you authenticate, that information is saved for the current PowerShell session, the dialog is closed, and you have access to all of the Azure PowerShell cmdlets.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c7a3e-110">Logowanie obowiązuje _tylko_ w ramach bieżącej sesji programu PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c7a3e-110">This sign in is for the current PowerShell session _only_.</span></span> <span data-ttu-id="c7a3e-111">Aby utrwalić logowanie na wiele sesji, zapoznaj się z artykułem [Poświadczenia trwałe](context-persistence.md).</span><span class="sxs-lookup"><span data-stu-id="c7a3e-111">To persist the login across multiple sessions, see the article on [Persistent Credentials](context-persistence.md).</span></span>

## <a name="sign-in-with-a-service-principal"></a><span data-ttu-id="c7a3e-112">Logowanie za pomocą jednostki usługi</span><span class="sxs-lookup"><span data-stu-id="c7a3e-112">Sign in with a service principal</span></span>

<span data-ttu-id="c7a3e-113">Jednostki usługi zapewniają możliwość tworzenia nieinteraktywnych kont, których możesz używać do manipulowania zasobami.</span><span class="sxs-lookup"><span data-stu-id="c7a3e-113">Service principals provide a way for you to create non-interactive accounts that you can use to manipulate resources.</span></span> <span data-ttu-id="c7a3e-114">Jednostki usługi są podobne do kont użytkowników, do których można zastosować reguły za pomocą usługi Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c7a3e-114">Service principals are like user accounts to which you can apply rules using Azure Active Directory.</span></span> <span data-ttu-id="c7a3e-115">Udzielając minimalnych uprawnień niezbędnych dla jednostki usługi, możesz zapewnić, że skrypty automatyzacji będą jeszcze bezpieczniejsze.</span><span class="sxs-lookup"><span data-stu-id="c7a3e-115">By granting the minimum permissions needed to a service principal, you can ensure your automation scripts are even more secure.</span></span>

<span data-ttu-id="c7a3e-116">Jeśli chcesz utworzyć jednostkę usługi do użycia z programem Azure PowerShell, zobacz [Tworzenie jednostki usługi platformy Azure za pomocą programu Azure PowerShell](create-azure-service-principal-azureps.md).</span><span class="sxs-lookup"><span data-stu-id="c7a3e-116">If you need to create a service principal for use with Azure PowerShell, see [Create an Azure service principal with Azure PowerShell](create-azure-service-principal-azureps.md).</span></span>

<span data-ttu-id="c7a3e-117">Aby zalogować się przy użyciu jednostki usługi, podaj argument `-ServicePrincipal` w poleceniu cmdlet `Connect-AzureRmAccount`.</span><span class="sxs-lookup"><span data-stu-id="c7a3e-117">To sign in with a service principal, use the `-ServicePrincipal` argument with the `Connect-AzureRmAccount` cmdlet.</span></span> <span data-ttu-id="c7a3e-118">Z jednostką usługi trzeba będzie również skojarzyć jej identyfikator aplikacji, poświadczenia logowania oraz identyfikator dzierżawy.</span><span class="sxs-lookup"><span data-stu-id="c7a3e-118">You will also need the service princpal's application ID, sign-in credentials, and the tenant ID associate with the service principal.</span></span> <span data-ttu-id="c7a3e-119">Aby pobrać poświadczenia jednostki usługi jako odpowiedni obiekt, użyj polecenia cmdlet [Get-Credential](/powershell/module/microsoft.powershell.security/get-credential).</span><span class="sxs-lookup"><span data-stu-id="c7a3e-119">In order to get the service principal's credentials as the appropriate object, use the [Get-Credential](/powershell/module/microsoft.powershell.security/get-credential) cmdlet.</span></span> <span data-ttu-id="c7a3e-120">To polecenie cmdlet spowoduje wyświetlenie okna dialogowego umożliwiającego wprowadzenie identyfikatora i hasła użytkownika.</span><span class="sxs-lookup"><span data-stu-id="c7a3e-120">This cmdlet will display a dialog box to enter the service principal user ID and password into.</span></span>

```azurepowershell-interactive
$pscredential = Get-Credential
Connect-AzureRmAccount -ServicePrincipal -ApplicationId  "http://my-app" -Credential $pscredential -TenantId $tenantid
```

## <a name="sign-in-using-an-azure-vm-managed-service-identity"></a><span data-ttu-id="c7a3e-121">Logowanie się za pomocą tożsamości usługi zarządzanej maszyny wirtualnej platformy Azure</span><span class="sxs-lookup"><span data-stu-id="c7a3e-121">Sign in using an Azure VM Managed Service Identity</span></span>

<span data-ttu-id="c7a3e-122">Tożsamość usługi zarządzanej (MSI) jest dostępna w wersji zapoznawczej usługi Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c7a3e-122">Managed Service Identity (MSI) is a preview feature of Azure Active Directory.</span></span> <span data-ttu-id="c7a3e-123">Jednostki usługi tożsamości usługi zarządzanej można używać do logowania się i uzyskiwania aplikacyjnego tokenu dostępu do uzyskania dostępu do innych zasobów.</span><span class="sxs-lookup"><span data-stu-id="c7a3e-123">You can use an MSI service principal for sign-in, and acquire an app-only access token to access other resources.</span></span> <span data-ttu-id="c7a3e-124">Tożsamość MSI jest dostępna tylko w przypadku maszyn wirtualnych działających w chmurze platformy Azure.</span><span class="sxs-lookup"><span data-stu-id="c7a3e-124">MSI is only available on virtual machines running in an Azure cloud.</span></span>

<span data-ttu-id="c7a3e-125">Aby uzyskać więcej informacji na temat tożsamości usługi zarządzanej, zobacz [How to use an Azure VM Managed Service Identity (MSI) for sign-in and token acquisition (Sposób użycia tożsamości usługi zarządzanej maszyny wirtualnej platformy Azure do logowania się i uzyskania tokenu)](/azure/active-directory/msi-how-to-get-access-token-using-msi).</span><span class="sxs-lookup"><span data-stu-id="c7a3e-125">For more information about MSI, see [How to use an Azure VM Managed Service Identity (MSI) for sign-in and token acquisition](/azure/active-directory/msi-how-to-get-access-token-using-msi).</span></span>

## <a name="sign-in-to-another-cloud"></a><span data-ttu-id="c7a3e-126">Logowanie się do innej chmury</span><span class="sxs-lookup"><span data-stu-id="c7a3e-126">Sign in to another Cloud</span></span>

<span data-ttu-id="c7a3e-127">Usługi w chmurze platformy Azure udostępniają różne środowiska zgodne z przepisami dotyczącymi obsługi danych obowiązującymi w różnych regionach.</span><span class="sxs-lookup"><span data-stu-id="c7a3e-127">Azure cloud services provide different environments that adhere to the data-handling regulations of various regions.</span></span> <span data-ttu-id="c7a3e-128">Jeśli konto platformy Azure znajduje się w chmurze skojarzonej z jednym z tych regionów, podczas logowania należy określić środowisko.</span><span class="sxs-lookup"><span data-stu-id="c7a3e-128">If your Azure account is in a cloud associated with one of these regions, you need to specify the environment when you sign in.</span></span> <span data-ttu-id="c7a3e-129">Jeśli na przykład konto należy do chmury chińskiej, rejestracja odbywa się za pomocą następującego polecenia:</span><span class="sxs-lookup"><span data-stu-id="c7a3e-129">For example, if you account is in the China cloud you sign on using the following command:</span></span>

```azurepowershell-interactive
Connect-AzureRmAccount -Environment AzureChinaCloud
```

<span data-ttu-id="c7a3e-130">Użyj następującego polecenia, aby uzyskać listę dostępnych środowisk:</span><span class="sxs-lookup"><span data-stu-id="c7a3e-130">Use the following command to get a list of available environments:</span></span>

```azurepowershell-interactive
Get-AzureRmEnvironment | Select-Object Name
```

## <a name="learn-more-about-managing-azure-role-based-access"></a><span data-ttu-id="c7a3e-131">Dowiedz się więcej o zarządzaniu dostępem opartym na rolach na platformie Azure</span><span class="sxs-lookup"><span data-stu-id="c7a3e-131">Learn more about managing Azure role-based access</span></span>

<span data-ttu-id="c7a3e-132">Aby uzyskać więcej informacji o zarządzaniu uwierzytelnianiem i subskrypcjami platformy Azure, zobacz [Zarządzanie kontami, subskrypcjami i rolami administracyjnymi](/azure/active-directory/role-based-access-control-configure).</span><span class="sxs-lookup"><span data-stu-id="c7a3e-132">For more information about authentication and subscription management in Azure, see [Manage Accounts, Subscriptions, and Administrative Roles](/azure/active-directory/role-based-access-control-configure).</span></span>

<span data-ttu-id="c7a3e-133">Polecenia cmdlet programu Azure PowerShell umożliwiające zarządzanie rolami:</span><span class="sxs-lookup"><span data-stu-id="c7a3e-133">Azure PowerShell cmdlets for role management:</span></span>

* [<span data-ttu-id="c7a3e-134">Get-AzureRmRoleAssignment</span><span class="sxs-lookup"><span data-stu-id="c7a3e-134">Get-AzureRmRoleAssignment</span></span>](/powershell/module/AzureRM.Resources/Get-AzureRmRoleAssignment)
* [<span data-ttu-id="c7a3e-135">Get-AzureRmRoleDefinition</span><span class="sxs-lookup"><span data-stu-id="c7a3e-135">Get-AzureRmRoleDefinition</span></span>](/powershell/module/AzureRM.Resources/Get-AzureRmRoleDefinition)
* [<span data-ttu-id="c7a3e-136">New-AzureRmRoleAssignment</span><span class="sxs-lookup"><span data-stu-id="c7a3e-136">New-AzureRmRoleAssignment</span></span>](/powershell/module/AzureRM.Resources/New-AzureRmRoleAssignment)
* [<span data-ttu-id="c7a3e-137">New-AzureRmRoleDefinition</span><span class="sxs-lookup"><span data-stu-id="c7a3e-137">New-AzureRmRoleDefinition</span></span>](/powershell/module/AzureRM.Resources/New-AzureRmRoleDefinition)
* [<span data-ttu-id="c7a3e-138">Remove-AzureRmRoleAssignment</span><span class="sxs-lookup"><span data-stu-id="c7a3e-138">Remove-AzureRmRoleAssignment</span></span>](/powershell/module/AzureRM.Resources/Remove-AzureRmRoleAssignment)
* [<span data-ttu-id="c7a3e-139">Remove-AzureRmRoleDefinition</span><span class="sxs-lookup"><span data-stu-id="c7a3e-139">Remove-AzureRmRoleDefinition</span></span>](/powershell/module/AzureRM.Resources/Remove-AzureRmRoleDefinition)
* [<span data-ttu-id="c7a3e-140">Set-AzureRmRoleDefinition</span><span class="sxs-lookup"><span data-stu-id="c7a3e-140">Set-AzureRmRoleDefinition</span></span>](/powershell/moduel/AzureRM.Resources/Set-AzureRmRoleDefinition)