---
title: .NET Framework による複数のプラットフォームの開発
ms.date: 10/21/2020
ms.assetid: b153baaa-130c-4169-860b-e580591de91e
ms.openlocfilehash: ef8fae4238f404d650528d25ab873fa48e2c0703
ms.sourcegitcommit: 279fb6e8d515df51676528a7424a1df2f0917116
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92688156"
---
# <a name="develop-for-multiple-platforms-with-net-framework"></a><span data-ttu-id="5093b-102">.NET Framework を使用して複数のプラットフォームを開発する</span><span class="sxs-lookup"><span data-stu-id="5093b-102">Develop for multiple platforms with .NET Framework</span></span>

<span data-ttu-id="5093b-103">.NET Framework と Visual Studio を使用して、Microsoft と Microsoft 以外の両方のプラットフォームを対象としたアプリを開発できます。</span><span class="sxs-lookup"><span data-stu-id="5093b-103">You can develop apps for both Microsoft and non-Microsoft platforms by using .NET Framework and Visual Studio.</span></span>

[!INCLUDE [net-framework-future](../../../includes/net-framework-future.md)]

## <a name="options-for-cross-platform-development"></a><span data-ttu-id="5093b-104">クロスプラットフォーム開発のオプション</span><span class="sxs-lookup"><span data-stu-id="5093b-104">Options for cross-platform development</span></span>

[!INCLUDE[standard](../../../includes/pcl-to-standard.md)]

<span data-ttu-id="5093b-105">複数プラットフォームを対象として開発する場合は、ソース コードやバイナリを共有し、.NET Framework コードと Windows ランタイム API の間で呼び出しを実行できます。</span><span class="sxs-lookup"><span data-stu-id="5093b-105">To develop for multiple platforms, you can share source code or binaries, and you can make calls between .NET Framework code and Windows Runtime APIs.</span></span>

