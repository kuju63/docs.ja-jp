---
title: x:Uid ディレクティブ
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], localizable content attribute
- XAML [XAML Services], x:Uid attribute
- x:Uid attribute [XAML Services]
- Uid attribute [XAML Services]
ms.assetid: 81defade-483b-4a89-b76d-9b25bba34010
ms.openlocfilehash: b5b480016d2183268422dea861510c6a169ac27b
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432618"
---
# <a name="xuid-directive"></a><span data-ttu-id="c2d5d-102">x:Uid ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="c2d5d-102">x:Uid Directive</span></span>

<span data-ttu-id="c2d5d-103">マークアップ要素の一意の識別子を提供します。</span><span class="sxs-lookup"><span data-stu-id="c2d5d-103">Provides a unique identifier for markup elements.</span></span> <span data-ttu-id="c2d5d-104">多くのシナリオでは、この一意の識別子は、XAML のローカリゼーション プロセスとツールで使用されます。</span><span class="sxs-lookup"><span data-stu-id="c2d5d-104">In many scenarios, this unique identifier is used by XAML localization processes and tools.</span></span>

## <a name="xaml-attribute-usage"></a><span data-ttu-id="c2d5d-105">XAML 属性の使用方法</span><span class="sxs-lookup"><span data-stu-id="c2d5d-105">XAML Attribute Usage</span></span>

```xaml
<object x:Uid="identifier"... />
```

## <a name="xaml-values"></a><span data-ttu-id="c2d5d-106">XAML 値</span><span class="sxs-lookup"><span data-stu-id="c2d5d-106">XAML Values</span></span>

|||
|-|-|
|`identifier`|<span data-ttu-id="c2d5d-107">手動で作成された文字列、またはコンシューマーによって解釈されるときにファイル内で一意である必要がある自動生成`x:Uid`された文字列。</span><span class="sxs-lookup"><span data-stu-id="c2d5d-107">A manually created or autogenerated string that should be unique in a file when it is interpreted by an `x:Uid` consumer.</span></span>|

## <a name="remarks"></a><span data-ttu-id="c2d5d-108">解説</span><span class="sxs-lookup"><span data-stu-id="c2d5d-108">Remarks</span></span>

