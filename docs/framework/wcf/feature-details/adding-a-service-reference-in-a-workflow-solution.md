---
title: ワークフロー ソリューションでのサービス参照の追加
ms.date: 03/30/2017
ms.assetid: 83574cf3-9803-49bc-837f-432936dc9c76
ms.openlocfilehash: 1b4cc16d3bd85c28ac7267e88ae0a714620c9861
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90557059"
---
# <a name="add-a-service-reference-in-a-workflow-solution"></a>ワークフローソリューションでのサービス参照の追加

ワークフロー アプリケーションでのサービス参照の追加は、通常の WCF アプリケーションとは動作が少し異なります。 [サービス参照の**追加**] を選択し、サービスの URL を指定すると、  >  **Service Reference**メタデータがダウンロードされ、カスタムアクティビティが生成されます。これにより、wcf サービスまたは wcf ワークフローサービスを呼び出すことができます。 サービス参照を追加した後、生成されたアクティビティがビルドされるように、ソリューションを再ビルドします。 これにより、アクティビティがワークフロー デザイナー ツールボックスに表示されます。 これは、ワークフローソリューション内にサービス参照を追加する場合にのみ機能します。 次の web キャストは、他の種類のプロジェクトにサービス参照を追加する方法を示しています。 [Web プロジェクトのワークフローから WCF サービスを呼び出し](/archive/blogs/endpoint/how-to-consume-a-wcf-service-from-a-wf4-workflow)ます。

同じ操作名が含まれるサービスへのサービス参照を複数追加すると、問題が発生します。 生成されたアクティビティは最初のサービス操作しか呼び出しません。 この問題を回避するには、サービス操作の名前を変更するか、生成された各アクティビティ内のエンドポイント構成名を変更します。

## <a name="see-also"></a>関連項目

- [ワークフロー サービス](workflow-services.md)
- [Web プロジェクトでのワークフローからの WCF サービスの呼び出し](/archive/blogs/endpoint/how-to-consume-a-wcf-service-from-a-wf4-workflow)
