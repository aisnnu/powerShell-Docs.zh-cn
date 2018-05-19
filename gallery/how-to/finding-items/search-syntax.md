---
ms.date: 06/12/2017
contributor: JKeithB
ms.topic: conceptual
keywords: 库,powershell,cmdlet,psgallery
title: 库搜索语法
ms.openlocfilehash: 4c0e357957ef970826ee90868db78ac07a14c804
ms.sourcegitcommit: e9ad4d85fd7eb72fb5bc37f6ca3ae1282ae3c6d7
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2018
---
# <a name="gallery-search-syntax"></a><span data-ttu-id="1ddd8-103">库搜索语法</span><span class="sxs-lookup"><span data-stu-id="1ddd8-103">Gallery Search Syntax</span></span>

<span data-ttu-id="1ddd8-104">PowerShell 库提供文本搜索框，可以在其中使用单词、短语和关键字表达式来缩小搜索结果的范围。</span><span class="sxs-lookup"><span data-stu-id="1ddd8-104">PowerShell Gallery offers a text searchbox where you can use words, phrases and keyword expressions to narrow down search results.</span></span>

## <a name="search-by-keywords"></a><span data-ttu-id="1ddd8-105">按关键字搜索</span><span class="sxs-lookup"><span data-stu-id="1ddd8-105">Search by Keywords</span></span>

    dsc azure sql

<span data-ttu-id="1ddd8-106">“搜索”将最大程度地查找包含所有 3 个关键字的相关文档，并返回匹配的文档。</span><span class="sxs-lookup"><span data-stu-id="1ddd8-106">Search will do its best effort to find relevant documents containing all 3 keywords, and return matching documents.</span></span>

## <a name="search-using-phrases-and-keywords"></a><span data-ttu-id="1ddd8-107">使用短语和关键字进行搜索</span><span class="sxs-lookup"><span data-stu-id="1ddd8-107">Search using Phrases and keywords</span></span>

    "azure sql" deployment

<span data-ttu-id="1ddd8-108">在引号（“”）之间输入短语将搜索更改为查找特定的短语而不是单独的关键字。</span><span class="sxs-lookup"><span data-stu-id="1ddd8-108">Entering a phrase between quotation marks ("") change the search to look for the particular phrase instead of separate keywords.</span></span>
<span data-ttu-id="1ddd8-109">匹配的文档通常应包含确切的短语“azure sql”，包括大写的变体。“Azure SQL”，并通常还包含“deployment”一词。</span><span class="sxs-lookup"><span data-stu-id="1ddd8-109">Matching documents should usually contain the exact phrase "azure sql", including variations on capitalization e.g. "Azure SQL", and also usually contain the word 'deployment'.</span></span>

## <a name="filtering-on-fields"></a><span data-ttu-id="1ddd8-110">按字段进行筛选</span><span class="sxs-lookup"><span data-stu-id="1ddd8-110">Filtering on fields</span></span>

<span data-ttu-id="1ddd8-111">通过将字段名称作为前缀加入搜索词，可以搜索特定项 ID（或“Id”或“id”），或一些其他字段。</span><span class="sxs-lookup"><span data-stu-id="1ddd8-111">You can search for a specific item ID (or 'Id' or 'id'), or certain other fields by prefixing search terms with the field name.</span></span>

<span data-ttu-id="1ddd8-112">目前可搜索的字段有“Id”、“Version”、“Tags”、“Author”、“Owner”、“Functions”、“Cmdlet”、“DscResources”和“PowerShellVersion”。</span><span class="sxs-lookup"><span data-stu-id="1ddd8-112">Currently the searchable fields are 'Id', 'Version', 'Tags', 'Author', 'Owner', 'Functions', 'Cmdlets', 'DscResources' and 'PowerShellVersion'.</span></span>

