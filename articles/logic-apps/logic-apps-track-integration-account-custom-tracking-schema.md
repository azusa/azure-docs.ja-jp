---
title: B2B 監視のカスタム追跡スキーマ - Azure Logic Apps | Microsoft Docs
description: カスタム追跡スキーマを作成して、Azure 統合アカウントのトランザクションからの B2B メッセージを監視します。
author: padmavc
manager: anneta
editor: ''
services: logic-apps
documentationcenter: ''
ms.assetid: 433ae852-a833-44d3-a3c3-14cca33403a2
ms.service: logic-apps
ms.workload: integration
ms.tgt_pltfrm: na
ms.devlang: na
ms.topic: article
ms.date: 01/27/2017
ms.author: LADocs; padmavc
ms.custom: H1Hack27Feb2017
ms.openlocfilehash: 94de6afcf3f9f95a3cb45207ef43e1d33b728d99
ms.sourcegitcommit: 9cdd83256b82e664bd36991d78f87ea1e56827cd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2018
---
# <a name="enable-tracking-to-monitor-your-complete-workflow-end-to-end"></a>追跡を有効にしてワークフロー全体をエンド ツー エンドで監視する
企業間取引のワークフローにおけるさまざまな部分について、AS2 や X12 メッセージの追跡など、組み込みの追跡を有効にすることができます。 ロジック アプリ、BizTalk Server、SQL Server、またはその他のレイヤーを含むワークフローを作成する場合は、カスタムの追跡を有効にして、ワークフローの最初から最後までのイベントをログに記録することができます。 

このトピックでは、ロジック アプリの外部レイヤーで使用できるカスタム コードを示します。 

## <a name="custom-tracking-schema"></a>カスタム追跡スキーマ
````java

        {
            "sourceType": "",
            "source": {

            "workflow": {
                "systemId": ""
            },
            "runInstance": {
                "runId": ""
            },
            "operation": {
                "operationName": "",
                "repeatItemScopeName": "",
                "repeatItemIndex": "",
                "trackingId": "",
                "correlationId": "",
                "clientRequestId": ""
                }
            },
            "events": [
            {
                "eventLevel": "",
                "eventTime": "",
                "recordType": "",
                "record": {                
                }
            }
         ]
      }

````

| プロパティ | type | [説明] |
| --- | --- | --- |
| sourceType |   | 実行ソースのタイプ。 許可されている値は、**Microsoft.Logic/workflows** と **custom** です。 (必須) |
| ソース |   | ソースのタイプが **Microsoft.Logic/workflows** である場合は、このスキーマの後にソース情報を続ける必要があります。 ソースのタイプが **custom** の場合、スキーマは JToken です。 (必須) |
| systemId | String | ロジック アプリのシステム ID。 (必須) |
| runId | String | ロジック アプリの実行 ID。 (必須) |
| operationName | String | 操作の名前 (アクションやトリガーなど)。 (必須) |
| repeatItemScopeName | String | アクションが `foreach`/`until` ループ内にある場合の繰り返し項目名。 (必須) |
| repeatItemIndex | 整数 | アクションが `foreach`/`until` ループ内にあるかどうか。 繰り返される項目のインデックスを示します。 (必須) |
| trackingId | String | 追跡 ID (メッセージを関連付けるために使用します)。 (省略可能) |
| correlationId | String | 関連付け ID (メッセージを関連付けるために使用します)。 (省略可能) |
| clientRequestId | String | クライアントがメッセージを関連付けるために設定できます。 (省略可能) |
| eventLevel |   | イベントのレベル。 (必須) |
| eventTime |   | イベントの時刻 (YYYY-MM-DDTHH:MM:SS.00000Z という UTC 形式で示します)。 (必須) |
| recordType |   | 追跡レコードのタイプ。 許可されている値は **custom** です。 (必須) |
| record |   | カスタム レコード タイプ。 許可されている形式は、JToken です。 (必須) |

## <a name="b2b-protocol-tracking-schemas"></a>B2B プロトコル追跡スキーマ
B2B プロトコル追跡スキーマ について詳しくは、次のページをご覧ください。
* [AS2 の追跡スキーマ](../logic-apps/logic-apps-track-integration-account-as2-tracking-schemas.md)   
* [X12 の追跡スキーマ](logic-apps-track-integration-account-x12-tracking-schema.md)

## <a name="next-steps"></a>次の手順
* [B2B メッセージの監視方法](logic-apps-monitor-b2b-message.md)についての詳細情報。   
* [Log Analytics での B2B メッセージの追跡方法](../logic-apps/logic-apps-track-b2b-messages-omsportal.md)についての詳細情報。
* [Enterprise Integration Pack](../logic-apps/logic-apps-enterprise-integration-overview.md) についての詳細情報。
