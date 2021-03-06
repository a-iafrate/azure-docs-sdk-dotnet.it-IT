---
title: Librerie di Azure Resource Manager per .NET
description: Informazioni di riferimento sulle librerie di Azure Resource Manager per .NET
ms.date: 10/19/2017
ms.topic: reference
ms.service: multiple
ms.openlocfilehash: 6d3a27c5f7ba94f5579723cc4f798826c8bdefd6
ms.sourcegitcommit: 5d9b713653b3d03e1d0a67f6e126ee399d1c2a60
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/26/2018
ms.locfileid: "47190840"
---
# <a name="azure-resource-manager-libraries-for-net"></a>Librerie di Azure Resource Manager per .NET

## <a name="overview"></a>Panoramica

Gestione risorse di Azure consente di usare le risorse incluse nella soluzione come un gruppo.  Per altre informazioni su Resource Manager, vedere [Panoramica di Azure Resource Manager](https://docs.microsoft.com/azure/azure-resource-manager/resource-group-overview).

## <a name="management-library"></a>Libreria di gestione

La libreria di Azure Resource Manager per .NET consente di creare, aggiornare, eliminare ed elencare le risorse e i gruppi di risorse.

Installare il [pacchetto NuGet](https://www.nuget.org/packages/Microsoft.Azure.Management.ResourceManager.Fluent) direttamente dalla [Console di Gestione pacchetti][PackageManager] di Visual Studio o tramite l'[interfaccia della riga di comando di .NET Core][DotNetCLI].

#### <a name="visual-studio-package-manager"></a>Visual Studio - Gestione pacchetti

```powershell
Install-Package Microsoft.Azure.Management.ResourceManager.Fluent
```

```bash
dotnet add package Microsoft.Azure.Management.ResourceManager.Fluent
```

### <a name="example"></a>Esempio

Questo esempio crea un nuovo gruppo di risorse.

```csharp
/* Include these "using" directives.
using Microsoft.Azure.Management.ResourceManager.Fluent;
using Microsoft.Azure.Management.ResourceManager.Fluent.Core;
*/

IResourceGroup resourceGroup = azure.ResourceGroups
    .Define("ResourceGroupName")
    .WithRegion(Region.USWest)
    .Create();
```

> [!div class="nextstepaction"]
> [Esplorare le API di gestione](/dotnet/api/overview/azure/resources/management)


## <a name="samples"></a>Esempi

* [Gestire gruppi di risorse](https://github.com/Azure-Samples/resources-dotnet-manage-resource-group)
* [Gestire risorse](https://github.com/Azure-Samples/resources-dotnet-manage-resource)
* [Distribuire risorse con modelli ARM](https://github.com/Azure-Samples/resources-dotnet-deploy-using-arm-template)
* [Distribuire risorse con modelli ARM (con stato di avanzamento)](https://github.com/Azure-Samples/resources-dotnet-deploy-using-arm-template-with-progress)


[PackageManager]: https://docs.microsoft.com/nuget/tools/package-manager-console
[DotNetCLI]: https://docs.microsoft.com/dotnet/core/tools/dotnet-add-package
