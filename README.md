# プロンプト作例集

Threadsでいいねしたプロンプトを使って、Museが画像を生成した作例を貯めるサイトです。
プロンプト全文と生成結果と元の投稿を、セットで残します。

- サイトID: `prompt`
- 実装は山形グルメ案内（Markdown CMS）と同じ仕組みです。記事の frontmatter に `source_url` を書くと、詳細JSONに `embed_platform`／`embed_url` が付き、記事ページで元の投稿（Threads／Instagram）の公式埋め込みを表示します。
- カバー画像は任意です（`source_url` の埋め込みがある記事では省略できます）。
- 作例記事の型（標準）: 記事本文には「使ったプロンプト」の節を作り、実際に使ったプロンプトの全文をコードブロック（```）でそのまま載せること。要旨だけにしない。記事ページでは、コードブロックにコピーボタンが付きます。

## ローカルビルド

```sh
python3 -m venv .venv
.venv/bin/pip install -r requirements.txt
.venv/bin/python scripts/build.py
.venv/bin/python -m unittest discover -s scripts -p 'test_*.py'
```

生成物は `dist/` に出ます（コミット対象外）。公開側では GitHub Actions が `data/` と `docs/` へ同期し、GitHub Pages（`docs/`）で配信します。

公開サイト: https://oosawak.github.io/prompt-gallery/
