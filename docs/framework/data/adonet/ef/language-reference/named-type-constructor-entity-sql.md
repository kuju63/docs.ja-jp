---
title: 名前付きの型コンストラクター (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 549dea04-d93d-4c87-a292-f81b1598dbfd
ms.openlocfilehash: c673b58ee5811e3d3b74b3744d3f5291888e2253
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91197782"
---
# <a name="named-type-constructor-entity-sql"></a>名前付きの型コンストラクター (Entity SQL)

エンティティ型や複合型など、概念モデル標準型のインスタンスの作成に使用します。  
  
## <a name="syntax"></a>構文  
  
```sql  
[{identifier. }] identifier( [expression [{, expression }]] )  
```  
  
## <a name="arguments"></a>引数  

 `identifier`  
 単純な識別子および引用符で囲まれた識別子の値。 詳しくは、「[識別子](identifiers-entity-sql.md)」をご覧ください。  
  
 `expression`  
 型の宣言に表示される順序と同じ順序であると見なされる型の属性。  
  
## <a name="return-value"></a>戻り値  

 名前付きの複合型とエンティティ型のインスタンス。  
  
## <a name="remarks"></a>Remarks  

 次の例は、標準型と複合型を作成する方法を示しています。  
  
 次の式は、 `Person` 型のインスタンスを作成する式です。  
  
 `Person("abc", 12)`  
  
 次の式は、複合型のインスタンスを作成する式です。  
  
 `MyModel.ZipCode(‘98118’, ‘4567’)`  
  
 次の式は、入れ子になった複合型のインスタンスを作成する式です。  
  
 `MyModel.AddressInfo('My street address', 'Seattle', 'WA', MyModel.ZipCode('98118', '4567'))`  
  
 次の式は、入れ子になった複合型を持つエンティティのインスタンスを作成する式です。  
  
 `MyModel.Person("Bill", MyModel.AddressInfo('My street address', 'Seattle', 'WA', MyModel.ZipCode('98118', '4567')))`  
  
 次の例は、複合型のプロパティを null に初期化する方法を示しています。`MyModel.ZipCode(‘98118’, null)`  
  
## <a name="example"></a>例  

 次の Entity SQL クエリでは、名前付きの型コンストラクターを使用して、概念モデル型のインスタンスを作成します。 このクエリは、AdventureWorks Sales Model に基づいています。 このクエリをコンパイルして実行するには、次の手順を実行します。  
  
1. 「[方法: StructuralType 結果を返すクエリを実行する](../how-to-execute-a-query-that-returns-structuraltype-results.md)」の手順に従います。  
  
2. 次のクエリを引数として `ExecuteStructuralTypeQuery` メソッドに渡します。  
  
 [!code-sql[DP EntityServices Concepts#NAMED_TYPE_CONSTRUCTOR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#named_type_constructor)]  
  
## <a name="see-also"></a>関連項目

- [コンストラクター](constructing-types-entity-sql.md)
- [Entity SQL リファレンス](entity-sql-reference.md)
