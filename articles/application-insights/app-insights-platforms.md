---
title: 'Application Insights: 言語、プラットフォーム、統合 | Microsoft Docs'
description: Application Insights で利用できる言語、プラットフォーム、統合
services: application-insights
documentationcenter: ''
author: OlegAnaniev-MSFT
manager: carmonm
ms.assetid: 974db106-54ff-4318-9f8b-f7b3a869e536
ms.service: application-insights
ms.workload: tbd
ms.tgt_pltfrm: ibiza
ms.devlang: na
ms.topic: get-started-article
ms.date: 09/01/2016
ms.author: mbullwin
ms.openlocfilehash: 7440bb38fc68ce49504188a40ca1aafbb1e07913
ms.sourcegitcommit: c3d53d8901622f93efcd13a31863161019325216
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/29/2018
---
# <a name="developer-analytics-languages-platforms-and-integrations"></a>開発者分析: 言語、プラットフォーム、統合
以下は、これまでに把握している [Application Insights](app-insights-overview.md) の実装です (サード パーティによるものも含む)。

## <a name="languages---officially-supported-by-application-insights-team"></a>Application Insights チームで正式にサポートされている言語
* [C#|VB (.NET)](app-insights-asp-net.md)
* [Java](app-insights-java-get-started.md)
* [JavaScript Web ページ](app-insights-javascript.md)
* [Node.JS](app-insights-nodejs.md)

## <a name="languages---community-supported"></a>コミュニティでサポートされている言語
* [PHP](https://github.com/Microsoft/ApplicationInsights-PHP)
* [Python](https://pypi.python.org/pypi/applicationinsights/0.1.0)
* [Ruby](https://rubygems.org/gems/application_insights)
* [その他](#projects)

## <a name="platforms-and-frameworks"></a>プラットフォームとフレームワーク
* [ASP.NET](app-insights-asp-net.md)
* [ASP.NET - 既にライブとなっているアプリ用](app-insights-monitor-performance-live-website-now.md)
* [ASP.NET Core](app-insights-asp-net-core.md)
* [Android](https://github.com/Microsoft/ApplicationInsights-Android) (App Center、HockeyApp)
* [Azure Web Apps](app-insights-azure-web-apps.md)
* [Azure Cloud Services](app-insights-cloudservices.md)&#151; Web ロールと worker ロールの両方を含む
* [Azure Functions](https://github.com/christopheranderson/azure-functions-app-insights-sample)
* [Docker](app-insights-docker.md)
* [Glimpse](https://azure.microsoft.com/blog/glimpse-application-insights/)
* [iOS](https://github.com/Microsoft/ApplicationInsights-iOS) (App Center、HockeyApp)
* [J2EE](app-insights-java-get-started.md)
* [J2EE - 既にライブとなっているアプリ用](app-insights-java-live.md)
* [macOS アプリ](https://support.hockeyapp.net/kb/client-integration-ios-mac-os-x-tvos/hockeyapp-for-mac-os-x) (HockeyApp)
* [Node.JS](https://www.npmjs.com/package/applicationinsights)
* [OSX](https://github.com/Microsoft/ApplicationInsights-OSX)
* [Spring](http://joe.blog.freemansoft.com/2015/12/enabling-microsoft-application-insight.html)
* [ユニバーサル Windows アプリ](https://support.hockeyapp.net/kb/client-integration-windows-and-windows-phone/how-to-create-an-app-for-uwp) (App Center、HockeyApp)
* [WCF](https://github.com/Microsoft/ApplicationInsights-SDK-Labs/blob/master/WCF/readme.md)
* [Windows Phone 8 および 8.1 アプリ](https://support.hockeyapp.net/kb/client-integration-windows-and-windows-phone/hockeyapp-for-windows-phone-silverlight-apps-80-and-81) (HockeyApp)
* [Windows Presentation Foundation アプリ](https://support.hockeyapp.net/kb/client-integration-windows-and-windows-phone/hockeyapp-for-windows-wpf-apps) (HockeyApp)
* [Windows デスクトップのアプリケーションとサービス、および worker ロール](app-insights-windows-desktop.md)
* [その他](#projects)

## <a name="logging-frameworks"></a>ログ記録フレームワーク
* [Log4Net、NLog、または System.Diagnostics.Trace](app-insights-diagnostic-search.md)
* [Java、Log4J、または Logback](app-insights-java-trace-logs.md)
* [セマンティック ログ (SLAB)](https://github.com/fidmor89/SLAB_AppInsights) - [セマンティック ログ アプリケーション ブロック](https://msdn.microsoft.com/library/dn440729.aspx)と統合
* [クラウド ベースのロード テスト](http://blogs.msdn.com/b/visualstudioalm/archive/2015/07/30/getting-application-insights-counters-with-cloud-based-load-testing.aspx)
* [LogStash プラグイン](https://github.com/Azure/azure-diagnostics-tools/tree/master/Logstash/logstash-output-applicationinsights)
* [Log Analytics](https://blogs.technet.microsoft.com/msoms/2016/09/26/application-insights-connector-in-oms/)
* [Logary](https://www.nuget.org/packages/Logary.Targets.AppInsights/)
* [Logrus](https://github.com/jjcollinge/logrus-appinsights)

## <a name="content-management-systems"></a>コンテンツ管理システム
* [Concrete](https://github.com/fidmor89/appInsights-Concrete)
* [Drupal](https://github.com/fidmor89/AppInsights-Drupal)
* [Joomla](https://github.com/fidmor89/AppInsights-Joomla)
* [Orchard](https://azure.microsoft.com/blog/integrating-application-insights-into-a-modular-cms-and-a-multi-tenant-public-saas/preview/)
* [SharePoint](app-insights-sharepoint.md)
* [WordPress](https://wordpress.org/plugins/application-insights/)

## <a name="export-and-data-analysis"></a>エクスポートとデータの分析
* [Alooma](https://www.alooma.com/blog/application-insights-amazon-redshift)
* [Power BI](http://blogs.msdn.com/b/powerbi/archive/2015/11/04/explore-your-application-insights-data-with-power-bi.aspx)
* [Stream Analytics](app-insights-export-power-bi.md)

## <a name="projects"></a> 独自の SDK をビルドする
使用する言語やプラットフォーム用の SDK がない場合は、自分で作成するという方法があります。 [GitHub の Application Insights SDK プロジェクト](https://github.com/Microsoft/AppInsights-Home)に示されている既存の SDK のコードをご覧ください。
