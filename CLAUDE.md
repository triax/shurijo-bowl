# CLAUDE.md

このファイルは、このリポジトリでコードを扱う際のClaude Code (claude.ai/code) への指針を提供します。

## プロジェクト概要

これは「第3回 首里城ボウル」のための静的ウェブサイトプロジェクトです。2025年6月29日に沖縄県読谷村陸上競技場で開催される、TRIAX（東京、X2-EAST）対琉球ガーディアンライオンズ（沖縄、X2-WEST）のアメリカンフットボールイベントです。沖縄県内でXリーグのチーム同士が試合を行うのは史上初となります。

## プロジェクト構造

- `/2025/` - メインイベントページディレクトリ
  - `index.html` - 動的な選手データ読み込み機能を持つイベントランディングページ
  - `2025.css` - アニメーション付きイベント専用スタイル
  - `README.md` - イベント情報とデータソース
- `/index.css` - プロジェクト全体で共有されるグローバルスタイル
- `/.gitignore` - .claudeと.vscodeディレクトリを無視

## 主要機能

1. **動的な選手データ読み込み**: 
   - Google SheetsのCSVエンドポイントから選手名簿を取得
   - 選手カードに写真（Google Driveサムネイル）、名前、ポジション、メッセージを表示
   - CSVパーサーは日本語テキストと特殊文字を処理
   
2. **キービジュアル統合**: Google Driveからイベントポスターを表示
3. **インタラクティブUI**: AOS（Animate On Scroll）、jQuery、Tailwind CSSを使用したアニメーション
4. **レスポンシブデザイン**: 様々なデバイスに対応するモバイルファーストアプローチ

## アーキテクチャメモ

- **純粋な静的サイト**: ビルドプロセス、フレームワーク、サーバーサイドレンダリングなし
- **データ読み込み**: JavaScriptがページ読み込み時にCSVデータを取得し、動的に選手カードを生成
- **スタイリングアプローチ**: Tailwindユーティリティとカスタムアニメーション用CSSの組み合わせ
- **アニメーションシステム**: 背景の波、グロー効果、ホバー状態のCSSアニメーション

## 開発コマンド

これはビルドプロセスのない静的HTML/CSS/JSプロジェクトです。開発するには：

```bash
# ローカルでサイトを提供（任意の静的サーバーを使用）
python3 -m http.server 8000
# または
npx serve .
```

## 外部依存関係

プロジェクトはCDNホストされたライブラリを使用：
- Tailwind CSS - ユーティリティスタイリング用
- jQuery 3.7.1 - DOM操作用
- AOS 2.3.1 - スクロールアニメーション用
- Font Awesome 6.5.1 - アイコン用
- Google Fonts（Bebas Neue、Noto Sans JP）

## データソース

- 選手名簿: Google SheetsのCSVエクスポート `https://docs.google.com/spreadsheets/d/1pBskF8oCg3HrdWtv0xACeWDfe7_mZZ8-2a8gncHRhjA/gviz/tq?tqx=out:csv`
- キービジュアル画像: Google DriveファイルID `1fuqRf0ehzLjTGAzmzui3orfc8zLkHS8I`
- 選手写真: Google DriveサムネイルAPIフォーマット: `https://drive.google.com/thumbnail?id={photoId}&sz=w400`

## デザインシステム

- **カラー**: オレンジ（#fb923c から #ef4444）とブルー（#3b82f6）のアクセントを持つダークテーマ
- **タイポグラフィ**: ヘッダーにBebas Neue、本文にNoto Sans JP
- **エフェクト**: グラデーション背景、アニメーション波、グローイングテキストシャドウ、シマーエフェクト