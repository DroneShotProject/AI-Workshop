# AI 開発ワークショップ アウトライン & 詳細解説

本ドキュメントは、「AIを活用した現代的なソフトウェア開発」を学ぶワークショップのアウトラインおよび講義用詳細資料です。

---

## 1. 本日のゴール (Workshop Goals)

AIがコードを自動生成する時代において、エンジニアやプランナーが持つべきマインドセットと本質的なスキルを定義します。

### ① 「コードが書けること」は重要ではない
- **背景**: 生成AI（LLM）の進化により、プログラミング言語の文法知識や単純なコーディング作業の価値は相対的に低下しています。
- **本質**: 私たちが目指すべきは「コードを書くこと」ではなく、**「価値のあるプロダクト（動くソフトウェア）を世に送り出すこと」**です。

### ② 「作りたいもの」を詳細に言語化できるか
- **課題**: AIに「〇〇なアプリを作って」と曖昧（抽象的）に頼むと、AIは一般的な無難なものしか出力できず、期待通りの成果物は得られません。
- **解決策（具体化の技術）**:
  - ターゲットユーザー、解決したい課題、具体的な機能要件（Input/Output）、画面構成、表示するデータ（APIの仕様など）を**具体的かつ論理的に言語化**する力が必要です。
  - プロンプトにどれだけ「具体的で詳細な文脈（Context）」を与えられるかが、成果物のクオリティを左右します。

### ③ 「モデル」と「エージェント」の違い
- **モデル (Model)**: 知識や推論能力を提供する「脳」にあたる存在（例：GPT-4, Claude 3.5 Sonnet, Gemini 1.5 Pro）。
- **エージェント (Agent)**: 脳の命令を受けて、実際にファイルを読み書きしたり、ターミナルでコマンドを実行したり、ブラウザを操作して検証を行う「手足」を持った自律プログラム。
- **現在地**: 単にチャットでAIと会話する時代から、**エージェントが開発環境と統合され、動くソフトウェアを自動で構築・検証してくれる時代**へと移行しています。今最も価値があるのは、脳内にあるアイデアを「実際に動いて利用価値があるソフトウェア」として素早く展開することです。

### ④ 「無料」を使い倒せ & アカウントの特権を活かせ
- **個人の無料枠**: 各社が提供している無料枠、無料プラン（Google AI Studio、Claude Consoleの初期枠など）を組み合わせることで、お金をかけずに強力な開発環境・API環境を作れます。
- **大学アカウントの活用 (特権)**:
  - **Microsoft 365 大学アカウント**: 大学が提供する学内アカウントは多くの場合、有料プラン（Microsoft 365 Copilot）が利用可能です。組織向けセキュリティ（商用データ保護）が適用された状態で、GPT-4oなどの最新GPTモデルを安全かつ無料で利用できます。
  - **Google Workspace 大学アカウント**: 同様に、学術機関向けセキュリティが保証された環境でGemini等の高性能モデルを安全に利用できます。これらはデータがモデルの再学習に使用されないため、開発中のコードや機密性の高いアイデアを入力する際にも安心して使えます。

---

## 2. モデル (Models) - 各プラットフォームの概要

開発で使用される主要な大規模言語モデル（LLM）の特徴を比較します。

### GPT (OpenAI)
- **ChatGPT**: 最も普及している対話型AI。最新モデル（GPT-4o等）は高速で、汎用的なコーディング指示に強い。
- **Codex (現行のAPI/モデル群に統合)**: かつてGitHub Copilotの基盤となった、コード生成に特化したモデル群。

### Claude (Anthropic)
- **Claude**: 日本語の自然な表現や、極めて高い倫理的・論理的推論能力が強み。コードのバグ修正やアルゴリズム設計において高い評価を得ています。
- **Claude Code**: Anthropicが開発した、ターミナル上で自律的に動作する最新のコーディングエージェント。

