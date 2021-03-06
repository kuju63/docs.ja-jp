---
title: null セマンティクス
ms.date: 03/30/2017
ms.assetid: a97017ae-d634-4cf3-bbaf-054a528fd683
ms.openlocfilehash: 739ee95be45d7d64a4ad1678837b9706a533f07d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91147542"
---
# <a name="null-semantics"></a>null セマンティクス

次の表では、[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] のドキュメントで `null` (Visual Basic では `Nothing`) に関する問題について説明されている各部分へのリンクを示します。  
  
|トピック|説明|  
|-----------|-----------------|  
|[SQL と CLR の型の不一致](sql-clr-type-mismatches.md)|このトピックの「null セマンティクス」セクションでは、3 つの状態を持つ SQL のブール値と、2 つの状態を持つ共通言語ランタイム (CLR) の <xref:System.Boolean>、リテラルの `Nothing` (Visual Basic) と `null` (C#)、および関連するその他の話題について説明されています。|  
|[標準クエリ演算子の変換](standard-query-operator-translation.md)|このトピックの「null セマンティクス」セクションでは、 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]での null の比較のセマンティクスについて説明します。|  
|[System.String メソッド](system-string-methods.md)|このトピックの「.NET との相違」セクションでは、 <xref:System.String.LastIndexOf%2A> の戻り値が 0 の場合に、文字列が null の場合と、見つかった位置が 0 の場合の両方があることについて説明します。|  
|[数値のシーケンスの合計の計算](compute-the-sum-of-values-in-a-numeric-sequence.md)|null のみを含むシーケンスまたは空のシーケンスの場合に、<xref:System.Linq.Enumerable.Sum%2A> 演算子が 0 ではなく `null` (Visual Basic では `Nothing`) に評価されることについて説明されています。|  
  
## <a name="see-also"></a>関連項目

- [データ型と関数](data-types-and-functions.md)
