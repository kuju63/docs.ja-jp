---
title: CStr 関数の戻り値
ms.date: 07/20/2015
helpviewer_keywords:
- times [Visual Basic], CStr Function return values
- type conversion [Visual Basic]
- dates [Visual Basic], CStr Function return values
- CStr function
- strings [Visual Basic], return value
- Date data type [Visual Basic], converting
- dates [Visual Basic]
- String data type [Visual Basic], converting
ms.assetid: 3aa744e7-1419-45d5-85e3-e5abc2953673
ms.openlocfilehash: cc5e5cc437175e9aebfba559488ca74283faa9ad
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "90870156"
---
# <a name="return-values-for-the-cstr-function-visual-basic"></a>CStr 関数の戻り値 (Visual Basic)

次の表に、`expression` のさまざまなデータ型に対する `CStr` の戻り値を示します。  
  
|`expression` 型が次の場合|`CStr` 戻り値|  
|-----------------------------|--------------------|  
|[Boolean データ型](../data-types/boolean-data-type.md)|"True" または "False" を格納する文字列。|  
|[Date データ型](../data-types/date-data-type.md)|システムの短い日付形式の `Date` 値 (日付と時刻) を格納する文字列。|  
|[数値のデータ型](../../programming-guide/language-features/data-types/numeric-data-types.md)|数を表す文字列。|  
  
## <a name="cstr-and-date"></a>CStr と Date  

 `Date` 型には、常に日付と時刻の両方の情報が格納されます。 型変換の目的で、Visual Basic では、1/1/0001 (1 年の 1 月 1 日) を日付の*ニュートラル値*と見なし、00:00:00 (午前 0 時) を時刻のニュートラル値と見なします。 `CStr` では、結果の文字列にニュートラル値が含まれません。 たとえば、`#January 1, 0001 9:30:00#` を文字列に変換した場合、結果は "9:30:00 AM" になります。日付情報は含まれません。 ただし、日付情報は元の `Date` 値には引き続き存在しているため、<xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A> などの関数を使用して回復できます。  
  
> [!NOTE]
> `CStr` 関数では、アプリケーションの現在のカルチャ設定に基づいてその変換が実行されます。 特定のカルチャの数値の文字列表現を取得するには、数値の `ToString(IFormatProvider)` メソッドを使用します。 たとえば、型 `Double` の値を `String` に変換する場合は、<xref:System.Double.ToString%2A?displayProperty=nameWithType> を使用します。  
  
## <a name="see-also"></a>関連項目

- <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A>
- [データ型変換関数](type-conversion-functions.md)
- [Boolean データ型](../data-types/boolean-data-type.md)
- [Date データ型](../data-types/date-data-type.md)
