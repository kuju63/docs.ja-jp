---
ms.openlocfilehash: 1ddc2cea19872b44ff9659bcebd76117587ea89a
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "92159491"
---
### <a name="targetframework-change-from-netcoreapp-to-net"></a>TargetFramework が netcoreapp から net に変更される

MSBuild `TargetFramework` プロパティの値が `netcoreapp3.1` から `net5.0` に変更されました。 それにより、`TargetFramework` の値の解析に依存するコードが破損するおそれがあります。

#### <a name="version-introduced"></a>導入されたバージョン

5.0

#### <a name="change-description"></a>変更の説明

.NET Core 1.0 から 3.1 では、MSBuild `TargetFramework` の値は `netcoreapp` で始まります。たとえば、.NET Core 3.1 を対象とするアプリの場合、`netcoreapp3.1` になります。 .NET 5.0 以降、この値が簡略化され、`net` で始まります。たとえば、.NET 5.0 の場合、`net5.0` になります。

詳細については、「[The future of .NET Standard](https://devblogs.microsoft.com/dotnet/the-future-of-net-standard/)」 (.NET Standard の未来) と「[Target framework names in .NET 5](https://github.com/dotnet/designs/blob/main/accepted/2020/net5/net5.md)」 (.NET 5 のターゲット フレームワーク名) を参照してください。

#### <a name="reason-for-change"></a>変更理由

- `TargetFramework` 値を簡略化します。
- `TargetFramework` プロパティに `TargetPlatform` を含めることをプロジェクトで可能にします。

#### <a name="recommended-action"></a>推奨される操作

`TargetFramework` の値を解析するロジックがある場合、それを更新する必要があります。 たとえば、次の MSBuild 条件は `TargetFramework` の値に依存します。

```xml
<PropertyGroup Condition="$(TargetFramework.StartsWith('netcoreapp'))">
```

この要件の場合、代わりにターゲット フレームワークの識別子を比較するようにコードを更新できます。

```xml
<PropertyGroup Condition="'$([MSBuild]::GetTargetFrameworkIdentifier('$(TargetFramework)'))' == '.NETCoreApp'">
```

#### <a name="category"></a>カテゴリ

MSBuild

#### <a name="affected-apis"></a>影響を受ける API

N/A

<!--

#### Affected APIs

Not detectable via API analysis.

-->
