---
title: プロパティとインデクサーの比較 - C# プログラミング ガイド
description: C# のインデクサーとプロパティの類似点を比較します。 一部の違いを除いて、プロパティのアクセサーに対して定義されている規則は、インデクサーのアクセサーに適用されます。
ms.date: 07/20/2015
helpviewer_keywords:
- properties [C#], vs. indexers
- indexers [C#], vs. properties
ms.assetid: 3358a89f-44a0-4a4d-bf8c-07237a90af39
ms.openlocfilehash: fff20ca965e7614d26f7da32321a829d13292389
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91192530"
---
# <a name="comparison-between-properties-and-indexers-c-programming-guide"></a>プロパティとインデクサーの比較 (C# プログラミング ガイド)

インデクサーはプロパティと似ています。 次の表で示す相違点を除けば、プロパティのアクセサーに対して定義されているすべての規則が、インデクサーのアクセサーにも適用されます。  
  
|プロパティ|インデクサー|  
|--------------|-------------|  
|パブリック データ メンバーのように、メソッドを呼び出せるようにします。|オブジェクト自体で配列表記を使用して、オブジェクトの内部コレクションの要素にアクセスできるようにします。|  
|シンプルな名前でアクセスされます。|インデックスでアクセスされます。|  
|静的メンバーまたはインスタンス メンバーとして使用できます。|インスタンス メンバーである必要があります。|  
|プロパティの [get](../../language-reference/keywords/get.md) アクセサーにはパラメーターがありません。|インデクサーの `get` アクセサーには、インデクサーと同じ仮パラメーター リストがあります。|  
|プロパティの [set](../../language-reference/keywords/set.md) アクセサーには、暗黙の `value` パラメーターがあります。|インデクサーの `set` アクセサーには、インデクサーと同じ仮パラメーター リストのほか、[value](../../language-reference/keywords/value.md) パラメーターがあります。|  
|[自動実装プロパティ](../classes-and-structs/auto-implemented-properties.md)を持つ簡略化された構文がサポートされます。|インデクサーのみを取得するための式形式メンバーがサポートされます。|  
  
## <a name="see-also"></a>関連項目

- [C# プログラミング ガイド](../index.md)
- [インデクサー](./index.md)
- [プロパティ](../classes-and-structs/properties.md)
