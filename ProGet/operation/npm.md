---
title: NPM
keywords: ProGet
sequence: 40
show-related-content: false
---

NodeJS用のnpmクライアントと互換性を持つのがProGet npmフィードです。 ProGet npmフィードは、スコープ付きとスコープなしの両方のnpmパッケージをサポートします。

npmjs.orgのパブリックリポジトリへのコネクタは、スコープ付きパッケージを検索結果に含めません。これは、パブリックリポジトリにはそれらを含めるためのメカニズムがないためです。 スコープ付きパッケージは、このコネクタを介して使用できます。 それらは検索から除外されるだけであり、これはnpmjs.orgで直接検索した場合と同じ動作です。

npmクライアントはWindows統合認証の使用をサポートしていないため、ProGetは基本HTTP認証を優先してnpm APIエンドポイントの使用を無効にしようとします。 ただし、URLごとにWindows認証を無効にしても、すべての環境で機能するわけではありません。 これでうまく動かない場合は、別途ライセンスを取得せずに、Windows認証を無効にしたProGet用のIISで2つ目のウェブサイトを作成することができます。

### ProGetの構成

1. ナビゲーションバーのFeedsタブをクリックすると、システム内にフィードのリストが表示されます。  
2. [新規フィードを作成]ボタンをクリックして[npm]を選択します。  
3. フィード名フィールドにURLに適した値を指定します。 例：“プライベートnpm”  
4. [フィードの作成]ボタンをクリックすると、自動的に新しく作成されたレジストリに移動します。  
5. ProGetサーバーがインターネットにアクセスできる場合は、npmjs.orgのパッケージのリストが表示されます。 これらはコネクタパッケージと呼ばれ、ProGetインスタンスではホストされていませんが、他のサーバーから可視化できるようプロキシされています。  
6. npmフィードを作成したら、フィード内に直接、またはページ上部の[コネクタ]タブをクリックして、npmjs.orgのコネクタを追加できます。 このようにしてあなたはあなたの個人的なものに加えてパッケージのその豊富なライブラリにアクセスすることができます。 外部パッケージのサブセットのみを含める場合は、コネクタでフィルタリングも可能です。

### npmの設定

デフォルトでは、npmはnpmjs.orgからデータを取得するように設定されています。 次のコマンドを使用して、ProGetサーバーの名前/ポートの名前をprogetに置き換え、上記で作成したnpmフィードの名前をprivate-npmに置き換えます。

```
[~]$ npm config set registry http://proget/npm/private-npm
```

## パッケージを公開する
npmを使ってパッケージをProGetに公開することもできます。 adduserコマンドを使用してProGetのデフォルトのAdminアカウントとしてログインし、パスワードの入力を求められたら、ProGetへのログインに使用したものと同じパスワードを使用します（デフォルトはAdmin）。  
```    
[~]$ npm adduser

[~]$ npm publish package.tgz  
```