<span data-ttu-id="1ddd8-113">[ID 和标题之间的区别是什么？</span><span class="sxs-lookup"><span data-stu-id="1ddd8-113">[What's the difference between ID and Title?</span></span> <span data-ttu-id="1ddd8-114">ID 是在控制台中使用的名称。</span><span class="sxs-lookup"><span data-stu-id="1ddd8-114">ID is the name you use in the console.</span></span> <span data-ttu-id="1ddd8-115">标题是在搜索结果中的项页顶部所显示的内容。]</span><span class="sxs-lookup"><span data-stu-id="1ddd8-115">Title is what is shown at the top of the item page in search results.]</span></span>

## <a name="examples"></a><span data-ttu-id="1ddd8-116">示例</span><span class="sxs-lookup"><span data-stu-id="1ddd8-116">Examples</span></span>

    ID:"PSReadline"
    id:"AzureRM.Profile"

<span data-ttu-id="1ddd8-117">分别在其 ID 字段中查找具有“PSReadline”或“AzureRM.Profile”的项。</span><span class="sxs-lookup"><span data-stu-id="1ddd8-117">finds items with "PSReadline" or "AzureRM.Profile" in their ID field respectively.</span></span>

    Id:"AzureRM.Profile"

<span data-ttu-id="1ddd8-118">是另一种在其 ID 字段中查找具有“AzureRM.Profile”项的方法。</span><span class="sxs-lookup"><span data-stu-id="1ddd8-118">is another way to find items with "AzureRM.Profile" in their ID field.</span></span>

<span data-ttu-id="1ddd8-119">“Id”筛选器是一个子字符串匹配，因此，如果搜索以下内容：</span><span class="sxs-lookup"><span data-stu-id="1ddd8-119">The 'Id' filter is a substring match, so if you search for the following:</span></span>

    Id:"azure"

<span data-ttu-id="1ddd8-120">你将得到如“AzureRM.Profile”和“Azure.Storage”等结果。</span><span class="sxs-lookup"><span data-stu-id="1ddd8-120">You'll get results like 'AzureRM.Profile' and 'Azure.Storage'.</span></span>

<span data-ttu-id="1ddd8-121">你也可以搜索单个字段中的多个关键字。</span><span class="sxs-lookup"><span data-stu-id="1ddd8-121">You can also search for multiple keywords in a single field.</span></span> <span data-ttu-id="1ddd8-122">或混合和匹配字段。</span><span class="sxs-lookup"><span data-stu-id="1ddd8-122">Or mix and match fields.</span></span>

    id:azure tags:intellisense
    id:azure id:storage

<span data-ttu-id="1ddd8-123">并且，你可以执行短语搜索：</span><span class="sxs-lookup"><span data-stu-id="1ddd8-123">And you can perform phrase searches:</span></span>

    id:"azure.storage"


<span data-ttu-id="1ddd8-124">搜索具有 DSC 标记的所有项。</span><span class="sxs-lookup"><span data-stu-id="1ddd8-124">To search all items with DSC tag.</span></span>

    Tags:"DSC"

<span data-ttu-id="1ddd8-125">搜索具有指定函数的所有项。</span><span class="sxs-lookup"><span data-stu-id="1ddd8-125">To search all items with the specified function.</span></span>

    Functions:"Update-AzureRM"

<span data-ttu-id="1ddd8-126">搜索具有指定 cmdlet 的所有项。</span><span class="sxs-lookup"><span data-stu-id="1ddd8-126">To search all items with the specified cmdlet.</span></span>

    Cmdlets:"Get-AzureRmEnvironment"

<span data-ttu-id="1ddd8-127">搜索具有指定 DSC 资源名称的所有项。</span><span class="sxs-lookup"><span data-stu-id="1ddd8-127">To search all items with the specified DSC Resource name.</span></span>

    DscResources:"xArchive"

<span data-ttu-id="1ddd8-128">搜索具有指定 PowerShellVersion 的所有项</span><span class="sxs-lookup"><span data-stu-id="1ddd8-128">To search all items with the specified PowerShellVersion</span></span>

    PowerShellVersion:"5.0"
    PowerShellVersion:"3.0"
    PowerShellVersion:"2.0"


<span data-ttu-id="1ddd8-129">最后，如果你使用不支持的字段（如“commands”），我们将忽略该字段并搜索所有字段。</span><span class="sxs-lookup"><span data-stu-id="1ddd8-129">Finally, if you use a field we don't support, such as 'commands', we'll just ignore it and search all the fields.</span></span> <span data-ttu-id="1ddd8-130">因此以下查询</span><span class="sxs-lookup"><span data-stu-id="1ddd8-130">So the following query</span></span>

    commands:blobs storage

<span data-ttu-id="1ddd8-131">的解释与此查询完全相同：</span><span class="sxs-lookup"><span data-stu-id="1ddd8-131">Is interpreted exactly the same as this query:</span></span>

    blobs storage