﻿---
title: リポジトリにコミットしてビルドを開始する
keywords: buildmaster
sequence: 30
show-related-content: false
---

BuildMasterは、自動ビルドを開始するための3つの方法をサポートしています。

{.docs}  
- リポジトリモニタ - コードリポジトリを定期的にポーリングし、最新のコミットを取得および比較して新しいビルドを開始する必要があるかどうかを判断する、ユーザー設定のBuildMasterサービス。  
- リポジトリフック - パイプラインで定義されたGitHubまたはGitLabリポジトリは、変更を検出するとビルドの作成を開始します。  
- Release＆Build API  -  TeamCity、Jenkinsなど、サードパーティのシステムからビルドを作成するための最も一般的な方法です。

注：リポジトリモニタとリポジトリフックはどちらも、プラン内で使用できる共通の変数をサポートしています。 デフォルトの変数は次のとおりです。  

{.docs}
- $ Branch  - 最初に参照/ヘッド/なしでコミットがプッシュされた参照。 例：マスター  
- $CommitHash  - コミットに関連付けられたID、SHA、またはハッシュ。例  525571720b56ca53d1d3229e774c7b7980d3ff2b
