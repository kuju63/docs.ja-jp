---
title: .NET 用 Azure ライブラリの認証を理解する
description: Azure SDK for .NET を利用したさまざまな認証について説明します。
ms.date: 06/19/2020
ms.custom: azure-sdk-dotnet
ms.openlocfilehash: 5ed29d5485dc7f59bcc757c8903116edf6bd5d7d
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174874"
---
# <a name="authenticate-with-the-azure-sdk-for-net"></a><span data-ttu-id="0d267-103">Azure SDK for .NET を使用した認証</span><span class="sxs-lookup"><span data-stu-id="0d267-103">Authenticate with the Azure SDK for .NET</span></span>

## <a name="recommended-azureidentity"></a><span data-ttu-id="0d267-104">推奨:Azure.Identity</span><span class="sxs-lookup"><span data-stu-id="0d267-104">Recommended: Azure.Identity</span></span>

<span data-ttu-id="0d267-105">Azure SDK for .NET の最新パッケージでは、共通の認証パッケージを使用して認証します。`Azure.Identity` です。</span><span class="sxs-lookup"><span data-stu-id="0d267-105">The latest packages in the Azure SDK for .NET use a common authentication package to authenticate, `Azure.Identity`.</span></span> <span data-ttu-id="0d267-106">`Azure.Identity` の使用は、このドキュメントの後半で説明する他の認証メカニズムよりも推奨されています。</span><span class="sxs-lookup"><span data-stu-id="0d267-106">Using `Azure.Identity` is recommended over other authentication mechanisms described later in this document.</span></span> <span data-ttu-id="0d267-107">`Azure.Identity` から提供される資格情報をサポートするパッケージには、*Azure* で始まるパッケージ識別子が与えられています。</span><span class="sxs-lookup"><span data-stu-id="0d267-107">Packages supporting the credentials provided by `Azure.Identity` have package identifiers starting with *Azure.*</span></span> <span data-ttu-id="0d267-108">[詳細については、Azure SDK for .NET の最新リリースをご覧ください](https://azure.github.io/azure-sdk/releases/latest/index.html#net)。</span><span class="sxs-lookup"><span data-stu-id="0d267-108">[For more information, see the latest releases in the Azure SDK for .NET](https://azure.github.io/azure-sdk/releases/latest/index.html#net).</span></span>

<span data-ttu-id="0d267-109">プロジェクトで `Azure.Identity` を使用する方法の詳細については、[.NET 用 Azure Identity クライアント](/dotnet/api/overview/azure/identity-readme)に関するドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0d267-109">For complete instructions on using `Azure.Identity` in your project, see the documentation for [Azure Identity client for .NET](/dotnet/api/overview/azure/identity-readme).</span></span>

> [!TIP]
> <span data-ttu-id="0d267-110">Azure Identity を使用して Azure リソースにアクセスし、管理する例については、「[Azure Identity、Resource Management、Storage のサンプル](/samples/dotnet/samples/azure-identity-resource-management-storage/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0d267-110">See the [Azure Identity, Resource Management, and Storage sample](/samples/dotnet/samples/azure-identity-resource-management-storage/) for examples of using Azure Identity to manage and access Azure resources.</span></span>

<span data-ttu-id="0d267-111">Azure.Identity をサポートしないライブラリで認証するには、このトピックの残りを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0d267-111">To authenticate with libraries that don't support Azure.Identity, see the rest of this topic.</span></span>

## <a name="access-azure-resources"></a><span data-ttu-id="0d267-112">Azure リソースにアクセスする</span><span class="sxs-lookup"><span data-stu-id="0d267-112">Access Azure resources</span></span>

<span data-ttu-id="0d267-113">Key Vault からシークレットを取得したり、Storage に BLOB を保管したりするなど、Azure リソースの操作には、さまざまな Azure サービス ライブラリで認証のための接続文字列やキーが必要になります。</span><span class="sxs-lookup"><span data-stu-id="0d267-113">To interact with Azure resources, such as retrieving a secret from Key Vault or storing a blob in Storage, many Azure service libraries require a connection string or keys for authentication.</span></span> <span data-ttu-id="0d267-114">たとえば、SQL Database では[標準の SQL 接続文字列](https://docs.microsoft.com/azure/azure-sql/database/connect-query-dotnet-core)が使用されます。</span><span class="sxs-lookup"><span data-stu-id="0d267-114">For example, SQL Database uses a [standard SQL connection string](https://docs.microsoft.com/azure/azure-sql/database/connect-query-dotnet-core).</span></span> <span data-ttu-id="0d267-115">[CosmosDB](/azure/cosmos-db/)、[Azure Cache for Redis](/azure/azure-cache-for-redis/cache-dotnet-how-to-use-azure-redis-cache)、および [Service Bus](/azure/service-bus-messaging/service-bus-dotnet-get-started-with-queues) などの他の Azure サービスでは、サービス接続文字列が使用されます。</span><span class="sxs-lookup"><span data-stu-id="0d267-115">Service connection strings are used in other Azure services like [CosmosDB](/azure/cosmos-db/), [Azure Cache for Redis](/azure/azure-cache-for-redis/cache-dotnet-how-to-use-azure-redis-cache), and [Service Bus](/azure/service-bus-messaging/service-bus-dotnet-get-started-with-queues).</span></span> <span data-ttu-id="0d267-116">これらの文字列は、Azure portal、CLI、または PowerShell を使用して取得できます。</span><span class="sxs-lookup"><span data-stu-id="0d267-116">You can get those strings using the Azure portal, CLI, or PowerShell.</span></span> <span data-ttu-id="0d267-117">また、コード内から .NET 用 Azure 管理ライブラリを使い、リソースを照会することによって接続文字列を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="0d267-117">You can also use the Azure management libraries for .NET to query resources to build connection strings in your code.</span></span>

<span data-ttu-id="0d267-118">接続文字列の使用方法は製品によって異なります。</span><span class="sxs-lookup"><span data-stu-id="0d267-118">The methods for using a connection string vary by product.</span></span> <span data-ttu-id="0d267-119">[こちらの Azure 製品ドキュメントをご覧ください](/azure/?product=featured)。</span><span class="sxs-lookup"><span data-stu-id="0d267-119">[Refer to the documentation for your Azure product](/azure/?product=featured).</span></span>

## <a name="manage-azure-resources"></a><span data-ttu-id="0d267-120">Azure のリソースを管理する</span><span class="sxs-lookup"><span data-stu-id="0d267-120">Manage Azure resources</span></span>

[!include[Create service principal](includes/create-sp.md)]

<span data-ttu-id="0d267-121">サービス プリンシパルを作成した後は、リソースを作成および管理するサービス プリンシパルの認証に 2 つのオプションを利用できます。</span><span class="sxs-lookup"><span data-stu-id="0d267-121">Now that the service principal is created, two options are available to authenticate to the service principal to create and manage resources.</span></span>

<span data-ttu-id="0d267-122">どちらのオプションでも、次の NuGet パッケージをプロジェクトに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0d267-122">For both options you will need to add the following NuGet packages to your project.</span></span>

```powershell
Install-Package Microsoft.Azure.Management.Fluent
Install-Package Microsoft.Azure.Management.ResourceManager.Fluent
```

### <a name="authenticate-with-token-credentials"></a><span data-ttu-id="0d267-123">トークン資格情報で認証を行う</span><span class="sxs-lookup"><span data-stu-id="0d267-123">Authenticate with token credentials</span></span>

<span data-ttu-id="0d267-124">最初の方法では、コードでトークン資格情報オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="0d267-124">The first method is to build the token credential object in code.</span></span> <span data-ttu-id="0d267-125">構成ファイル、レジストリ、または Azure Key Vault に、資格情報を安全に保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0d267-125">You should store the credentials securely in a configuration file, the registry, or Azure KeyVault.</span></span>

```csharp
var credentials = SdkContext.AzureCredentialsFactory
    .FromServicePrincipal(clientId,
        clientSecret,
        tenantId,
        AzureEnvironment.AzureGlobalCloud);
```

<span data-ttu-id="0d267-126">サービス プリンシパル作成時の JSON 出力の *clientId*、*clientSecret*、および *tenantId* 値を使用します。</span><span class="sxs-lookup"><span data-stu-id="0d267-126">Use the *clientId*, *clientSecret*, and *tenantId* values from the JSON output when you created the service principal.</span></span>

<span data-ttu-id="0d267-127">その後、API を使うためのエントリ ポイントとなる `Azure` オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="0d267-127">Then create the entry point `Azure` object to start working with the API:</span></span>

```csharp
var azure = Microsoft.Azure.Management.Fluent.Azure
    .Configure()
    .Authenticate(credentials)
    .WithDefaultSubscription();
```

### <a name="file-based-authentication"></a><a name="mgmt-file"></a><span data-ttu-id="0d267-128">ファイルベースの認証</span><span class="sxs-lookup"><span data-stu-id="0d267-128">File-based authentication</span></span>

<span data-ttu-id="0d267-129">ファイルベースの認証を使うと、プレーンテキスト ファイルにサービス プリンシパルの資格情報を格納し、ファイル システム内で保護できます。</span><span class="sxs-lookup"><span data-stu-id="0d267-129">File-based authentication allows you to put the service principal credentials in a plain text file and secure it within the file system.</span></span>

[!include[File-based authentication](includes/file-based-auth.md)]

<span data-ttu-id="0d267-130">ファイルの内容を読み取り、API を使うためのエントリ ポイントとなる `Azure` オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="0d267-130">Read the contents of the file and create the entry point `Azure` object to start working with the API:</span></span>

```csharp
// pull in the location of the authentication properties file from the environment
var credentials = SdkContext.AzureCredentialsFactory
    .FromFile(Environment.GetEnvironmentVariable("AZURE_AUTH_LOCATION"));

var azure = Microsoft.Azure.Management.Fluent.Azure
    .Configure()
    .Authenticate(credentials)
    .WithDefaultSubscription();
```