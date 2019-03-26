---
title: 脆弱性スキャン
keywords: ProGet
sequence: 10
show-related-content: false
---

ProGetの脆弱性スキャンおよびブロック機能は、誤ってフィードに安全でないパッケージを組み込んでしまうことからあなたを保護します。 Sonatype（OSS Index）とWhiteSourceの2つの主要な脆弱性スキャン企業と提携して、サードパーティのパッケージを脆弱性データベースに対して自動的にスキャンします。

ProGetは、脆弱性を管理するための3つの異なるワークフローをサポートしています。

|      | マニュアル | OSS Index | Whitesource |
|------|-------|------|-------|
| コスト | - | - | $$$ |
| スキャン力 | * | *** | ***** |
| 脆弱なパッケージをブロック | ✔ | ✔ | ✔ |
| 手動での脆弱性リポートの入力 | ✔ | - | - |
| ProGet内で脆弱性レポートを評価 | ✔ | ✔ | - |
| 公開データベースの自動スキャン | - | ✔ | ✔ |
| Scan propriety databases | - | - | ✔ |
| 購入の必要有無 | - | -<sup>R</sup> | [Sign Up](https://www.whitesourcesoftware.com/trial3/) |



<sup>R</sup>OSSインデックスは有料での購入は必要ありませんが、ユーザーは登録アカウントを作成する必要があります。

これらのワークフローの詳細については、ProGetとOSS Indexの統合およびProGetとWhiteSourceの統合のドキュメントを参照してください。

## フィードと脆弱性の設定
脆弱性スキャンとブロックを使用するようにフィードを明確に設定する必要があります。 最終結果は同じですが、ワークフローはProGetのさまざまな機能を使用します。

脆弱性の発生源は、手動およびOSSのインデックス管理ワークフローに使用されます。 これらは評価する必要のあるProGetに脆弱性記録を追加します

パッケージアクセスルールはWhiteSource管理のワークフローに使用されます。 WhiteSourceで設定されたルールに基づいてこれらのブロックパッケージのダウンロード

[フィードの管理]ページで両方を設定できます。 OSSインデックスが脆弱性の原因として、またはWhiteSourceとしてパッケージアクセスルールとして表示されない場合は、[管理]> [拡張機能]をチェックして、それらの拡張機能がインストールされていることを確認してください。