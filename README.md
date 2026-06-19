# Px Downloader Fixed

> [Px Downloader](https://github.com/rndomhack/px-downloader) の非公式メンテナンス版。pixiv からイラスト・漫画・うごイラ・小説をダウンロードする Firefox / Chrome 拡張機能。

![Version](https://img.shields.io/badge/version-3.6.0.3-blue)
![License](https://img.shields.io/badge/license-MIT-green)
![Firefox](https://img.shields.io/badge/Firefox-supported-orange?logo=firefox)
![Chrome](https://img.shields.io/badge/Chrome-supported-blue?logo=googlechrome)

## オリジナルからの変更点

### v3.6.0.3

- **UTF-8 絵文字修正** — 作品タイトルに ZWJ sequence（🏴‍☠️, 👯‍♀️ 等の合成絵文字）が含まれるとダウンロードが失敗する問題を修正。ファイル名から U+200D (ZWJ), U+FE0F, U+FE0E (Variation Selector) を除去
- **DL完了時の自動ブックマーク** — ダウンロード完了後、pixiv のブックマークボタンを自動クリック
- **AMO 対応** — `data_collection_permissions` 追加、`downloads.shelf`（Chrome専用）パーミッション削除

## 元リポジトリ

[rndomhack/px-downloader](https://github.com/rndomhack/px-downloader) — オリジナル版（メンテナンス終了）

## インストール

### Firefox

1. [Releases](https://github.com/dekotan24/px-downloader/releases) から `.xpi` をダウンロード
2. Firefox で `about:addons` を開き、歯車アイコン → 「ファイルからアドオンをインストール」

### ソースからビルド

```bash
git clone https://github.com/dekotan24/px-downloader.git
cd px-downloader
npm install
NODE_OPTIONS=--openssl-legacy-provider npm run build
```

ビルド成果物は `dist/` に出力されます。

## 使い方

1. pixiv の作品ページを開く
2. 画像の右上に表示される **PX** ボタンをクリック
3. 設定した保存先にダウンロードされます

### 対応コンテンツ

| タイプ | 形式 |
|-------|------|
| イラスト | PNG / JPG（原寸） |
| 漫画 | 複数ページ ZIP |
| うごイラ | ZIP / GIF / APNG / WebP |
| 小説 | テキスト |

## 技術スタック

| | |
|---|---|
| ビルド | webpack 5 + Babel |
| ポリフィル | webextension-polyfill |
| 圧縮 | JSZip |
| アニメーション | gif.js |

## ライセンス

MIT（[オリジナル](https://github.com/rndomhack/px-downloader)と同じ）
