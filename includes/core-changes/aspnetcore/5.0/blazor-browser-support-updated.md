---
ms.openlocfilehash: 584014572ab799e1e3ab2f02c9fbf4fe6b0c17e7
ms.sourcegitcommit: 636af37170ae75a11c4f7d1ecd770820e7dfe7bd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/07/2020
ms.locfileid: "91804928"
---
### <a name="blazor-updated-browser-support"></a>Blazor: ブラウザー サポートの更新

ASP.NET Core 5.0 には、[新しい Blazor 機能](https://github.com/dotnet/aspnetcore/issues/21514)が導入されていますが、その一部は古いブラウザーと互換性がありません。 ASP.NET Core 5.0 の Blazor でサポートされているブラウザーのリストが、それに従って更新されています。

ディスカッションについては、GitHub イシュー [dotnet/aspnetcore#26475](https://github.com/dotnet/aspnetcore/issues/26475) を参照してください。

#### <a name="version-introduced"></a>導入されたバージョン

5.0

#### <a name="old-behavior"></a>以前の動作

Blazor Server は、十分なポリフィルを備えた Microsoft Internet Explorer 11 をサポートしています。 Blazor Server と Blazor WebAssembly は、[Microsoft Edge レガシ](https://support.microsoft.com/help/4533505/what-is-microsoft-edge-legacy)でも機能します。

#### <a name="new-behavior"></a>新しい動作

ASP.NET Core 5.0 の Blazor Server は、Microsoft Internet Explorer 11 ではサポートされていません。 Blazor Server と Blazor WebAssembly は、Microsoft Edge レガシでは完全には機能しません。

#### <a name="reason-for-change"></a>変更理由

ASP.NET Core 5.0 の新しい Blazor 機能は、これらの古いブラウザーと互換性がなく、これらの古いブラウザーの使用は減少しています。 詳細については、次のリソースを参照してください。

* [Microsoft Edge レガシの Windows サポートも、2021 年 3 月 9 日に終了します](https://support.microsoft.com/help/4533505/what-is-microsoft-edge-legacy)
* [Microsoft 365 のアプリとサービスでの Microsoft Internet Explorer 11 のサポートは、2021 年 8 月 17 日までに終了します](/lifecycle/announcements/m365-ie11-microsoft-edge-legacy)

#### <a name="recommended-action"></a>推奨される操作

これらの古いブラウザーから[新しい Chromium ベースの Microsoft Edge](https://www.microsoft.com/edge) にアップグレードしてください。 これらの古いブラウザーをサポートする必要がある Blazor アプリの場合は、ASP.NET Core 3.1 を使用してください。 ASP.NET Core 3.1 の Blazor でサポートされているブラウザーのリストは変更されておらず、[サポートされているプラットフォーム](/aspnet/core/blazor/supported-platforms?view=aspnetcore-3.1)に記載されています。

#### <a name="category"></a>カテゴリ

ASP.NET Core

#### <a name="affected-apis"></a>影響を受ける API

なし

<!--

#### Affected APIs

Not detectable via API analysis

-->
