# Copilotへの指示
- このファイルは、Copilotに対する指示を含んでいます。
- このファイルを編集することで、Copilotの動作を調整できます。

- アカウント認証(ログイン)しないと内容を閲覧できないURLに遭遇した場合、「このURLの内容は読めません」と必ず返答してください。
  あたかもURLの内容を読んでいるかのように振る舞うことは避けてください。

## PJ概要

# デプロイ先
GitHub Pages

# 利用ツール
ジェキルを利用。
Jekyll＝ビルド時にMarkdown等をHTMLに焼き固める静的サイトメーカー（Liquidテンプレート）。

# 公開URL
https://orange-lemon-22.github.io/blog/

# ローカルPATH
C:\Users\mail\dev\GitHubPages\blog-site-updated

# GitHub上のURL
https://github.com/orange-lemon-22/blog

# Jekyllを使った理由
GitHub Pagesが公式でサポートしている静的サイトジェネレータ
記事は Markdown（.md）を置くだけでOK → 運用が超シンプル
テーマやレイアウトが フォルダ/ファイルで見通せる（学習コスト低い）

# 仕組み
ノート（.md）を「_posts」という箱に入れるとジェキルという“整えるロボ”がきれいなWebページに仕上げてくれる。
表紙（トップページ）やプロフィールも、決まった箱に置けば自動で並ぶよ。

# 基本のしくみ
静的サイトジェネレータ：フォルダにある Markdown/HTML を読んで、完成したHTML（_site/）を作るだけ。サーバー側の処理はゼロ。
フロントマター：各記事の先頭にある --- ではさまれた設定（YAML）。タイトルや日付、使うレイアウトを指定する。
レイアウト：ページの「型」。_layouts/default.html が土台、記事は _layouts/post.html で本文をはめ込む。
インクルード：共通パーツ。_includes/adsense.html のように、必要な場所で {% include adsense.html %} すると同じコードを使い回せる。

# 公開後、記事を増やす運用：_posts に置くだけ？リビルドは？
運用：はい、置くだけです。_posts/YYYY-MM-DD-スラッグ.md を追加してコミット＆プッシュ。
リビルド：GitHub Pages が自動で再生成します（手動ビルドは不要）。
※ もし独自プラグイン等で「Pages標準ビルドに非対応」の構成にする場合は、GitHub Actionsで自前ビルド→
gh-pagesに出力、という運用に切り替えます。今回の構成はPages標準ビルドでOKです。

# サイト全体構成
blog-site/
├─ _config.yml                # サイト全体の設定（タイトル、URL、AdSense、プラグイン など）
├─ index.md                   # トップページ（記事一覧を出す）
├─ about.md                   # プロフィールページ
├─ _layouts/                  # ページの型（テンプレート）
│  ├─ default.html            # 全ページの土台（ヘッダ/フッタ等）
│  └─ post.html               # 記事ページの型（本文のはめ込み先）
├─ _includes/                 # 共通パーツ
│  └─ adsense.html            # AdSense読み込みスクリプト（有効化時のみ）
├─ _posts/                    # 記事を置く場所（Markdownファイル）
│  ├─ 2025-08-17-copilot-gpt5.md
│  └─ 2025-08-18-kiro.md
├─ assets/                    # 画像やCSSなどの静的ファイル
│  ├─ css/
│  │  └─ style.css            # ここをいじればデザイン調整
│  └─ images/
│     ├─ welcome-hero.png
│     └─ powershell-docker.png
└─ _site/                     # （生成物）ローカルビルド時に出力。Git管理に含めない


# 各フォルダの役割
| 場所               | 役割（短語）     |
| ---------------- | ---------- |
| `_posts/`        | 記事Markdown |
| `_layouts/`      | ページの型      |
| `_includes/`     | 共通部品       |
| `assets/css/`    | 見た目（CSS）   |
| `assets/images/` | 画像置き場      |
| `index.md`       | トップページ     |
| `about.md`       | プロフィール     |
| `_config.yml`    | 全体設定       |

