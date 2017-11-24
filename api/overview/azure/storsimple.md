---
title: Librerie di Azure StorSimple per .NET
description: Informazioni di riferimento sulle librerie di Azure StorSimple per .NET
keywords: Azure, .NET, SDK, API, StorSimple
author: camsoper
ms.author: casoper
manager: wpickett
ms.date: 10/27/2017
ms.topic: reference
ms.prod: azure
ms.technology: azure
ms.devlang: dotnet
ms.service: storsimple
ms.custom: devcenter, svc-overview
ms.openlocfilehash: dcb6732bf1eded6852a3185546a09c96cfe84eca
ms.sourcegitcommit: 64c9e16e42894e8db8ed088487e55c5e0edd6861
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/31/2017
---
# <a name="azure-storsimple-libraries-for-net"></a><span data-ttu-id="036d3-104">Librerie di Azure StorSimple per .NET</span><span class="sxs-lookup"><span data-stu-id="036d3-104">Azure StorSimple libraries for .NET</span></span>

## <a name="overview"></a><span data-ttu-id="036d3-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="036d3-105">Overview</span></span>

<span data-ttu-id="036d3-106">Microsoft Azure StorSimple è una soluzione di archiviazione aziendale che fornisce interfacce iSCSI o SMB fisiche alla risorsa di archiviazione basata sul cloud.</span><span class="sxs-lookup"><span data-stu-id="036d3-106">Microsoft Azure StorSimple is an enterprise storage solution that provides physical iSCSI or SMB interfaces to cloud-based storage.</span></span> 

<span data-ttu-id="036d3-107">Altre informazioni su [Azure StorSimple](/azure/storsimple/).</span><span class="sxs-lookup"><span data-stu-id="036d3-107">Learn more about [Azure StorSimple](/azure/storsimple/).</span></span>    

## <a name="management-library"></a><span data-ttu-id="036d3-108">Libreria di gestione</span><span class="sxs-lookup"><span data-stu-id="036d3-108">Management library</span></span>

<span data-ttu-id="036d3-109">Installare il [pacchetto NuGet](https://www.nuget.org/packages/Microsoft.Azure.Management.StorSimple.Fluent) direttamente dalla [Console di Gestione pacchetti][PackageManager] di Visual Studio o tramite l'[interfaccia della riga di comando di .NET Core][DotNetCLI].</span><span class="sxs-lookup"><span data-stu-id="036d3-109">Install the [NuGet package](https://www.nuget.org/packages/Microsoft.Azure.Management.StorSimple.Fluent) directly from the Visual Studio [Package Manager console][PackageManager] or with the [.NET Core CLI][DotNetCLI].</span></span>

#### <a name="visual-studio-package-manager"></a><span data-ttu-id="036d3-110">Visual Studio - Gestione pacchetti</span><span class="sxs-lookup"><span data-stu-id="036d3-110">Visual Studio Package Manager</span></span>

```powershell
Install-Package Microsoft.Azure.Management.StorSimple.Fluent
```

```bash
dotnet add package Microsoft.Azure.Management.StorSimple.Fluent
```

> [!div class="nextstepaction"]
> [<span data-ttu-id="036d3-111">Esplorare le API di gestione</span><span class="sxs-lookup"><span data-stu-id="036d3-111">Explore the management APIs</span></span>](/dotnet/api/overview/azure/monitor/management)

## <a name="samples"></a><span data-ttu-id="036d3-112">Esempi</span><span class="sxs-lookup"><span data-stu-id="036d3-112">Samples</span></span>

<span data-ttu-id="036d3-113">Esplorare altro [codice .NET di esempio](https://azure.microsoft.com/resources/samples/?platform=dotnet) da usare nelle app.</span><span class="sxs-lookup"><span data-stu-id="036d3-113">Explore more [sample .NET code](https://azure.microsoft.com/resources/samples/?platform=dotnet) you can use in your apps.</span></span>

[PackageManager]: https://docs.microsoft.com/nuget/tools/package-manager-console
[DotNetCLI]: https://docs.microsoft.com/dotnet/core/tools/dotnet-add-package