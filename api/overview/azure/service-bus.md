---
title: Librerie del bus di servizio di Azure per .NET
description: Informazioni di riferimento sulle librerie del bus di servizio di Azure per .NET
keywords: Azure, .NET, SDK, API, bus di servizio
author: camsoper
ms.author: casoper
manager: douge
ms.date: 08/01/2017
ms.topic: reference
ms.prod: azure
ms.technology: azure
ms.devlang: dotnet
ms.service: multiple
ms.openlocfilehash: d4d3ac982794fc7533b97fe8c053730b4b39ff58
ms.sourcegitcommit: d95a6ad3774a49b16f652e40e7860e47636c7ad0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/28/2017
---
# <a name="azure-service-bus-libraries-for-net"></a>Librerie del bus di servizio di Azure per .NET

## <a name="overview"></a>Panoramica

Il [bus di servizio di Azure](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-messaging-overview) è un'infrastruttura di messaggistica che risiede tra le applicazioni e permette loro di scambiare messaggi offrendo scalabilità e resilienza migliori.

## <a name="client-library"></a>Libreria client

Installare il [pacchetto NuGet](https://www.nuget.org/packages/WindowsAzure.ServiceBus) direttamente dalla [Console di Gestione pacchetti][PackageManager] di Visual Studio.

#### <a name="visual-studio-package-manager"></a>Visual Studio - Gestione pacchetti

```powershell
Install-Package WindowsAzure.ServiceBus
```

### <a name="code-example"></a>Esempio di codice

Questo esempio invia un messaggio a una coda del bus di servizio.

```csharp
// using Microsoft.ServiceBus.Messaging;

QueueClient client = QueueClient.CreateFromConnectionString(connectionString, queueName);
BrokeredMessage message = new BrokeredMessage("This is a test message!");
client.Send(message);
```

> [!div class="nextstepaction"]
> [Esplorare le API client](/dotnet/api/overview/azure/servicebus/client)


## <a name="management-library"></a>Libreria di gestione

Installare il [pacchetto NuGet](https://www.nuget.org/packages/Microsoft.Azure.Management.ServiceBus.Fluent) direttamente dalla [Console di Gestione pacchetti][PackageManager] di Visual Studio o tramite l'[interfaccia della riga di comando di .NET Core][DotNetCLI].

#### <a name="visual-studio-package-manager"></a>Visual Studio - Gestione pacchetti

```powershell
Install-Package Microsoft.Azure.Management.ServiceBus.Fluent
```

#### <a name="net-core-cli"></a>Interfaccia della riga di comando di .NET Core

```bash
dotnet add package Microsoft.Azure.Management.ServiceBus.Fluent
```

### <a name="code-example"></a>Esempio di codice

Questo esempio crea una coda del bus di servizio con dimensioni massime di 1024 MB.

```csharp
// using Microsoft.Azure.Management.ServiceBus.Fluent;
// using Microsoft.Azure.Management.ServiceBus.Fluent.Models;

using (ServiceBusManagementClient client = new ServiceBusManagementClient(credentials))
{
    client.SubscriptionId = subscriptionId;
    QueueInner parameters = new QueueInner
    {
        MaxSizeInMegabytes = 1024
    };
    await client.Queues.CreateOrUpdateAsync(resourceGroupName, namespaceName, queueName, parameters);
}
```

> [!div class="nextstepaction"]
> [Esplorare le API di gestione](/dotnet/api/overview/azure/servicebus/management)

## <a name="samples"></a>Esempi

- [Service Bus Queue Basics - .Net](https://azure.microsoft.com/resources/samples/service-bus-dotnet-manage-queue-with-basic-features/) (Nozioni fondamentali sulle code del bus di servizio - .NET)
- [Service Bus Queue Advanced Features - .Net](https://azure.microsoft.com/resources/samples/service-bus-dotnet-manage-queue-with-advanced-features/) (Funzionalità avanzate delle code del bus di servizio - .NET)
- [Service Bus Publish/Subscribe Basics - .Net](https://azure.microsoft.com/resources/samples/service-bus-dotnet-manage-publish-subscribe-with-basic-features/) (Nozioni fondamentali su pubblicazione/sottoscrizione del bus di servizio - .NET)
- [Service Bus Publish/Subscribe Advanced Features - .Net](https://azure.microsoft.com/resources/samples/service-bus-dotnet-manage-publish-subscribe-with-advanced-features/) (Funzionalità avanzate di pubblicazione/sottoscrizione del bus di servizio - .NET)
- [Service Bus with Claims-Based Authorization - .Net](https://azure.microsoft.com/resources/samples/service-bus-dotnet-manage-with-claims-based-authorization/) (Autenticazione basata sulle attestazioni del bus di servizio - .NET)

Visualizzare l'[elenco completo](https://azure.microsoft.com/resources/samples/?term=service+bus) degli esempi di codice per il bus di servizio di Azure.


[PackageManager]: https://docs.microsoft.com/nuget/tools/package-manager-console
[DotNetCLI]: https://docs.microsoft.com/dotnet/core/tools/dotnet-add-package