### Gemini / Google AI Studio (Google)
- **Gemini**: 超巨大なコンテキストウィンドウ（100万〜200万トークン）を持ち、リポジトリ全体のコードや膨大なドキュメントを一括して読み込めるのが強み。
- **Google AI Studio**: Googleの提供するWebベースの開発者向け無料プラットフォーム。Gemini 1.5 Pro / FlashのAPIキーを無料で発行でき、システム指示（System Instructions）や安全設定を細かく調整しながらプログラミング補助やコード生成の検証を高速に行うことができます。コーディング支援能力が非常に高く、API呼び出し回数の無料枠も太っ腹です。
- **Gemini CLI**: コマンドラインからGeminiの強力な機能にアクセスするためのユーティリティ。
- **Antigravity**: 本開発環境で動作しているような、より高度な意思決定とファイル編集能力を持つ自律型エージェント。

---

## 2.5. AIプラットフォームと利用チャネルの整理

AI技術はモデル単体ではなく、多様なプラットフォームやデバイス（チャネル）を通じて開発者に提供されています。主要なプラットフォームとそれぞれの具体的な利用方法（名称・ツール）を以下に整理します。

### ① 利用形態（チャネル）ごとの代表例

| 利用形態 | 特徴 | 主要なツール・名称 |
| :--- | :--- | :--- |
| **ブラウザ (Web UI)** | チャットUIを通じて対話的に使用する。最初のアイデア出しやコードレビューに最適。 | ChatGPT, Claude.ai, Gemini, Microsoft Copilot |
| **デスクトップ APP** | 専用アプリ。ショートカット起動や画面共有機能など、OSと統合された便利な機能を持つ。 | ChatGPT Desktop, Claude Desktop, Microsoft Copilot |
| **モバイル APP** | スマホやタブレットからアクセス。移動中のアイデア出しや音声でのやり取りに便利。 | ChatGPT (iOS/Android), Claude (iOS/Android), Gemini App |
| **IDE 拡張機能** | エディタ内に直接統合され、コードを書いている最中にリアルタイムでアシストする。 | GitHub Copilot, Gemini in VS Code, Roo Cline (Cline) |
| **CLI (Command Line)** | ターミナルから直接コマンドでAIを呼び出す。自動化スクリプトやパイプライン処理に強い。 | Claude Code, Gemini CLI, gh copilot |
| **開発者向けプラットフォーム** | APIキーの発行、プロンプトの調整、モデルの挙動テスト、データ連携等を行う環境。 | **Google AI Studio**, OpenAI Platform (Playground), Anthropic Console |
| **クラウド・インフラ (DB)** | AI開発に必要なデータ、ベクトルデータ、実行環境を管理するインフラ基盤。 | **MongoDB Atlas** (ベクトル検索・データホスティング), Vertex AI, Azure OpenAI |

### ② プラットフォーム別：提供ツール・インターフェース対応表

| プラットフォーム | ブラウザ (Web) | デスクトップ App | モバイル App | IDE拡張 / 専用IDE | CLI / エージェント | 開発者プラットフォーム |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **OpenAI / Microsoft** | ChatGPT, Microsoft Copilot | ChatGPT Desktop | ChatGPT App, Copilot App | GitHub Copilot | gh copilot | OpenAI Platform (Playground) |
| **Anthropic** | Claude.ai | Claude Desktop | Claude App | Roo Cline (API連携), Cursor (連携) | **Claude Code** (自律エージェント) | Anthropic Console (Workbench) |
| **Google** | Gemini Web | (PWA等のWeb対応) | Gemini App | Gemini in VS Code, Project IDX | Gemini CLI | **Google AI Studio**, Vertex AI |
| **データ・インフラ** | **MongoDB Atlas** (Web UI) | Compass (GUIツール) | - | Atlas VS Code 拡張機能 | Atlas CLI | MongoDB Atlas (インフラ・ベクトルDB) |

---

## 3. エージェント (Agents) & 開発環境

AIと協調して開発を行うためのエージェントシステムや統合開発環境（IDE）のリンクと解説です。

