---
title: '方法 : イベントベースの非同期パターンのクライアントを実装する'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Event-based Asynchronous Pattern
- ProgressChangedEventArgs class
- BackgroundWorker component
- events [.NET], asynchronous
- Asynchronous Pattern
- AsyncOperationManager class
- threading [.NET], asynchronous features
- components [.NET], asynchronous
- AsyncOperation class
- threading [Windows Forms], asynchronous features
- AsyncCompletedEventArgs class
ms.assetid: 21a858c1-3c99-4904-86ee-0d17b49804fa
ms.openlocfilehash: 95997f219a08c131905cfc86b78e94c36f3ec851
ms.sourcegitcommit: 4a938327bad8b2e20cabd0f46a9dc50882596f13
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/28/2020
ms.locfileid: "92888816"
---
# <a name="how-to-implement-a-client-of-the-event-based-asynchronous-pattern"></a>方法 : イベントベースの非同期パターンのクライアントを実装する
次のコード例では、[イベント ベースの非同期パターンの概要](event-based-asynchronous-pattern-overview.md)ページに記載されている方法でコンポーネントを使用しています。 この例のフォームでは、「[方法 : イベントベースの非同期パターンをサポートするコンポーネントを実装する](component-that-supports-the-event-based-asynchronous-pattern.md)」に説明がある `PrimeNumberCalculator` コンポーネントが使用されています。  
  
 この例を使用するプロジェクトを実行すると、"Prime Number Calculator" とグリッドと共に、 **[Start New Task]\(新しいタスクの開始\)** と **[キャンセル]** という 2 つのボタンが表示されます。 **[Start New Task]\(新しいタスクの開始\)** ボタンは数回連続でクリックできます。クリックのたびに、非同期操作は計算を開始し、無作為に生成されたテスト用の数字が素数かどうかを判断します。 フォームには進捗と増分が定期的に表示されます。 各操作には一意のタスク ID が割り当てられます。 計算結果は **[結果]** 列に表示されます。テスト用の数字が素数ではない場合、 **Composite** というラベルが付き、その最初の除数が表示されます。  
  
 保留中の操作は **[キャンセル]** ボタンでキャンセルできます。 複数選択が可能です。  
  
> [!NOTE]
> ほとんどの数値は素数になりません。 操作を数回完了しても素数が出てこない場合、さらに多くのタスクを開始してください。いずれは素数が見つかります。  
  
## <a name="example"></a>例  
 [!code-csharp[System.ComponentModel.AsyncOperationManager#10](snippets/component-that-supports-the-event-based-asynchronous-pattern/csharp/primenumbercalculatormain.cs#10)]
 [!code-vb[System.ComponentModel.AsyncOperationManager#10](snippets/component-that-supports-the-event-based-asynchronous-pattern/vb/primenumbercalculatormain.vb#10)]  
  
## <a name="see-also"></a>参照

- <xref:System.ComponentModel.AsyncOperation>
- <xref:System.ComponentModel.AsyncOperationManager>
- <xref:System.Windows.Forms.WindowsFormsSynchronizationContext>