<span data-ttu-id="c2d5d-109">[MS-XAML]では、`x:Uid`ディレクティブとして定義されます。</span><span class="sxs-lookup"><span data-stu-id="c2d5d-109">In [MS-XAML], `x:Uid` is defined as a directive.</span></span> <span data-ttu-id="c2d5d-110">詳細については、「 [ \[MS-XAML\]セクション 5.3.6](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c2d5d-110">For more information, see [\[MS-XAML\] Section 5.3.6](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span></span>

<span data-ttu-id="c2d5d-111">`x:Uid`は、記載`x:Name`されている XAML ローカリゼーション シナリオと、ローカライズに使用される識別子が のプログラミング モデルへの依存性を持たないため`x:Name`、両方から離散的です。</span><span class="sxs-lookup"><span data-stu-id="c2d5d-111">`x:Uid` is discrete from `x:Name` both because of the stated XAML localization scenario and so that identifiers that are used for localization have no dependencies on the programming model implications of `x:Name`.</span></span> <span data-ttu-id="c2d5d-112">また、XAML`x:Name`名前スコープによって制御されます。ただし、`x:Uid`一意性の適用に関する XAML 言語定義の概念によって制御されるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="c2d5d-112">Also, `x:Name` is governed by the XAML namescope; however, `x:Uid` is not governed by any XAML language defined concept of uniqueness enforcement.</span></span> <span data-ttu-id="c2d5d-113">広い意味での XAML プロセッサ (ローカリゼーション プロセスの一部ではないプロセッサ) は、値`x:Uid`の一意性を強制することは期待されていません。</span><span class="sxs-lookup"><span data-stu-id="c2d5d-113">XAML processors in a broad sense (processors that are not part of the localization process) are not expected to enforce uniqueness of `x:Uid` values.</span></span> <span data-ttu-id="c2d5d-114">その責任は概念的に値の創始者にあります。</span><span class="sxs-lookup"><span data-stu-id="c2d5d-114">That responsibility is conceptually on the originator of the values.</span></span> <span data-ttu-id="c2d5d-115">単一の XAML`x:Uid`ソース内の値の一意性の期待は、専用のグローバリゼーション プロセスやツールなどの値のコンシューマーにとって妥当です。</span><span class="sxs-lookup"><span data-stu-id="c2d5d-115">The expectation of uniqueness of `x:Uid` values within a single XAML source is reasonable for consumers of the values, such as dedicated globalization processes or tools.</span></span> <span data-ttu-id="c2d5d-116">一般的な一意性モデル`x:Uid`は、XAML を表す XML エンコード ファイル内で値が一意であるというものです。</span><span class="sxs-lookup"><span data-stu-id="c2d5d-116">The typical uniqueness model is that `x:Uid` values are unique within an XML-encoded file that represents XAML.</span></span>

<span data-ttu-id="c2d5d-117">特定の XAML スキーマに関する重要な知識を持`x:Uid`つツールは、マークアップでテキスト文字列値が検出されるすべての場合ではなく、真のローカライズ可能な文字列にのみ適用するように選択できます。</span><span class="sxs-lookup"><span data-stu-id="c2d5d-117">Tools that have significant knowledge of a particular XAML schema can choose to apply `x:Uid` only for true localizable strings, instead of for all cases where a text string value is encountered in markup.</span></span>

<span data-ttu-id="c2d5d-118">フレームワークは、定義する型に属性`x:Uid`<xref:System.Windows.Markup.UidPropertyAttribute>を適用することで、オブジェクト モデル内の特定のプロパティをエイリアスとして指定できます。</span><span class="sxs-lookup"><span data-stu-id="c2d5d-118">Frameworks can specify a particular property in their object model to be an alias for `x:Uid` by applying the attribute <xref:System.Windows.Markup.UidPropertyAttribute> to the defining type.</span></span> <span data-ttu-id="c2d5d-119">フレームワークが特定のプロパティを指定する場合、同じオブジェクトに対`x:Uid`してエイリアス化されたメンバーの両方を指定することは無効です。</span><span class="sxs-lookup"><span data-stu-id="c2d5d-119">If a framework specifies a particular property, it is not valid to specify both `x:Uid` and the aliased member on the same object.</span></span> <span data-ttu-id="c2d5d-120">エイリアスを`x:Uid`付けたメンバーの両方を指定すると、.NET XAML サービス<xref:System.Xaml.XamlDuplicateMemberException>API は通常、このケースをスローします。</span><span class="sxs-lookup"><span data-stu-id="c2d5d-120">If both `x:Uid` and the aliased member are specified, .NET XAML Services API typically throws <xref:System.Xaml.XamlDuplicateMemberException> for this case.</span></span>

## <a name="wpf-usage-notes"></a><span data-ttu-id="c2d5d-121">WPF の使用上の注意</span><span class="sxs-lookup"><span data-stu-id="c2d5d-121">WPF Usage Notes</span></span>

<span data-ttu-id="c2d5d-122">WPF ローカリゼーション`x:Uid`プロセスおよび BAML 形式の XAML での役割の詳細については[、「WPF のグローバリゼーション」または「WPF のグローバリゼーション](../../framework/wpf/advanced/globalization-for-wpf.md)」を参照してください。<xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A></span><span class="sxs-lookup"><span data-stu-id="c2d5d-122">For more information about the role of `x:Uid` in the WPF localization process and in the BAML form of XAML, see [Globalization for WPF](../../framework/wpf/advanced/globalization-for-wpf.md) or <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A></span></span>

## <a name="see-also"></a><span data-ttu-id="c2d5d-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="c2d5d-123">See also</span></span>

- <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A>
- <xref:Microsoft.Build.Tasks.Windows.UidManager>
- [<span data-ttu-id="c2d5d-124">WPF のグローバリゼーション</span><span class="sxs-lookup"><span data-stu-id="c2d5d-124">Globalization for WPF</span></span>](../../framework/wpf/advanced/globalization-for-wpf.md)