### 主要ツール一覧
- **[Claude Code (Docs)](https://code.claude.com/docs/ja/overview)**: 
  - Anthropicが提供する自律型CLIエージェント。ターミナル上で動き、ファイルの検索、コードの書き換え、テストの実行までを自律的にこなします。
- **[OpenAI Codex / Developer Platform](https://openai.com/ja-JP/codex/)**: 
  - OpenAIが提供するコード生成APIやツールの紹介。現在の高度なコード生成アシスタントの先駆け。
- **[Gemini CLI (geminicli.com)](https://geminicli.com/)**: 
  - Geminiのパワーをターミナルで手軽に利用するためのCLIツール群。
- **[Cursor (cursor.com)](https://cursor.com/ja)**: 
  - VS Codeをベースに開発された、AIネイティブな次世代コードエディタ。コードの自動補完（Copilot++）や、リポジトリ全体を考慮したチャット、コードの差分インライン編集などが非常に強力です。
- **[Visual Studio Code (VS Code)](https://code.visualstudio.com/)**: 
  - デファクトスタンダードのコードエディタ。豊富なAI拡張機能（Marp, GitHub Copilot, Roo Clineなど）を追加することで、強力なAI開発環境に変貌します。

---

## 4. デザイン (Design tools)

開発の初期段階でUI/UXのプロトタイプを素早く作成し、AIにコードへ落とし込ませるためのツールです。

- **Figma Make**: Figma上でプロンプトからデザイン要素を自動生成したり、静止画からコンポーネントを構築する機能。
- **Stitch**: UIコンポーネントの視覚的な構築やコードへのエクスポートを容易にするモダンなツール。

---

## 5. MCP (Model Context Protocol)

**MCP (Model Context Protocol)** は、AIモデルが外部のデータソース、ツール, APIと安全かつ標準化された方法で安全に接続・通信するためのオープンソースプロトコルです。

- **[Chrome DevTools MCP](https://github.com/ChromeDevTools/chrome-devtools-mcp)**:
  - AIエージェントがChromeブラウザのDevToolsを直接操作できるようにするMCPサーバー。AI自身がブラウザのコンソールログを確認したり、DOM構造を解析してデバッグすることが可能になります。
- **[Figma MCP Catalog](https://www.figma.com/ja-jp/mcp-catalog/)**:
  - FigmaのデザインデータをAIがコンテキストとして正確に読み取るためのMCP連携。デザインの仕様やスタイルガイドを直接AIに参照させながらコーディングを進めることができます。

---

## 6. 手を動かしてみよう (Hands-on)

### 演習課題：リアルタイム気象データ表示Webアプリの構築

以下の具体的なプロンプト情報をAIエージェントに与え、実際に動くWebアプリケーションを一瞬で構築するデモまたはハンズオンを行います。

#### プロンプト指示（例）
```text
このデータを表示するWebアプリケーションを作りたい。

[フレームワーク1]: React (Vite)
[フレームワーク2]: TypeScript / Tailwind CSS
UIコンポーネントは shadcn/ui を使って。

データソースAPI:
https://api.open-meteo.com/v1/forecast?latitude=41.841784&longitude=140.766926&hourly=temperature_2m&timezone=auto&past_days=0&forecast_days=7

要件:
1. 上記API（函館の7日間の気温予測データ）からデータを非同期で取得し、見やすいグラフ（Rechartsなど）で視覚化すること。
2. shadcn/ui の Card や Button コンポーネントを使用し、ダッシュボード風のモダンなUIにすること。
3. 気温が特定のしきい値（例: 25度以上）を超える時間帯をハイライトする機能を付けること。
```

#### ハンズオンの流れ
1. **プロジェクトの初期化**: `npm create vite@latest` または `npx create-next-app` を用いて、エージェントにプロジェクトを作らせる。
2. **shadcn/ui のセットアップ**: テーマカラー（今回のワークショップで定義した `#AF1F24`）を `tailwind.config.js` に設定。
3. **API連携の実装**: `fetch` または `axios` を用いて Open-Meteo API からデータを取得。
4. **UIの実装**: グラフコンポーネントを配置し、レスポンシブなダッシュボードを構築。
5. **ローカル実行・動作確認**: `npm run dev` で起動し、ブラウザで実際に函館の気象データが表示されることを確認。