|<span data-ttu-id="5093b-106">目的</span><span class="sxs-lookup"><span data-stu-id="5093b-106">If you want to...</span></span>|<span data-ttu-id="5093b-107">用途</span><span class="sxs-lookup"><span data-stu-id="5093b-107">Use...</span></span>|
|-----------------------|------------|
|<span data-ttu-id="5093b-108">Windows Phone 8.1 アプリと Windows 8.1 アプリの間でソース コードを共有する</span><span class="sxs-lookup"><span data-stu-id="5093b-108">Share source code between Windows Phone 8.1 and Windows 8.1 apps</span></span>|<span data-ttu-id="5093b-109">**共有プロジェクト** (Visual Studio 2013 更新プログラム 2 のユニバーサル アプリ テンプレート)。</span><span class="sxs-lookup"><span data-stu-id="5093b-109">**Shared projects** (Universal Apps template in Visual Studio 2013, Update 2).</span></span><br /><br /> <span data-ttu-id="5093b-110">-  Visual Basic は現在サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="5093b-110">-   Currently no Visual Basic support.</span></span><br /><span data-ttu-id="5093b-111">-  #`if` ステートメントを使用してプラットフォーム固有のコードを分離できます。</span><span class="sxs-lookup"><span data-stu-id="5093b-111">-   You can separate platform-specific code by using #`if` statements.</span></span><br /><br /> <span data-ttu-id="5093b-112">詳細については、次の情報を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5093b-112">For details, see:</span></span><br /><br /> <span data-ttu-id="5093b-113">-   [コーディングを開始する](/windows/uwp/get-started/create-uwp-apps)</span><span class="sxs-lookup"><span data-stu-id="5093b-113">-   [Start coding](/windows/uwp/get-started/create-uwp-apps)</span></span><br /><span data-ttu-id="5093b-114">-   [Visual Studio を使用したユニバーサル XAML アプリのビルド](https://devblogs.microsoft.com/visualstudio/using-visual-studio-to-build-universal-xaml-apps/) (ブログ記事)</span><span class="sxs-lookup"><span data-stu-id="5093b-114">-   [Using Visual Studio to build Universal XAML Apps](https://devblogs.microsoft.com/visualstudio/using-visual-studio-to-build-universal-xaml-apps/) (blog post)</span></span><br /><span data-ttu-id="5093b-115">-   [Visual Studio を使用した XAML 収束アプリの構築](https://channel9.msdn.com/Events/Build/2014/3-591) (ビデオ)</span><span class="sxs-lookup"><span data-stu-id="5093b-115">-   [Using Visual Studio to Build XAML Converged Apps](https://channel9.msdn.com/Events/Build/2014/3-591) (video)</span></span>|
|<span data-ttu-id="5093b-116">異なるプラットフォームを対象とするアプリ間でバイナリを共有する</span><span class="sxs-lookup"><span data-stu-id="5093b-116">Share binaries between apps that target different platforms</span></span>|<span data-ttu-id="5093b-117">プラットフォームに依存しないコードの **ポータブル クラス ライブラリ プロジェクト** 。</span><span class="sxs-lookup"><span data-stu-id="5093b-117">**Portable Class Library projects** for code that is platform-agnostic.</span></span><br /><br /> <span data-ttu-id="5093b-118">-  この方法は通常、ビジネス ロジックを実装するコードに使用されます。</span><span class="sxs-lookup"><span data-stu-id="5093b-118">-   This approach is typically used for code that implements business logic.</span></span><br /><span data-ttu-id="5093b-119">-  Visual Basic または C# を使用できます。</span><span class="sxs-lookup"><span data-stu-id="5093b-119">-   You can use Visual Basic or C#.</span></span><br /><span data-ttu-id="5093b-120">-  API のサポートはプラットフォームによって異なります。</span><span class="sxs-lookup"><span data-stu-id="5093b-120">-   API support varies by platform.</span></span><br /><span data-ttu-id="5093b-121">-  Windows 8.1 および Windows Phone 8.1 を対象としたポータブル クラス ライブラリ プロジェクトでは、Windows ランタイム API と XAML がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="5093b-121">-   Portable Class Library projects that target Windows 8.1 and Windows Phone 8.1 support Windows Runtime APIs and XAML.</span></span> <span data-ttu-id="5093b-122">これらの機能は、古いバージョンのポータブル クラス ライブラリでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="5093b-122">These features aren't available in older versions of the Portable Class Library.</span></span><br /><span data-ttu-id="5093b-123">-  必要に応じて、インターフェイスまたは抽象クラスを使用してプラットフォーム固有のコードを抽象化できます。</span><span class="sxs-lookup"><span data-stu-id="5093b-123">-   If needed, you can abstract out platform-specific code by using interfaces or abstract classes.</span></span><br /><br /> <span data-ttu-id="5093b-124">詳細については、次の情報を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5093b-124">For details, see:</span></span><br /><br /> <span data-ttu-id="5093b-125">-   [ポータブル クラス ライブラリ](portable-class-library.md)</span><span class="sxs-lookup"><span data-stu-id="5093b-125">-   [Portable Class Library](portable-class-library.md)</span></span><br /><span data-ttu-id="5093b-126">-   [ポータブル クラス ライブラリの作成方法](/archive/blogs/dsplaisted/how-to-make-portable-class-libraries-work-for-you) (ブログ記事)</span><span class="sxs-lookup"><span data-stu-id="5093b-126">-   [How to Make Portable Class Libraries Work for You](/archive/blogs/dsplaisted/how-to-make-portable-class-libraries-work-for-you) (blog post)</span></span><br /><span data-ttu-id="5093b-127">-   [MVVM を利用した汎用性のあるクラス ライブラリの使用](using-portable-class-library-with-model-view-view-model.md)</span><span class="sxs-lookup"><span data-stu-id="5093b-127">-   [Using Portable Class Library with MVVM](using-portable-class-library-with-model-view-view-model.md)</span></span> <br /><span data-ttu-id="5093b-128">-   [複数のプラットフォームを対象とするライブラリのアプリ リソース](app-resources-for-libraries-that-target-multiple-platforms.md)</span><span class="sxs-lookup"><span data-stu-id="5093b-128">-   [App Resources for Libraries That Target Multiple Platforms](app-resources-for-libraries-that-target-multiple-platforms.md)</span></span> <br /><span data-ttu-id="5093b-129">-   [.NET 移植性アナライザー](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer) (Visual Studio 拡張機能)</span><span class="sxs-lookup"><span data-stu-id="5093b-129">-   [.NET Portability Analyzer](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer) (Visual Studio extension)</span></span>|
|<span data-ttu-id="5093b-130">Windows 8.1 および Windows Phone 8.1 以外のプラットフォームを対象としたアプリの間でソース コードを共有する</span><span class="sxs-lookup"><span data-stu-id="5093b-130">Share source code between apps for platforms other than Windows 8.1 and Windows Phone 8.1</span></span>|<span data-ttu-id="5093b-131">**[リンクとして追加]** 機能。</span><span class="sxs-lookup"><span data-stu-id="5093b-131">**Add as link** feature.</span></span><br /><br /> <span data-ttu-id="5093b-132">-  この方法は、両方のアプリに共通しているが、何らかの理由で移植できないアプリ ロジックに適しています。</span><span class="sxs-lookup"><span data-stu-id="5093b-132">-   This approach is suitable for app logic that's common to both apps but not portable, for some reason.</span></span> <span data-ttu-id="5093b-133">この機能は Visual Basic または Visual C# のコードに使用できます。</span><span class="sxs-lookup"><span data-stu-id="5093b-133">You can use this feature for C# or Visual Basic code.</span></span><br />     <span data-ttu-id="5093b-134">たとえば Windows Phone 8 と Windows 8 は Windows ランタイム API を共有しますが、ポータブル クラス ライブラリはこれらのプラットフォームでは Windows ランタイムをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="5093b-134">For example, Windows Phone 8 and Windows 8 share Windows Runtime APIs, but Portable Class Libraries do not support Windows Runtime for those platforms.</span></span> <span data-ttu-id="5093b-135">Windows Phone 8 アプリと、Windows 8 を対象とした Windows ストア アプリの間で共通する Windows ランタイム コードを共有するには、`Add as link` を使用できます。</span><span class="sxs-lookup"><span data-stu-id="5093b-135">You can use `Add as link` to share common Windows Runtime code between a Windows Phone 8 app and a Windows Store app that targets Windows 8.</span></span><br /><br /> <span data-ttu-id="5093b-136">詳細については、次の情報を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5093b-136">For details, see:</span></span><br /><br /> <span data-ttu-id="5093b-137">-   [[リンクとして追加] でコードを共有する](/previous-versions/windows/apps/jj714082(v=vs.105))</span><span class="sxs-lookup"><span data-stu-id="5093b-137">-   [Share code with Add as Link](/previous-versions/windows/apps/jj714082(v=vs.105))</span></span><br /><span data-ttu-id="5093b-138">-   [方法: 既存の項目をプロジェクトに追加する](/previous-versions/visualstudio/visual-studio-2010/9f4t9t92(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="5093b-138">-   [How to: Add Existing Items to a Project](/previous-versions/visualstudio/visual-studio-2010/9f4t9t92(v=vs.100))</span></span>|
|<span data-ttu-id="5093b-139">.NET Framework を使用して Windows ストア アプリを作成するか、または .NET Framework コードから Windows ランタイム API を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="5093b-139">Write Windows Store apps using the .NET Framework or call Windows Runtime APIs from .NET Framework code</span></span>|<span data-ttu-id="5093b-140">.NET Framework C# または Visual Basic コードの **Windows ランタイム API** 。 .NET Framework を使用して Windows ストア アプリを作成します。</span><span class="sxs-lookup"><span data-stu-id="5093b-140">**Windows Runtime APIs** from your .NET Framework C# or Visual Basic code, and use the .NET Framework to create Windows Store apps.</span></span> <span data-ttu-id="5093b-141">2 つのプラットフォーム間の API の違いについて注意してください。</span><span class="sxs-lookup"><span data-stu-id="5093b-141">You should be aware of API differences between the two platforms.</span></span> <span data-ttu-id="5093b-142">ただし、これらの違いに対処するためのクラスがあります。</span><span class="sxs-lookup"><span data-stu-id="5093b-142">However, there are classes to help you work with those differences.</span></span><br /><br /> <span data-ttu-id="5093b-143">詳細については、次の情報を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5093b-143">For details, see:</span></span><br /><br /> <span data-ttu-id="5093b-144">-   [Windows ストア アプリおよび Windows ランタイムのための .NET Framework サポート](support-for-windows-store-apps-and-windows-runtime.md)</span><span class="sxs-lookup"><span data-stu-id="5093b-144">-   [.NET Framework Support for Windows Store Apps and Windows Runtime](support-for-windows-store-apps-and-windows-runtime.md)</span></span> <br /><span data-ttu-id="5093b-145">-   [Windows ランタイムへの URI の引き渡し](passing-a-uri-to-the-windows-runtime.md)</span><span class="sxs-lookup"><span data-stu-id="5093b-145">-   [Passing a URI to the Windows Runtime](passing-a-uri-to-the-windows-runtime.md)</span></span> <br />-   <xref:System.IO.WindowsRuntimeStreamExtensions><br />-    <xref:System.WindowsRuntimeSystemExtensions>|
|<span data-ttu-id="5093b-146">Microsoft 以外のプラットフォームに対応した .NET Framework アプリの開発</span><span class="sxs-lookup"><span data-stu-id="5093b-146">Build .NET Framework apps for non-Microsoft platforms</span></span>|<span data-ttu-id="5093b-147">.NET Framework の **ポータブル クラス ライブラリの参照アセンブリ** と、Visual Studio 拡張機能またはサードパーティ ツール (Xamarin など)。</span><span class="sxs-lookup"><span data-stu-id="5093b-147">**Portable Class Library reference assemblies** in the .NET Framework, and a Visual Studio extension or third-party tool such as Xamarin.</span></span><br /><br /> <span data-ttu-id="5093b-148">詳細については、次の情報を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5093b-148">For details, see:</span></span><br /><br /> <span data-ttu-id="5093b-149">-   [すべてのプラットフォームでポータブル クラス ライブラリが利用可能に](https://devblogs.microsoft.com/dotnet/portable-class-library-pcl-now-available-on-all-platforms/)</span><span class="sxs-lookup"><span data-stu-id="5093b-149">-   [Portable Class Library now available on all platforms.](https://devblogs.microsoft.com/dotnet/portable-class-library-pcl-now-available-on-all-platforms/)</span></span> <span data-ttu-id="5093b-150">(ブログの投稿)</span><span class="sxs-lookup"><span data-stu-id="5093b-150">(blog post)</span></span><br /><span data-ttu-id="5093b-151">-   [Xamarin ドキュメント](/xamarin)</span><span class="sxs-lookup"><span data-stu-id="5093b-151">-   [Xamarin documentation](/xamarin)</span></span>|
|<span data-ttu-id="5093b-152">JavaScript および HTML を使用したクロスプラットフォーム開発</span><span class="sxs-lookup"><span data-stu-id="5093b-152">Use JavaScript and HTML for cross-platform development</span></span>|<span data-ttu-id="5093b-153">Windows 8.1 と Windows Phone 8.1 の Windows ランタイム API に対する開発を行うための、Visual Studio 2013 更新プログラム 2 の **ユニバーサル アプリ テンプレート** 。</span><span class="sxs-lookup"><span data-stu-id="5093b-153">**Universal App templates** in Visual Studio 2013, Update 2 to develop against Windows Runtime APIs for Windows 8.1 and Windows Phone 8.1.</span></span> <span data-ttu-id="5093b-154">現在、クロスプラットフォーム アプリを開発するときに .NET Framework API で JavaScript と HTML を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="5093b-154">Currently, you can't use JavaScript and HTML with .NET Framework APIs to develop cross-platform apps.</span></span><br /><br /> <span data-ttu-id="5093b-155">詳細については、次の情報を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5093b-155">For details, see:</span></span><br /><br /> <span data-ttu-id="5093b-156">-   [JavaScript プロジェクト テンプレート](/previous-versions/windows/apps/hh758331(v=win.10))</span><span class="sxs-lookup"><span data-stu-id="5093b-156">-   [JavaScript Project Templates](/previous-versions/windows/apps/hh758331(v=win.10))</span></span><br /><span data-ttu-id="5093b-157">-   [JavaScript を使用した Windows ランタイム アプリの Windows Phone への移植](/previous-versions/windows/apps/dn636144(v=win.10))</span><span class="sxs-lookup"><span data-stu-id="5093b-157">-   [Porting a Windows Runtime app using JavaScript to Windows Phone](/previous-versions/windows/apps/dn636144(v=win.10))</span></span>|