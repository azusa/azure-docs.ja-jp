---
title: Azure SQL Database の仮想コアベースのリソース制限 | Microsoft Docs
description: このページでは、Azure SQL Database に対するいくつかの一般的な仮想コアベースのリソース制限について説明します。
services: sql-database
author: CarlRabeler
manager: craigg
ms.service: sql-database
ms.custom: DBs & servers
ms.topic: article
ms.date: 04/04/2018
ms.author: carlrab
ms.openlocfilehash: 23bab643a88fe27eb34750f970f962041f8c18f4
ms.sourcegitcommit: 6fcd9e220b9cd4cb2d4365de0299bf48fbb18c17
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/05/2018
---
# <a name="azure-sql-database-vcore-based-purchasing-model-limits-preview"></a>Azure SQL Database の仮想コアベースの購入モデルの制限 (プレビュー)

> [!IMPORTANT]
> DTU ベースの購入モデルの制限については、[SQL Database の DTU ベースのリソース制限](sql-database-dtu-resource-limits.md)に関する記事をご覧ください。

## <a name="single-database-storage-sizes-and-performance-levels"></a>単一データベース: ストレージ サイズとパフォーマンス レベル

次の表では、各サービス レベルおよびパフォーマンス レベルにおいて単一データベースで使用可能なリソースを示します。 [Azure Portal](sql-database-single-database-resources.md#manage-single-database-resources-using-the-azure-portal)、[Transact-SQL](sql-database-single-database-resources.md#manage-single-database-resources-using-transact-sql)、[PowerShell](sql-database-single-database-resources.md#manage-single-database-resources-using-powershell)、[Azure CLI](sql-database-single-database-resources.md#manage-single-database-resources-using-the-azure-cli)、または [REST API](sql-database-single-database-resources.md#manage-single-database-resources-using-the-rest-api) を使って、単一のデータベースにサービス レベル、パフォーマンス レベル、ストレージ量を設定できます。

### <a name="general-purpose-service-tier"></a>汎用のサービス階層
|パフォーマンス レベル|GP_Gen4_1|GP_Gen4_2|GP_Gen4_4|GP_Gen4_8|GP_Gen4_16|
|:--- | --: |--: |--: |--: |--: |
|H/W の世代|4|4|4|4|4|
|仮想コア|1|2|4|8|16|
|メモリ (GB)|7|14|28|56|112|
|列ストアをサポート|[はい]|はい|はい|はい|[はい]|
|インメモリ OLTP ストレージ (GB)|該当なし|該当なし|該当なし|該当なし|該当なし|
|ストレージの種類|Premium (リモート) ストレージ|Premium (リモート) ストレージ|Premium (リモート) ストレージ|Premium (リモート) ストレージ|Premium (リモート) ストレージ|
|IO 待機時間 (概算)|5 ～ 7 ミリ秒 (書き込み)<br>5 ～ 10 ミリ秒 (読み取り)|5 ～ 7 ミリ秒 (書き込み)<br>5 ～ 10 ミリ秒 (読み取り)|5 ～ 7 ミリ秒 (書き込み)<br>5 ～ 10 ミリ秒 (読み取り)|5 ～ 7 ミリ秒 (書き込み)<br>5 ～ 10 ミリ秒 (読み取り)|5 ～ 7 ミリ秒 (書き込み)<br>5 ～ 10 ミリ秒 (読み取り)|
|最大データ サイズ (GB)|1024|1024|1536|3072|4096|
|最大ログ サイズ|307|307|461|922|1229|
|TempDB のサイズ (DB)|32|64|128|256|384|
|ターゲットの IOPS|320|640|1280|2560|5120|
|IO 待機時間 (概算)|5 ～ 7 ミリ秒 (書き込み)
|最大同時実行ワーカー (要求) 数|200|400|800|1600|3200|
|最大同時ログイン数|200|400|800|1600|3200|
|許可される最大セッション数|3000|3000|3000|3000|3000|
|レプリカの数|1|1|1|1|1|
|マルチ AZ|該当なし|該当なし|該当なし|該当なし|該当なし|
|読み取りスケールアウト|該当なし|該当なし|該当なし|該当なし|該当なし|
|含まれるバックアップ ストレージ|1X DB サイズ|1X DB サイズ|1X DB サイズ|1X DB サイズ|1X DB サイズ|
|||

### <a name="business-critical-service-tier"></a>Business Critical サービス レベル
|パフォーマンス レベル|BC_Gen4_1|BC_Gen4_2|BC_Gen4_4|BC_Gen4_8|BC_Gen4_16|
|:--- | --: |--: |--: |--: |--: |
|H/W の世代|4|4|4|4|4|
|仮想コア|1|2|4|8|16|
|メモリ (GB)|7|14|28|56|112|
|列ストアをサポート|[はい]|はい|はい|はい|[はい]|
|インメモリ OLTP ストレージ (GB)|1|2|4|8|20|
|ストレージの種類|接続されている SSD|接続されている SSD|接続されている SSD|接続されている SSD|接続されている SSD|
|最大データ サイズ (GB)|1024|1024|1024|1024|1024|
|最大ログ サイズ|307|307|307|307|307|
|TempDB のサイズ (DB)|32|64|128|256|384|
|ターゲットの IOPS|5000|10000|20000|40000|80000|
|IO 待機時間 (概算)|1 ～ 2 ミリ秒 (書き込み)<br>1 ～ 2 ミリ秒 (読み取り)|1 ～ 2 ミリ秒 (書き込み)<br>1 ～ 2 ミリ秒 (読み取り)|1 ～ 2 ミリ秒 (書き込み)<br>1 ～ 2 ミリ秒 (読み取り)|1 ～ 2 ミリ秒 (書き込み)<br>1 ～ 2 ミリ秒 (読み取り)|1 ～ 2 ミリ秒 (書き込み)<br>1 ～ 2 ミリ秒 (読み取り)|
|最大同時実行ワーカー (要求) 数|200|400|800|1600|3200|
|最大同時ログイン数|200|400|800|1600|3200|
|許可される最大セッション数|3000|3000|3000|3000|3000|
|レプリカの数|3|3|3|3|3|
|マルチ AZ|[はい]|はい|はい|はい|[はい]|
|読み取りスケールアウト|[はい]|はい|はい|はい|[はい]|
|含まれるバックアップ ストレージ|1X DB サイズ|1X DB サイズ|1X DB サイズ|1X DB サイズ|1X DB サイズ|
|||

## <a name="single-database-change-storage-size"></a>単一データベース: ストレージ サイズを変更する

- 1 GB の増分を使用して最大サイズの上限に達するまでストレージをプロビジョニングすることができます。 構成可能な最小データ ストレージは 5 GB です 
- 単一データベースのストレージは、[Azure Portal](sql-database-single-database-resources.md#manage-single-database-resources-using-the-azure-portal)、[Transact-SQL](/sql/t-sql/statements/alter-database-azure-sql-database#examples)、[PowerShell](/powershell/module/azurerm.sql/set-azurermsqldatabase)、[Azure CLI](/cli/azure/sql/db#az_sql_db_update)、または [REST API](/rest/api/sql/databases/update) を使って最大サイズを増減することでプロビジョニングできます。
- SQL Database は自動的に追加ストレージの 30% をログ ファイルに割り当て、TempDB の仮想コアごとに 32 GB を割り当てますが、384 GB を超えることはありません。 TempDB は、すべてのサービス レベルの接続されている SSD にあります。
- 単一データベースのストレージの料金は、データ ストレージとログ ストレージの容量の合計にサービス レベルのストレージ単価を掛けて計算します。 TempDB のコストは仮想コア価格に含まれています。 追加ストレージの価格について詳しくは、「[SQL Database の価格](https://azure.microsoft.com/pricing/details/sql-database/)」をご覧ください。

## <a name="single-database-change-vcores"></a>単一データベース: 仮想コアを変更する

仮想コア数を最初に選択した後は、[Azure Portal](sql-database-single-database-resources.md#manage-single-database-resources-using-the-azure-portal)、[Transact-SQL](/sql/t-sql/statements/alter-database-azure-sql-database#examples)、[PowerShell](/powershell/module/azurerm.sql/set-azurermsqldatabase)、[Azure CLI](/cli/azure/sql/db#az_sql_db_update)、または [REST API](/rest/api/sql/databases/update) を使い、実際の状況に基づいて、単一データベースを動的にスケールアップまたはスケールダウンできます。 

データベースのサービス レベルやパフォーマンス レベルを変更すると、新しいパフォーマンス レベルで元のデータベースのレプリカが作成され、接続先がそのレプリカに切り替えられます。 このプロセスでデータが失われることはありませんが、レプリカに切り替えるほんの少しの間、データベースに接続できなくなるため、実行中の一部トランザクションがロールバックされる場合があります。 切り替え時間はさまざまですが、通常 4 秒以内であり、99% 以上が 30 秒未満です。 接続が無効になった時点で多数のトランザクションが実行中の場合、切り替え時間が長引くことがあります。 

スケールアップ プロセス全体の継続時間は、変更前後のデータベースのサイズとサービス レベルによって異なります。 たとえば、250 GB のデータベースを General Purpose サービス レベルとの間または General Purpose サービス レベル内で変更する場合は、6 時間以内に完了します。 Business Critical サービス レベル内で同じサイズのデータベースのパフォーマンス レベルを変更する場合、スケールアップは 3 時間以内で完了します。

> [!TIP]
> 実行中の操作の監視については、[SQL REST API を使った操作の管理](/rest/api/sql/Operations/List)、[CLI を使った操作の管理](/cli/azure/sql/db/op)、[T-SQL を使った操作の管理](/sql/relational-databases/system-dynamic-management-views/sys-dm-operation-status-azure-sql-database)に関する各ページと、2 つの PowerShell コマンド [Get-AzureRmSqlDatabaseActivity](/powershell/module/azurerm.sql/get-azurermsqldatabaseactivity) と [Stop-AzureRmSqlDatabaseActivity](/powershell/module/azurerm.sql/stop-azurermsqldatabaseactivity) をご覧ください。

* より上位のサービス レベルまたはパフォーマンス レベルにアップグレードしても、より大きなサイズ (最大サイズ) を明示的に指定しない限り、データベースの最大サイズは増加しません。
* データベースをダウングレードするには、データベースで使われている領域がダウングレード後のサービス レベルとパフォーマンス レベルで許可されている最大サイズより小さい必要があります。 
* [geo レプリケーション](sql-database-geo-replication-portal.md)が有効な状態でデータベースをアップグレードする場合、そのセカンダリ データベースを目的のパフォーマンス レベルにアップグレードしてから、プライマリ データベースをアップグレードします (パフォーマンスを最大にするための一般的なガイダンス)。 別のエディションにアップグレードする場合は、最初にセカンダリ データベースのアップグレードが必要です。
* [geo レプリケーション](sql-database-geo-replication-portal.md)が有効な状態でデータベースをダウングレードする場合、プライマリ データベースを目的のパフォーマンス レベルにダウングレードしてから、セカンダリ データベースをダウングレードします (パフォーマンスを最大にするための一般的なガイダンス)。 別のエディションにダウングレードする場合は、最初にプライマリ データベースのダウングレードが必要です。
* データベースに対する新しいプロパティは、変更が完了するまで適用されません。

## <a name="elastic-pool-storage-sizes-and-performance-levels"></a>エラスティック プール: ストレージ サイズとパフォーマンス レベル

次の表では、SQL Database エラスティック プールについて、各サービス レベルおよびパフォーマンス レベルで使用可能なリソースを示します。 [Azure Portal](sql-database-elastic-pool.md#manage-elastic-pools-and-databases-using-the-azure-portal)、[PowerShell](sql-database-elastic-pool.md#manage-elastic-pools-and-databases-using-powershell)、[Azure CLI](sql-database-elastic-pool.md#manage-elastic-pools-and-databases-using-the-azure-cli)、または [REST API](sql-database-elastic-pool.md#manage-elastic-pools-and-databases-using-the-rest-api) を使って、サービス レベル、パフォーマンス レベル、ストレージ量を設定できます。

> [!NOTE]
> エラスティック プール内の個々のデータベースのリソース制限は、一般的に同じパフォーマンス レベルのプール外の単一のデータベースのリソース制限と同じです。 たとえば、GP_Gen4_1 データベースの最大同時実行ワーカー数は 200 ワーカーです。 そのため、GP_Gen4_1 プール内のデータベースの最大の同時実行ワーカー数も 200 ワーカーです。 GP_Gen4_1 プールの同時実行ワーカーの総数は 210 です。

### <a name="general-purpose-service-tier"></a>汎用のサービス階層
|パフォーマンス レベル|GP_Gen4_1|GP_Gen4_2|GP_Gen4_4|GP_Gen4_8|GP_Gen4_16|
|:--- | --: |--: |--: |--: |--: |
|H/W の世代|4|4|4|4|4|
|仮想コア|1|2|4|8|16|
|メモリ (GB)|7|14|28|56|112|
|列ストアをサポート|[はい]|はい|はい|はい|[はい]|
|インメモリ OLTP ストレージ (GB)|該当なし|該当なし|該当なし|該当なし|該当なし|
|ストレージの種類|Premium (リモート) ストレージ|Premium (リモート) ストレージ|Premium (リモート) ストレージ|Premium (リモート) ストレージ|Premium (リモート) ストレージ|
|最大データ サイズ (GB)|512|756|1536|2048|3584|
|最大ログ サイズ|154|227|461|614|1075|
|TempDB のサイズ (DB)|32|64|128|256|384|
|ターゲットの IOPS|320|640|1280|2560|5120|
|IO 待機時間 (概算)|5 ～ 7 ミリ秒 (書き込み)<br>5 ～ 10 ミリ秒 (読み取り)|5 ～ 7 ミリ秒 (書き込み)<br>5 ～ 10 ミリ秒 (読み取り)|5 ～ 7 ミリ秒 (書き込み)<br>5 ～ 10 ミリ秒 (読み取り)|5 ～ 7 ミリ秒 (書き込み)<br>5 ～ 10 ミリ秒 (読み取り)|5 ～ 7 ミリ秒 (書き込み)<br>5 ～ 10 ミリ秒 (読み取り)|
|最大同時実行ワーカー (要求) 数|210|420|840|1680|3360|
|最大同時ログイン数|210|420|840|1680|3360|
|許可される最大セッション数|3000|3000|3000|3000|3000|
|最大プール密度|100|200|500|500|500|
|最小/最大エラスティック プールのクリック停止|0、0.25、0.5、1|0、0.25、0.5、1、2|0、0.25、0.5、1、2、4|0、0.25、0.5、1、2、4、8|0、0.25、0.5、1、2、4、8、16|
|レプリカの数|1|1|1|1|1|
|マルチ AZ|該当なし|該当なし|該当なし|該当なし|該当なし|
|読み取りスケールアウト|該当なし|該当なし|該当なし|該当なし|該当なし|
|含まれるバックアップ ストレージ|1X DB サイズ|1X DB サイズ|1X DB サイズ|1X DB サイズ|1X DB サイズ|
|||

### <a name="business-critical-service-tier"></a>Business Critical サービス レベル
|パフォーマンス レベル|GP_Gen4_1|GP_Gen4_2|GP_Gen4_4|GP_Gen4_8|GP_Gen4_16|
|:--- | --: |--: |--: |--: |--: |
|H/W の世代|4|4|4|4|4|
|仮想コア|1|2|4|8|16|
|メモリ (GB)|7|14|28|56|112|
|列ストアをサポート|[はい]|はい|はい|はい|[はい]|
|インメモリ OLTP ストレージ (GB)|1|2|4|8|20|
|ストレージの種類|接続されている SSD|接続されている SSD|接続されている SSD|接続されている SSD|接続されている SSD|
|最大データ サイズ (GB)|1024|1024|1024|1024|1024|
|最大ログ サイズ|307|307|307|461|614|
|TempDB のサイズ (DB)|32|64|128|256|384|
|ターゲットの IOPS|320|640|1280|2560|5120|
|IO 待機時間 (概算)|1 ～ 2 ミリ秒 (書き込み)<br>1 ～ 2 ミリ秒 (読み取り)|1 ～ 2 ミリ秒 (書き込み)<br>1 ～ 2 ミリ秒 (読み取り)|1 ～ 2 ミリ秒 (書き込み)<br>1 ～ 2 ミリ秒 (読み取り)|1 ～ 2 ミリ秒 (書き込み)<br>1 ～ 2 ミリ秒 (読み取り)|1 ～ 2 ミリ秒 (書き込み)<br>1 ～ 2 ミリ秒 (読み取り)|
|最大同時実行ワーカー (要求) 数|210|420|840|1680|3360|
|最大同時ログイン数|210|420|840|1680|3360|
|許可される最大セッション数|3000|3000|3000|3000|3000|
|最大プール密度|該当なし|50|100|100|100|
|最小/最大エラスティック プールのクリック停止|0、0.25、0.5、1|0、0.25、0.5、1、2|0、0.25、0.5、1、2、4|0、0.25、0.5、1、2、4、8|0、0.25、0.5、1、2、4、8、16|
|マルチ AZ|[はい]|はい|はい|はい|[はい]|
|読み取りスケールアウト|[はい]|はい|はい|はい|[はい]|
|含まれるバックアップ ストレージ|1X DB サイズ|1X DB サイズ|1X DB サイズ|1X DB サイズ|1X DB サイズ|
|||
エラスティック プールのすべての仮想コアがビジーの場合は、プール内の各データベースが、同量のコンピューティング リソースを受け取ってクエリを処理します。 SQL Database サービスは、コンピューティング時間を均等にすることで、データベース間におけるリソース共有の公平性を実現します。 それ以外の場合、エラスティック プールのリソース共有の公平性は、データベースあたりの仮想コア分が 0 以外の値に設定されているときに、リソース量に加えて各データベースに適用されることが保証されます。

### <a name="database-properties-for-pooled-databases"></a>プールされたデータベースのデータベース プロパティ

次の表では、プールされたデータベースのプロパティについて説明します。

| プロパティ | [説明] |
|:--- |:--- |
| データベースあたりの最大仮想コア数 |プール内の他のデータベースによる使用状況に基づいて使用可能な場合にプール内の任意のデータベースが使用できる仮想コアの最大数。 データベースごとの最大仮想コア数は、データベースに対して保証されたリソースではありません。 これは、プール内のすべてのデータベースに適用されるグローバル設定です。 データベースのピーク使用率を処理するのに十分高いデータベースあたり最大仮想コア数を設定します。 プールでは通常、ホットとコールドのデータベース使用パターンがあり、すべてのデータベースが同時に最大に使用されることはないため、ある程度高めに上限が設定されています。|
| データベースごとの最小の仮想コア数 |プール内の任意のデータベースで保証される仮想コアの最小数。 これは、プール内のすべてのデータベースに適用されるグローバル設定です。 データベースあたりの最小仮想コア数は 0 に設定でき、これが既定値です。 このプロパティは、0 とデータベースあたりの平均仮想コア使用率の間に設定されます。 プール内のデータベースの数とデータベースごとの最小仮想コア数の積がプールごとの仮想コア数の値を超えることはできません。|
| データベースあたりの最大ストレージ容量 |プール内のデータベースに対してユーザーによって設定される最大データベース サイズ。 プールされたデータベースは割り当てられたプール ストレージを共有するので、データベースが到達できるサイズは、残りのプール ストレージとデータベース サイズのうち、どちらか小さい方に制限されます。 最大データベース サイズとはデータ ファイルの最大サイズのことであり、ログ ファイルによって使用される領域は含まれません。 |
|||
 
## <a name="elastic-pool-change-storage-size"></a>エラスティック プール: ストレージ サイズを変更する

- 最大サイズの上限に達するまでストレージをプロビジョニングすることができます。 
 - Standard ストレージの場合は、10 GB の増分でサイズを増減します
 - Premium ストレージの場合は、250 GB の増分でサイズを増減します
- エラスティック プールのストレージは、[Azure Portal](sql-database-elastic-pool.md#manage-elastic-pools-and-databases-using-the-azure-portal)、[PowerShell](/powershell/module/azurerm.sql/set-azurermsqlelasticpool)、[Azure CLI](/cli/azure/sql/elastic-pool#az_sql_elastic_pool_update)、または [REST API](/rest/api/sql/elasticpools/update) を使って最大サイズを増減することでプロビジョニングできます。
- エラスティック プールのストレージの料金は、ストレージ量にサービス レベルのストレージ単価を掛けて計算します。 追加ストレージの価格について詳しくは、「[SQL Database の価格](https://azure.microsoft.com/pricing/details/sql-database/)」をご覧ください。

## <a name="elastic-pool-change-vcores"></a>エラスティック プール: 仮想コアを変更する

[Azure Portal](sql-database-elastic-pool.md#manage-elastic-pools-and-databases-using-the-azure-portal)、[PowerShell](/powershell/module/azurerm.sql/set-azurermsqlelasticpool)、[Azure CLI](/cli/azure/sql/elastic-pool#az_sql_elastic_pool_update)、または [REST API](/rest/api/sql/elasticpools/update) を使って、リソースのニーズに基づいてエラスティック プールのパフォーマンス レベルを増減できます。

- プールの仮想コアを再スケーリングするときは、データベースの接続が短時間失われます。 これは、(プールではなく) 単一データベースの DTU を再スケーリングするときと同じ動作です。 再スケーリング操作中にデータベース接続が失われる時間とその影響について詳しくは、「[単一データベース: DTU を変更する](#single-database-change-storage-size)」をご覧ください。 
- プールの仮想コアの再スケーリングに要する時間は、プール内のすべてのデータベースで使われているストレージの総量によって異なる場合があります。 一般に、再スケーリングの待機時間の平均は 100 GB あたり 90 分以下です。 たとえば、プール内のすべてのデータベースで使用される領域の合計が 200 GB の場合、プールの再スケーリングにかかる想定待機時間は、3 時間以下になります。 Standard または Basic レベルでは場合により、使われている容量に関係なく、再スケーリングの待機時間が 5 分未満になることがあります。
- 一般に、データベースあたりの最小仮想コア数またはデータベースあたりの最大仮想コア数の変更に要する時間は、5 分以内です。
- プールの仮想コア数をダウンサイズするときは、プールで使われている領域が、ターゲットのサービス レベルとプール仮想コアで許可されている最大サイズより小さい必要があります。

## <a name="what-is-the-maximum-number-of-servers-and-databases"></a>サーバーとデータベースの最大数

| 最大値 | 値 |
| :--- | :--- |
| サーバーあたりのデータベース数 | 5000 |
| サブスクリプションあたりのサービスの数 (リージョンあたり) | 20 |
|||

> [!IMPORTANT]
> データベースの数がサーバーあたりの制限に近づくと、次の状況が発生します。
> <br> •    マスター データベースに対して実行するクエリの待機時間が増えます。  これには、リソース使用率統計情報のビューも含まれます (sys.resource_stats など)。
> <br> •    サーバー内のデータベースの列挙を要する、管理操作やポータル ビュー ポイント表示の待機時間が長くなります。

## <a name="what-happens-when-database-and-elastic-pool-resource-limits-are-reached"></a>データベース リソースとエラスティック プール リソースが制限に達したときの影響

### <a name="compute-vcores"></a>コンピューティング (仮想コア)

(仮想コアの使用率によって測定された) データベース コンピューティングの使用率が高くなると、クエリの待機時間が増加し、タイムアウトすることさえあります。このような状況下では、クエリはサービスによってキューに格納されることがあり、リソースが空くと実行用のリソースを提供されます。
高いコンピューティング使用率が発生する場合、次のような軽減オプションがあります。

- データベースまたエラスティック プールのパフォーマンス レベルを上げて、より多くの仮想コアをデータベースに提供します。 「[単一データベース: 仮想コアを変更する](#single-database-change-vcores)」と「[エラスティック プール: 仮想コアを変更する](#elastic-pool-change-vcores)」をご覧ください。
- クエリを最適化して、各クエリのリソース使用率を引き下げます。 詳しくは、「[クエリの調整とヒント](sql-database-performance-guidance.md#query-tuning-and-hinting)」をご覧ください。

### <a name="storage"></a>Storage

使用済みのデータベース容量が最大サイズの上限に達すると、データのサイズが増えるデータベースの挿入および更新は失敗し、クライアントは[エラー メッセージ](sql-database-develop-error-messages.md)を受け取ります。 データベースの SELECTS と DELETES は引き続き成功します。

高い容量使用率が発生する場合、次のような軽減オプションがあります。

- データベースまたはエラスティック プールの最大サイズを増やすか、パフォーマンス レベルを変更して最大ストレージを増やします。 [SQL Database の仮想コアベースのリソース制限](sql-database-vcore-resource-limits.md)に関する記事をご覧ください。
- データベースがエラスティック プール内にある場合は、もう 1 つの方法として、データベースをプールの外に移動し、ストレージ領域が他のデータベースと共有されないようにすることもできます。

### <a name="sessions-and-workers-requests"></a>セッションとワーカー (要求) 

セッションおよびワーカーの最大数は、サービス レベルとパフォーマンス レベルによって決まります。 セッションまたはワーカーが上限に達した場合、新しい要求は拒否され、クライアントはエラー メッセージを受け取ります。 利用可能な接続の数はアプリケーションで制御できますが、同時ワーカーの数は推定または制御が困難なことがよくあります。 データベース リソースが上限に達し、クエリを長時間実行したためにワーカーが滞留するピーク負荷期間は特にそうです。 

セッションまたはワーカーの使用率が高い場合は、次のような軽減オプションがあります。
- データベースまたはエラスティック プールのサービス レベルまたはパフォーマンス レベルを高くします。 「[単一データベース: ストレージ サイズを変更する](#single-database-change-storage-size)」、「[単一データベース: 仮想コアを変更する](#single-database-change-vcores)」、「[エラスティック プール: ストレージ サイズを変更する](#elastic-pool-change-storage-size)」、「[エラスティック プール: 仮想コアを変更する](#elastic-pool-change-vcores)」をご覧ください。
- ワーカー使用率上昇の原因がコンピューティング リソースの競合である場合は、クエリを最適化して各クエリのリソース使用率を下げます。 詳しくは、「[クエリの調整とヒント](sql-database-performance-guidance.md#query-tuning-and-hinting)」をご覧ください。

## <a name="next-steps"></a>次の手順

- よく寄せられる質問の回答については、「[SQL Database に関する FAQ](sql-database-faq.md)」をご覧ください。
- Azure の一般的な制限については、「[Azure サブスクリプションとサービスの制限、クォータ、制約](../azure-subscription-service-limits.md)」をご覧ください。
