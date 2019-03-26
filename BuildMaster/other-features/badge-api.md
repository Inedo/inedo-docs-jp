---
title: バッジAPI
keywords: buildmaster
sequence: 10
show-related-content: false
---


BuildMasterは、外部ツールが次のような "CIバッジ"を生成するためにビルドステータスに問い合わせることを可能にします。

CIバッジAPIにアクセスするには、APIへのアクセス権を持つAPIキーを追加する必要があります。 その後、次のURLを使用してバッジイメージまたは対応するビルド/実行へのリンクを生成できます。

#### 画像：  
{buildmaster-host} / api / ci-badges / image？API_Key = {yourApiKey}＆$ ApplicationName = {appName}  

#### リンク：
{buildmaster-host} / api / ci-badges / link？API_Key = {yourApiKey}＆$ ApplicationName = {appName}

バッジ指定子はアプリケーションに限定されず、コミットID、ブランチなどに基づいてさらにフィルタリングすることができます。 バッジの設定方法およびクエリ方法の詳細については、CI Badge APIのドキュメントを参照してください。
