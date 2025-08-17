---
layout: post
title: PowerShell で Docker コンテナを操作するメモ
date: 2025-08-16 14:00:00 +0900
categories: [技術メモ]
image: /assets/images/powershell-docker.png
description: "Windows11上でPowerShellとDocker Desktopを使ってコンテナを管理するための基本的なコマンドをまとめました。"
---

最近のプロジェクトでは Docker を使った環境構築が欠かせません。ここでは、Windows 11 上の PowerShell から Docker コンテナを操作する際に良く使うコマンドをまとめました。

## Docker Desktop のインストール確認

まずは Docker Desktop がインストールされているか確認しましょう。PowerShell で以下のコマンドを実行します。

```powershell
docker version
```

クライアントとサーバーのバージョン情報が表示されれば、インストールは完了しています。

## イメージの取得と実行

Docker Hub から公式の nginx イメージを取得して実行する場合は次のようにします。

```powershell
docker pull nginx:latest
docker run --name my-nginx -p 8080:80 -d nginx:latest
```

このコマンドでポート 8080 で nginx が起動します。ブラウザで `http://localhost:8080` にアクセスして確認しましょう。

## コンテナの一覧表示と停止

動作中のコンテナを確認するには次のコマンドを使います。

```powershell
docker ps
```

停止したい場合は `docker stop`、削除したい場合は `docker rm` を実行します。

```powershell
docker stop my-nginx
docker rm my-nginx
```

今後も便利なコマンドや Tips を追記していきます。