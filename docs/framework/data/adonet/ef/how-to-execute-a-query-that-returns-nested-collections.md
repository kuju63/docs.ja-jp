---
title: '方法: 入れ子になったコレクションを返すクエリを実行する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f7f385f3-ffcf-4f3b-af35-de8818938e5f
ms.openlocfilehash: 3bf6e08e7842fbf235b519680b81f79fba4a7228
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91198406"
---
# <a name="how-to-execute-a-query-that-returns-nested-collections"></a>方法: 入れ子になったコレクションを返すクエリを実行する

ここでは、<xref:System.Data.EntityClient.EntityCommand> オブジェクトを使用して概念モデルに対してコマンドを実行する方法、および <xref:System.Data.EntityClient.EntityDataReader> を使用して入れ子になったコレクションの結果を取得する方法について説明します。  
  
### <a name="to-run-the-code-in-this-example"></a>この例のコードを実行するには  
  
1. [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) をプロジェクトに追加し、Entity Framework が使用されるようにプロジェクトを構成します。 詳細については、[Entity Data Model ウィザードを使用する](/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100))」を参照してください。  
  
2. アプリケーションのコード ページで、次の `using` ステートメント (Visual Basic の場合は `Imports`) を追加します。  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
## <a name="example"></a>例  

 "*入れ子になったコレクション*" とは、別のコレクションに含まれているコレクションのことです。 次に示すコードでは、`Contacts` のコレクションと、それぞれの `SalesOrderHeaders` に関連付けられている、`Contact` の入れ子になったコレクションを取得します。  
  
 [!code-csharp[DP EntityServices Concepts#ReturnNestedCollectionWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#returnnestedcollectionwithentitycommand)]
 [!code-vb[DP EntityServices Concepts#ReturnNestedCollectionWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#returnnestedcollectionwithentitycommand)]  
  
## <a name="see-also"></a>関連項目

- [Entity Framework 用の EntityClient プロバイダー](entityclient-provider-for-the-entity-framework.md)
