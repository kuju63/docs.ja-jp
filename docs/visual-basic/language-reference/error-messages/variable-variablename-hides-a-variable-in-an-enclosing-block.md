---
title: 変数 '<variablename>' は、囲まれたブロック内の変数を非表示にします。
ms.date: 07/20/2015
f1_keywords:
- vbc30616
- bc30616
helpviewer_keywords:
- BC30616
ms.assetid: e7658ebc-da45-451b-a409-a0f8915f0beb
ms.openlocfilehash: 408acaafd5e266266b5191313611b94b72a5c270
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "92161349"
---
# <a name="bc30616-variable-variablename-hides-a-variable-in-an-enclosing-block"></a>BC30616:変数 '\<variablename>' は、囲まれたブロック内の変数を非表示にします。

ブロックで囲まれた変数の名前が、別のローカル変数と同じ名前です。

 **エラー ID:** BC30616

## <a name="to-correct-this-error"></a>このエラーを解決するには

- 囲まれたブロック内の変数の名前を、他のローカル変数と同じにならないように変更します。 次に例を示します。

    ```vb
    Dim a, b, x As Integer
    If a = b Then
       Dim y As Integer = 20 ' Uniquely named block variable.
    End If
    ```

- このエラーの一般的な原因は、イベント ハンドラー内で `Catch e As Exception` を使用することです。 この場合は、`e` ではなく、`Catch` ブロック変数に `ex` という名前を付けます。

- このエラーのもう 1 つの一般的な原因は、別の `Catch` ブロック内の `Try` ブロック内で宣言されたローカル変数へのアクセスを試みることです。 これを修正するには、`Try...Catch...Finally` 構造体の外側で変数を宣言します。

## <a name="see-also"></a>関連項目

- [Try...Catch...Finally ステートメント](../statements/try-catch-finally-statement.md)
- [変数宣言](../../programming-guide/language-features/variables/variable-declaration.md)
