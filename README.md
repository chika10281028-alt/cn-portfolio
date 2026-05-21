# cn-portfolio

面接用のポートフォリオサイトです。Web アプリ開発の学習を兼ねて、**Blazor WebAssembly** で実装しています。

---

## 🚀 概要

- 自己紹介・スキル・経歴・プロジェクト事例を1サイトに集約したポートフォリオ
- Blazor WebAssembly の SPA として動作（静的ホスティングのみで動く）
- GitHub Pages で公開

公開 URL: `https://chika10281028-alt.github.io/cn-portfolio/`

---

## 🛠 使用技術

| カテゴリ | 採用技術 |
| --- | --- |
| フレームワーク | Blazor WebAssembly (.NET 8) |
| 言語 | C#  |
| マークアップ・スタイル | HTML / CSS |
| バージョン管理 | Git |
| デプロイ先 | GitHub Pages（`main`ブランチの`docs/` ブランチフォルダから配信） |

---
## 🛠 技術選定の背景

**なぜ Blazor WebAssembly を選んだのか:**

- 業務で培った C# / .NET の経験を活かしながら、フロントエンド開発にも取り組みたかったため
- C# でフロントエンドを実装できる Blazor WebAssembly に興味を持ち、Web アプリケーション開発を実践的に学習したかったため
- HTML / CSS については部分的な修正経験が中心だったため、Blazor WebAssembly のテンプレートをベースに、一人で画面実装やレイアウト調整を行いたかったため
- ポートフォリオ公開にあたり、GitHub Pages を利用した静的ホスティング構成を経験したかったため

このポートフォリオでは、C# / .NET の既存スキルを活かしながら、Web アプリケーションのフロント領域への理解を広げることを目的として開発を行いました。

---

## 📄 ページ構成

| パス | 役割 | 主な構成要素 |
| --- | --- | --- |
| `/` | Home | ヒーローセクション / 実績ハイライト / 強み3カード |
| `/about` | About | プロフィール / 業務概要 / 強み / 資格 / 目標 / 趣味 |
| `/skills` | Skills | 使用技術カード一覧 |
| `/experience` | Experience | 担当工程 / 開発経験 |

---

## 📁 プロジェクト構成

```
.
├── App.razor                # ルートコンポーネント (Router)
├── Program.cs               # WebAssembly Host エントリポイント
├── _Imports.razor           # 共通 @using 宣言
├── blazor-portfolio.csproj  # SDK: Microsoft.NET.Sdk.BlazorWebAssembly
├── blazor-portfolio.sln
│
├── Layout/
│   ├── MainLayout.razor       # サイドバー + メイン + フッターのレイアウト
│   ├── MainLayout.razor.css
│   ├── NavMenu.razor          # 左サイドバーのナビゲーション
│   └── NavMenu.razor.css
│
├── Pages/
│   ├── Home.razor + .css       # トップページ
│   ├── About.razor + .css      # 自己紹介
│   ├── Skills.razor + .css     # スキル一覧 (record 配列で生成)
│   └── Experience.razor + .css # 担当工程・開発経験
│
├── wwwroot/
│   ├── index.html             # SPA のエントリ HTML
│   ├── 404.html               # GitHub Pages 用 SPA フォールバック
│   ├── .nojekyll              # Jekyll 抑止
│   ├── favicon.png
│   ├── icon-192.png
│   └── css/
│       ├── app.css            # グローバルスタイル
│       └── bootstrap/         # Bootstrap 5 
│
└── docs/                    # GitHub Pages 公開ディレクトリ
                             # (publish 出力をここにコピー)
```

---

## 💻 ローカル起動

`.NET 8 SDK` がインストールされている前提です。

```bash
dotnet run
```

起動後、コンソールに表示される URL（例: `http://localhost:5xxx/`）にアクセス。

---

## 📦 GitHub Pages デプロイ手順

GitHub Pages の配信ソースを `main` ブランチの `docs/` フォルダに設定している前提です。

```bash
# 1. リリースビルド
dotnet publish -c Release -o publish

# 2. docs/ を更新（既存ファイルをクリアして publish 出力をコピー）

# 3. .nojekyll を配置（Jekyll が _framework/ を無視しないため）

# 4. push
```

数十秒〜1 分で公開 URL に反映されます。

### GitHub リポジトリの設定

- Settings → Pages
- **Source**: `Deploy from a branch`
- **Branch**: `main` / `/docs`
