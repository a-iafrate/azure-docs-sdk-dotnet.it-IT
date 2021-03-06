---
title: API di archiviazione di Azure per .NET
description: Informazioni di riferimento sulle librerie di archiviazione di Azure per .NET
ms.date: 10/19/2017
ms.topic: reference
ms.service: storage
ms.openlocfilehash: 2f278f0e3cb10d11190d529f427fa64040ee8b1d
ms.sourcegitcommit: 5d9b713653b3d03e1d0a67f6e126ee399d1c2a60
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/26/2018
ms.locfileid: "47189974"
---
# <a name="azure-storage-apis-for-net"></a>API di archiviazione di Azure per .NET

## <a name="overview"></a>Panoramica

Eseguire la lettura e la scrittura di file, dati di BLOB (oggetto), coppie chiave-valore e messaggi dalle applicazioni .NET con l'[Archiviazione di Azure](https://docs.microsoft.com/azure/storage/storage-introduction).

Per iniziare a usare Archiviazione di Azure, vedere [Introduzione all'archivio BLOB di Azure con .NET](/azure/storage/storage-dotnet-how-to-use-blobs).

## <a name="client-library"></a>Libreria client

Usare le [stringhe di connessione](/azure/storage/storage-create-storage-account#manage-your-storage-account) per connettersi a un account di archiviazione di Azure e quindi usare le classi e i metodi delle librerie client per usare l'archiviazione BLOB, tabelle, file o code.

Installare il [pacchetto NuGet](https://www.nuget.org/packages/WindowsAzure.Storage) direttamente dalla [Console di Gestione pacchetti][PackageManager] di Visual Studio o tramite l'[interfaccia della riga di comando di .NET Core][DotNetCLI].

#### <a name="visual-studio-package-manager"></a>Visual Studio - Gestione pacchetti

```powershell
Install-Package WindowsAzure.Storage
```

### <a name="net-core-cli"></a>Interfaccia della riga di comando di .NET Core

```bash
dotnet add package WindowsAzure.Storage
```

### <a name="code-example"></a>Esempio di codice

Questo esempio mostra come creare un nuovo BLOB in un nuovo contenitore in un account di archiviazione esistente.

```csharp
/* Include these "using" directives...
using Microsoft.WindowsAzure.Storage;
using Microsoft.WindowsAzure.Storage.Blob;
*/

string storageConnectionString = "DefaultEndpointsProtocol=https;"
    + "AccountName=[Storage Account Name]"
    + ";AccountKey=[Storage Account Key]"
    + ";EndpointSuffix=core.windows.net";

CloudStorageAccount account = CloudStorageAccount.Parse(storageConnectionString);
CloudBlobClient serviceClient = account.CreateCloudBlobClient();

// Create container. Name must be lower case.
Console.WriteLine("Creating container...");
var container = serviceClient.GetContainerReference("mycontainer");
container.CreateIfNotExistsAsync().Wait();

// write a blob to the container
CloudBlockBlob blob = container.GetBlockBlobReference("helloworld.txt");
blob.UploadTextAsync("Hello, World!").Wait();
```

> [!div class="nextstepactions"]
> [Esplorare le API client](/dotnet/api/overview/azure/storage/client)

## <a name="management-apis"></a>API di gestione

Creare e gestire account di archiviazione di Azure e chiavi di connessione con l'API di gestione.

Installare il [pacchetto NuGet](https://www.nuget.org/packages/Microsoft.Azure.Management.Storage.Fluent) direttamente dalla [Console di Gestione pacchetti][PackageManager] di Visual Studio o tramite l'[interfaccia della riga di comando di .NET Core][DotNetCLI].

#### <a name="visual-studio-package-manager"></a>Visual Studio - Gestione pacchetti

```powershell
Install-Package Microsoft.Azure.Management.Storage.Fluent
```

#### <a name="net-core-cli"></a>Interfaccia della riga di comando di .NET Core

````bash
dotnet add package Microsoft.Azure.Management.Storage.Fluent
````

### <a name="code-example"></a>Esempio di codice

Questo esempio mostra come creare un account di archiviazione.

```csharp
/* Include this "using" directive...
using Microsoft.Azure.Management.Storage.Fluent
*/

IStorageAccount storage = azure.StorageAccounts.Define(storageAccountName)
    .WithRegion(Region.USEast)
    .WithNewResourceGroup(rgName)
    .Create();
```

> [!div class="nextstepactions"]
> [Esplorare le API di gestione](/dotnet/api/overview/azure/storage/management)

## <a name="samples"></a>Esempi

* [Introduzione all'archivio BLOB di Azure con .NET](https://azure.microsoft.com/resources/samples/storage-blob-dotnet-getting-started/) 
* [Get started with Azure Queue Storage in .NET](https://azure.microsoft.com/resources/samples/storage-queue-dotnet-getting-started/) (Introduzione all'archiviazione code di Azure con .NET)

Visualizzare l'[elenco completo](https://azure.microsoft.com/resources/samples/?platform=dotnet&term=storage) degli esempi di codice per Archiviazione di Azure.

[PackageManager]: https://docs.microsoft.com/nuget/tools/package-manager-console
[DotNetCLI]: https://docs.microsoft.com/dotnet/core/tools/dotnet-add-package