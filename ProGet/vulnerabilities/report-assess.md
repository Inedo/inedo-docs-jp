---
title: ProGetの脆弱性レポートと評価
keywords: ProGet
sequence: 20
show-related-content: false
---

手動ワークフローとOSSインデックスワークフローの両方が脆弱性レポートを使用します。これは、特定のパッケージ、またはバージョン付きのパッケージの範囲に既知の脆弱性があることを本質的に識別します。 このレコードは手動で入力されるか、特定のフィードのパッケージに基づいてOSSインデックスからインポートされます。

新しく入力またはインポートされた脆弱性レポートはすべて未評価と見なされます。つまり、脆弱性に一致するパッケージはレポートが評価されるまでブロックされます。 評価には、承認されたユーザーによるレポートの確認、評価の種類の選択（無視、注意、ブロック）、およびオプションのコメントの入力が含まれます。


## 評価タイプ

ProGetには、3つの評価タイプが組み込まれています。

#### 無視
脆弱性レポートが適用されない、または無関係であることを示します。したがって、パッケージをダウンロードすることができます。

#### 警告
開発者はこの脆弱性を回避するように注意する必要があります。 パッケージはダウンロードされるかもしれませんが、警告がWeb UI上で発行されます

#### ブロック
脆弱性が深刻すぎて使用できないため、パッケージがダウンロードされない
名前、有効期限、重大度（色）、およびパッケージをブロックするかどうかを指定して、独自の評価タイプを編集または作成できます。

## 権限と制限を追加する
タスクは、[管理]> [セキュリティ]> [タスク]ページから権限（許可または制限）を追加または削除することによって、プリンシパルに割り当てられます。 交付金は次のもので構成されています。

プリンシパル - ユーザーまたはグループ
範囲 - 特定のフィードまたはすべてのフィード
タスク - プリンシパルが実行できること（または実行しないこともあります）
