---
title: アドミニストレーション
keywords: ProGet
sequence: 50
show-related-content: false
---

## ライセンスキー管理
Inedo製品内のライセンスキーを変更するには、キーを追加または変更するためのリンクがある「Licensing&amp;Activation」ページを使用して行います。 MyInedoから新しいキーを要求することができます。


## セキュリティとアクセスコントロール

セキュリティおよびアクセスコントロールポリシーは、プリンシパル（ユーザーまたはグループ）に特定の範囲で（フィード固有またはグローバルに）特定のタスクを実行する権限を与えることによって定義されます。 たとえば、「 'Internal Developers'グループは 'Dev'フィードに 'Publish Packages'を実行できます」と定義することができます。

プリンシパルは、ユーザーディレクトリで定義されます。ユーザーディレクトリは、内部（つまりProGetに組み込まれている）、または外部（Active DirectoryやLDAPなど）のいずれかです。 これにより、組織の他のメンバーがユーザーアカウントとグループメンバーシップを管理できるようにしながら、シングルサインオンエクスペリエンスを作成できます。

プリンシパルがタスクを実行するのを制限することもできます。たとえば、「 'Developers'グループは 'Restricted'フィードに 'Publish Packages'を実行できません」。 これらの重複するルールは、外部で定義されたユーザーディレクトリと同様に、きめ細かいアクセス制御ポリシーをモデル化するために使用できます。

ProGetには5つのタスクが付属しています。  

| Task | Result |
|------|--------|
| Administrate | Progetのインスタンスをコントロール |
| フィードを管理 | フィード設定の管理、パッケージの削除、およびパッケージの上書きアクセスを許可します。|
| パッケージをプロモートする | 同じフィードタイプの指定されたフィードにパッケージをプロモートするためのアクセスを許可します。 このタスクを許可されたユーザーには、少なくともソースフィードの[パッケージの表示とダウンロード]タスクも許可する必要があります。 |
| パッケージを公開する | フィードからパッケージを公開、アップロード、プッシュ、プルするためのアクセスを許可します。 |
| パッケージの表示とダウンロード | フィードからパッケージを表示およびダウンロードするためのアクセスを許可します。
