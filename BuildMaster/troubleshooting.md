﻿---
title: Buildmasterのトラブルシューティング#
keywords: buildmaster
sequence: 50
show-related-content: false
---

発生しがちな問題は次のとおりです。


#### BuildMasterサーバーはインターネットからアクセスできません。：  

この場合、要求はBuildMasterから開始されるため、Repository Monitorsがより適している可能性があります

#### ビルドが作成されていません。：  

カスタムプランが指定されていない場合、ビルドはアプリケーション内の最新のアクティブリリースに対してのみトリガーされます。 カスタムプランが指定されている場合は、そのプランがアプリケーションやリリースを列挙し、さらにビルドを作成します。

#### ログ：  

特定のトリガーのBuildMasterログ（要求がBuildMasterに到達したと仮定した場合）は、「管理」>「実行」ページにあります。 モードで絞り込む：トリガーをビルドして表示します。  

GitHub Webhooksページには、すべてのwebhookリクエスト、リクエストボディ、レスポンスが表示され、リクエストを再送信することもできます。
