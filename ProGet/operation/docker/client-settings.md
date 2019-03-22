---
title: Dockerクライアントの設定
keywords: ProGet
sequence: 20
show-related-content: false
---

ProGetはトークンベースの認証を使用します。つまり、Docker 1.11.0以降を使用する必要があります。

Dockerにログインします。 これを行うには、次のコマンドを使用します。ここで、progetsv1はProGetサーバーの名前です。
```
[~]$ sudo docker login progetsv1
```


## イメージを公開する
DockerイメージをProGetに公開するには、Dockerを使用して特別な形式でイメージにタグを付ける必要があります。 ローカルイメージの名前がubuntu：trustyの場合は、次のようにタグを付け直します。  
```  
[~]$ sudo docker tag ubuntu:trusty progetsv1:443/dmc/ubuntu:trusty  
```   
Once tagged, the image can now be pushed to ProGet:  
```
[~]$ sudo docker push progetsv1:443/dmc/ubuntu:trusty
```

## 画像を抽出する

その後、コマンドに若干の変更を加えるで画像を引っ張ることができます。


## ガベージコレクション
パッケージとは異なり、Dockerイメージは自己完結型ではありません。これはマニフェストBLOBへの参照であり、マニフェストBLOBは多数のレイヤーBLOBを参照します。 これらのレイヤBLOBは、レジストリ内の他のマニフェストによって参照される可能性があります。つまり、マニフェストBLOBを削除するときに、参照されているレイヤBLOBを単純に削除することはできません。

ガベージコレクションは、マニフェストから参照されなくなったパッケージストアからBLOBを削除するプロセスです。 ProGetは "FeedCleanUp"スケジュールされたジョブを通してDockerレジストリのガベージコレクションを実行します。
