﻿---
title: ガイド：リポジトリフックを使う
keywords: buildmaster
sequence: 50
show-related-content: false
---

BuildMasterはGitHubとGitLabによって起動されたカスタムウェブフックイベントをサポートします。  それぞれの特定のシステムに必要な設定の詳細についてはGit extension Wikiをご覧ください。

BuildMasterは特定のアプリケーションでビルドを作成するためにGitHubウェブフックイベントを受け取ることができます。

## 前提条件
GitHub WebフックをBuildMasterと統合するには、次の前提条件が必要です。

{.docs}
- 少なくとも1つのリポジトリまたは組織を持つGitHubアカウント  
- BuildMaster v6.1以降がインストールされている  
- BuildMasterサーバー上のBuildMasterのWebサイトポートに受信ファイアウォールルールを追加  

## GitHubの設定

{.docs}
- GitHubはリポジトリまたは組織レベルでWebフックをサポートします。ほとんどの場合、単一のWebフックエンドポイントのみを構成する必要があるため、組織レベルが適しています。

Webフックを作成するには、リポジトリまたは組織の[設定] > [Webフック]セクションにアクセスします。以下のオプションを設定してください。

{.docs}
- ペイロードURL：次のステップで生成されます
- コンテンツタイプ：application / json
- 機密：安全なトークンを作成し、次のステップにそれを書き留めます
- SSL検証：セキュリティのためにこれを有効にする必要があります、ウェブサーバー上で有効な証明書- 設定が必要です
- イベント：プッシュイベントだけ
- アクティブ：チェック

## BuildMasterの設定
BuildMasterで、Administration> Repository Hooks＆Monitorsページにアクセスしてwebhookレシーバーを追加します。 GitHubウェブフックを作成するには、以下のオプションがあります。

{.docs}
- 名前：生成されたペイロードURLの識別子としても機能する、Webhookエンドポイントを説明するわかりやすい名前。英数字、ダッシュ、および下線のみが許可されています  
- アプリケーション用に実行：特定のアプリケーションが選択されている場合、そのアプリケーション内のすべてのアクティブなリリースに対してビルドが作成されます。アプリケーションが選択されていない場合は、代わりに指定されたグローバルプランが実行されます（例については下記を参照）。  
- プラン：実行されるプラン。指定されている場合は適用範囲、それ以外の場合はグローバル計画  
- アクティブ：非アクティブなウェブフックはビルドを作成したり指定された計画を実行したりしません  
- 秘密のトークン：これはGitHub側で入力された秘密のフィールドと一致しなければなりません
- 保存すると、BuildMasterホストに関連するペイロードURLが概要ページに表示されます。 例： api / hooks / GitHubHook。

## GitHub設定を完了する"

WebMookレシーバーがBuildMasterで作成されたら、ペイロードURLとして、パブリックにアクセス可能なBuildMasterホストを基準にしてそのURLを入力します。次に例を示します。

詳細はこちら：`https://buildmaster.inedo.com/api/hooks/GitHubHook`

Webフックが保存されると、BuildMasterはGitHubプッシュイベントを受け入れる準備が整います。

設定をテストするには、直接コミットを押すか、GitHubでページを編集後、Settings > Webhooks > Editページを使用して、BuildMasterに送信されたデータとその反応を表示します。
