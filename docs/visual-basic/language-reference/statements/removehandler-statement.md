---
title: RemoveHandler ステートメント
ms.date: 07/20/2015
f1_keywords:
- vb.RemoveHandlerMethod
- vb.RemoveHandler
- RemoveHandler
helpviewer_keywords:
- RemoveHandler keyword [Visual Basic]
- RemoveHandler statement [Visual Basic]
ms.assetid: 647cd825-e877-4910-b4f1-8d168beebe6a
ms.openlocfilehash: a815241f20be12b3b7b4f2b87d50a8965021bbf0
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "90871931"
---
# <a name="removehandler-statement"></a>RemoveHandler ステートメント

イベントとイベント ハンドラー間の関連付けを削除します。  
  
## <a name="syntax"></a>構文  
  
```vb  
RemoveHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a>指定項目  
  
|用語|定義|  
|---|---|  
|`event`|処理されるイベントの名前。|  
|`eventhandler`|イベントを現在処理しているプロシージャの名前。|  
  
## <a name="remarks"></a>Remarks  

 `AddHandler` および `RemoveHandler` ステートメントを使用すると、プログラムの実行中に、特定のイベントのイベント処理をいつでも開始および停止できます。  
  
> [!NOTE]
> カスタム イベントの場合は、`RemoveHandler` ステートメントによってイベントの `RemoveHandler` アクセサーが呼び出されます。 カスタム イベントの詳細については、「[Event ステートメント](event-statement.md)」を参照してください。  
  
## <a name="example"></a>例  

 [!code-vb[VbVbalrEvents#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#17)]  
  
## <a name="see-also"></a>関連項目

- [AddHandler ステートメント](addhandler-statement.md)
- [Handles](handles-clause.md)
- [Event ステートメント](event-statement.md)
- [イベント](../../programming-guide/language-features/events/index.md)
