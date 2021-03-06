---
title: Librerie di Analisi di flusso di Azure per .NET
description: Informazioni di riferimento sulle librerie di Analisi di flusso di Azure per .NET
ms.date: 10/19/2017
ms.topic: reference
ms.service: stream-analytics
ms.openlocfilehash: c04a5c8a7b1d7e0f283d4fb81bd772de24f195eb
ms.sourcegitcommit: 5d9b713653b3d03e1d0a67f6e126ee399d1c2a60
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/26/2018
ms.locfileid: "47190454"
---
# <a name="azure-stream-analytics-libraries-for-net"></a>Librerie di Analisi di flusso di Azure per .NET

## <a name="overview"></a>Panoramica

[Analisi di flusso di Azure](/azure/stream-analytics/stream-analytics-introduction) è un motore di elaborazione di eventi completamente gestito che consente di configurare calcoli di analisi in tempo reale sui dati di streaming. I dati possono provenire da dispositivi, sensori, siti Web, feed di social media, applicazioni, sistemi di infrastruttura e altro ancora. 

Per altre informazioni su Analisi di flusso di Azure, vedere [Introduzione al rilevamento di illeciti in tempo reale con Analisi di flusso di Azure](/azure/stream-analytics/stream-analytics-real-time-fraud-detection).


## <a name="management-library"></a>Libreria di gestione

Usare la libreria di gestione di Analisi di flusso di Azure per creare, avviare e arrestare processi di Analisi di flusso di Azure.

Installare il [pacchetto NuGet](https://www.nuget.org/packages/Microsoft.Azure.Management.StreamAnalytics) direttamente dalla [Console di Gestione pacchetti][PackageManager] di Visual Studio o tramite l'[interfaccia della riga di comando di .NET Core][DotNetCLI].

#### <a name="visual-studio-package-manager"></a>Visual Studio - Gestione pacchetti

```powershell
Install-Package Microsoft.Azure.Management.StreamAnalytics
```

```bash
dotnet add package Microsoft.Azure.Management.StreamAnalytics
```

### <a name="code-example"></a>Esempio di codice

Questo esempio crea istanze di un client di Analisi di flusso e crea un processo di streaming.

```csharp
/* Include these 'using' directives:
using Microsoft.Azure.Management.StreamAnalytics;
*/
SynchronizationContext.SetSynchronizationContext(new SynchronizationContext());

// Get credentials
ServiceClientCredentials credentials = GetCredentials().Result;

// Create Stream Analytics management client
StreamAnalyticsManagementClient streamAnalyticsManagementClient = new StreamAnalyticsManagementClient(credentials)
{
    SubscriptionId = subscriptionId
};

// Create a streaming job
StreamingJob streamingJob = new StreamingJob()
{
    Tags = new Dictionary<string, string>()
    {
        { "Origin", ".NET SDK" },
        { "ReasonCreated", "Getting started tutorial" }
    },
    Location = "West US",
    EventsOutOfOrderPolicy = EventsOutOfOrderPolicy.Drop,
    EventsOutOfOrderMaxDelayInSeconds = 5,
    EventsLateArrivalMaxDelayInSeconds = 16,
    OutputErrorPolicy = OutputErrorPolicy.Drop,
    DataLocale = "en-US",
    CompatibilityLevel = CompatibilityLevel.OneFullStopZero,
    Sku = new Sku()
    {
        Name = SkuName.Standard
    }
};
StreamingJob createStreamingJobResult = streamAnalyticsManagementClient.StreamingJobs.CreateOrReplace(streamingJob, resourceGroupName, streamingJobName);
```

> [!div class="nextstepaction"]
> [Esplorare le API di gestione](/dotnet/api/overview/azure/streamanalytics/management)


## <a name="samples"></a>Esempi

- [Management .NET SDK: impostare ed eseguire processi di analisi tramite l'API di Analisi di flusso di Azure per .NET](/azure/stream-analytics/stream-analytics-dotnet-management-sdk)

Visualizzare l'[elenco completo](https://azure.microsoft.com/resources/samples/?platform=dotnet&service=stream-analytics) degli esempi di codice per Analisi di flusso di Azure.

[PackageManager]: https://docs.microsoft.com/nuget/tools/package-manager-console
[DotNetCLI]: https://docs.microsoft.com/dotnet/core/tools/dotnet-add-package
