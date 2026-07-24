# AI 開発ワークショップ アウトライン & 詳細解説

> **最終更新: 2026年6月11日** — Jina AIを使用したWeb横断検索による最新情報に更新済み

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
- **モデル (Model)**: 知識や推論能力を提供する「脳」にあたる存在（例：GPT-5.4, Claude Sonnet 4.6, Gemini 3.5 Flash）。
- **エージェント (Agent)**: 脳の命令を受けて、実際にファイルを読み書きしたり、ターミナルでコマンドを実行したり、ブラウザを操作して検証を行う「手足」を持った自律プログラム。
- **現在地**: 単にチャットでAIと会話する時代から、**エージェントが開発環境と統合され、動くソフトウェアを自動で構築・検証してくれる時代**へと移行しています。今最も価値があるのは、脳内にあるアイデアを「実際に動いて利用価値があるソフトウェア」として素早く展開することです。

### ④ 「無料」を使い倒せ & アカウントの特権を活かせ
- **個人の無料枠**: 各社が提供している無料枠、無料プラン（Google AI Studio、Claude Consoleの初期枠など）を組み合わせることで、お金をかけずに強力な開発環境・API環境を作れます。
- **大学アカウントの活用 (特権)**:
  - **Microsoft 365 大学アカウント (MS Copilot 365)**: 大学が提供する学内の有料アカウントを使えば、組織向けセキュリティ（商用データ保護）が適用された状態で、**GPT-5.4 / GPT-5.5** などの最新GPTモデルを安全かつ無料で利用できます。プロンプトやコードがモデルの再学習に使用されないため、開発中のコードも安心して入力できます。
  - **Google Workspace 大学アカウント**: 同様に、学術機関向けセキュリティが保証された環境でGemini等の高性能モデルを安全に利用できます。

### ⑤ AIへの課金は「自己投資」— 生産性向上と周りとの差別化
- **個人の自由と選択**: AIに課金するかどうかは個人の自由です。しかし、月額数千円（「飲み会1回分」程度）の投資で、得られるリターンは計り知れません。
- **生産性向上と学び**: 有料プランに課金することで、最新・最速のモデルや制限の少ない開発用エージェントを使いこなすことができ、日々の学習や開発の生産性が劇的に向上します。これは単なる出費ではなく、大きな「学び」と「時間」を買う自己投資です。
- **将来へのアドバンテージと差別化**: 企業に就職してからも、ビジネスや開発の現場で生成AIを使うのは当たり前の時代になっています。今のうちに有料ツールを使いこなすことで、「AIをどう実務に組み込むか」「AIエージェントにどう的確な指示を与えるか」というスキルが身につき、他の人と圧倒的な差別化を図ることができます。
- **コピペ開発からの脱却（世界が変わる体験）**:
  - Webサイト上の無料チャット画面にコードを「コピペ」して質問するやり方では、プロジェクト全体の依存関係やファイル構成（コンテキスト）をAIが理解できません。
  - 一方、課金してCursor Pro、Claude Code、Google Antigravityなどのプロ仕様のAIエージェントやIDE環境を構築すると、**プロジェクト全体を丸ごと読み取って自動デバッグや機能実装を行ってくれるため、開発の次元が文字通り変わります。**

---

## 2. モデル (Models) - 各プラットフォームの最新概要

> **2026年6月11日現在の情報**（各公式サイトより）

開発で使用される主要な大規模言語モデル（LLM）の最新系列を整理します。

### GPT (OpenAI) — 最新モデル: GPT-5 系列
| モデル名 | コンテキスト | 特徴 | 主な用途 |
| :--- | :--- | :--- | :--- |
| **GPT-5.5** | 1.05M tokens | 最上位フラッグシップ | 最高精度の推論・複雑なエージェントタスク |
| **GPT-5.4** | 1.05M tokens | 高性能・汎用 | コーディング、多段推論、文書生成 |
| **GPT-5.4 mini** | 400K tokens | 高速・低コスト | 大量処理、日常的なコーディング補助 |

- **ChatGPT**: ブラウザ/アプリ/デスクトップから手軽に使える対話型AI。最新GPT-5系列を搭載。
- **Codex**: コード生成に特化した系列。現在のOpenAI APIに統合されており、GPT-5でより高精度なコード生成が可能。
- **OpenAI Platform (Playground)**: APIキーの発行、モデルのテスト、プロンプト調整を行う開発者向けWebサービス。

### Claude (Anthropic) — 最新モデル: Claude 4〜5系列
| モデル名 | 特徴 | 主な用途 |
| :--- | :--- | :--- |
| **Claude Mythos** | 最上位・次世代最高推論 | 高度な知識労働、研究・科学的推論 |
| **Claude Fable** | 高性能フラッグシップ | 複雑なコーディング・文書作成 |
| **Claude Opus 4.7** | 高性能・汎用上位 | エンタープライズ向け高精度タスク |
| **Claude Sonnet 4.6** | バランス型・標準モデル | 日常のコーディング補助・テキスト生成 |
| **Claude Haiku** | 高速・軽量 | 大量テキスト処理・シンプルなタスク |

- **Claude Code**: Anthropicが開発した、ターミナル上で自律的に動作するコーディング専用エージェント（CLI）。
- **Claude Cowork**: デスクトップアプリと連携し、ローカルファイルやクラウドアプリに対してタスクを自律実行する新サービス。
- **Claude Security**: セキュリティ分析・脆弱性検出に特化したプロダクト。

### Gemini / Google AI Studio (Google) — 最新: Gemini 3.5 系列
| モデル名 | 特徴 | 主な用途 |
| :--- | :--- | :--- |
| **Gemini 3.5 Flash** | フロンティア性能・エージェント特化 | コーディング・マルチエージェントワークフロー |
| **Gemini 3.1 Pro** | 複雑タスク・高精度 | 複雑な推論・創造的タスク |
| **Gemini 3.1 Deep Think** | 科学・研究・工学向け最高推論 | 高度な科学推論・複雑な問題解決 |
| **Gemini 3.1 Flash-Lite** | 高効率・低コスト | 大量処理・シンプルなタスク |

- **Google AI Studio**: Gemini APIキーの無料発行と、モデルの動作テスト（System Instructions設定含む）ができる開発者向けWebプラットフォーム。コーディング支援能力が非常に高く、無料枠も豊富。
- **Gemini CLI**: コマンドラインからGeminiの強力な機能にアクセスするためのユーティリティ。
- **Google Antigravity** (本ツール): GoogleのAI-firstな開発プラットフォーム。Gemini 3.5 Flashを搭載した自律型エージェントが、ファイル編集からターミナル操作、ブラウザ検索まで開発作業全体を担う。
- **Gemma**: GoogleのオープンソースLLM（ローカル実行可）。独自のAIシステム構築に利用可能。

---

## 2.5. AIプラットフォームと利用チャネルの整理

AI技術はモデル単体ではなく、多様なプラットフォームやデバイス（チャネル）を通じて開発者に提供されています。主要なプラットフォームとそれぞれの具体的な利用方法（名称・ツール）を以下に整理します。

### ① 利用形態（チャネル）ごとの代表例

| 利用形態 | 特徴 | 主要なツール・名称 |
| :--- | :--- | :--- |
| **ブラウザ (Web UI)** | チャットUIを通じて対話的に使用する。最初のアイデア出しやコードレビューに最適。 | ChatGPT, Claude.ai, Gemini (gemini.google.com), Microsoft Copilot |
| **デスクトップ APP** | 専用アプリ。ショートカット起動や画面共有・ローカルファイル連携など、OSと統合された機能を持つ。 | ChatGPT Desktop, Claude Desktop (Cowork機能搭載), Microsoft Copilot, Google Antigravity |
| **モバイル APP** | スマホやタブレットからアクセス。移動中のアイデア出しや音声でのやり取りに便利。 | ChatGPT (iOS/Android), Claude (iOS/Android), Gemini App, Microsoft Copilot |
| **IDE 拡張機能 / AI-native IDE** | エディタ内に直接統合され、コードを書いている最中にリアルタイムでアシストする。 | GitHub Copilot, Gemini in VS Code, Roo Cline (Cline), **Cursor** (AI-native IDE) |
| **CLI (Command Line)** | ターミナルから直接コマンドでAIを呼び出す。自動化スクリプトやパイプライン処理、自律実行に強い。 | **Claude Code** (自律エージェント), **Gemini CLI**, gh copilot |
| **開発者向けプラットフォーム (Developer Platform)** | APIキーの発行、プロンプトの調整、モデルの挙動テスト、データ連携等を行う環境。 | **Google AI Studio**, OpenAI Platform (Playground), Anthropic Console |
| **クラウド・インフラ (DB / MLOps)** | AI開発に必要なデータ、ベクトルデータ、実行環境を管理するインフラ基盤。 | **MongoDB Atlas** (ベクトル検索・データホスティング), Vertex AI, Azure OpenAI Service, **MCP Atlas** |

### ② プラットフォーム別：提供ツール・インターフェース対応表

| プラットフォーム | ブラウザ (Web) | デスクトップ App | モバイル App | IDE拡張 / 専用IDE | CLI / エージェント | 開発者プラットフォーム |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **OpenAI / Microsoft** | ChatGPT, MS Copilot | ChatGPT Desktop, Copilot | ChatGPT App, Copilot App | GitHub Copilot | gh copilot | OpenAI Platform (Playground) |
| **Anthropic** | Claude.ai | **Claude Desktop** (Cowork) | Claude App | Roo Cline (API連携), Cursor | **Claude Code** (CLIエージェント) | Anthropic Console (Workbench) |
| **Google** | Gemini Web | **Google Antigravity** | Gemini App | Gemini in VS Code, Project IDX | **Gemini CLI** | **Google AI Studio**, Vertex AI |
| **データ・インフラ** | **MongoDB Atlas** (Web UI) | Compass (GUIクライアント) | — | Atlas VS Code 拡張機能 | Atlas CLI | MongoDB Atlas (インフラ・ベクトルDB) |

---

## 3. エージェント (Agents) & 開発環境

AIと協調して開発を行うためのエージェントシステムや統合開発環境（IDE）のリンクと解説です。

### 主要ツール一覧
- **[Claude Code (Docs)](https://code.claude.com/docs/ja/overview)**: 
  - Anthropicが提供する自律型CLIエージェント。ターミナル上で動き、ファイルの検索、コードの書き換え、テストの実行までを自律的にこなします。
- **[OpenAI Codex / Developer Platform](https://openai.com/ja-JP/codex/)**: 
  - OpenAIが提供するコード生成APIやツールの紹介。GPT-5系列によって高精度なコード自動生成・レビューが可能です。
- **[Gemini CLI (geminicli.com)](https://geminicli.com/)**: 
  - Gemini 3.5 FlashのパワーをCLIで手軽に利用するためのツール群。
- **[Cursor (cursor.com)](https://cursor.com/ja)**: 
  - VS Codeをベースに開発された、AIネイティブな次世代コードエディタ。Gemini 3.1 Pro, Claude Sonnet 4.6など複数モデルを切り替え可能で、コードの差分インライン編集などが非常に強力です。
- **[Visual Studio Code (VS Code)](https://code.visualstudio.com/)**: 
  - デファクトスタンダードのコードエディタ。豊富なAI拡張機能（Marp, GitHub Copilot, Roo Cline, Gemini in VS Codeなど）を追加することで、強力なAI開発環境に変貌します。

---

## 4. デザイン (Design tools)

開発の初期段階でUI/UXのプロトタイプを素早く作成し、AIにコードへ落とし込ませるためのツールです。

- **Figma Make**: Figma上でプロンプトからデザイン要素を自動生成したり、静止画からコンポーネントを構築する機能。Gemini 3 Proとの連携により、高品質なプロトタイプを高速生成できます。
- **Stitch**: UIコンポーネントの視覚的な構築やコードへのエクスポートを容易にするモダンなツール。

---

## 5. MCP (Model Context Protocol)

**MCP (Model Context Protocol)** は、AIモデルが外部のデータソース、ツール、APIと安全かつ標準化された方法で接続・通信するためのオープンソースプロトコルです。2026年現在、主要エージェント（Claude, Gemini, OpenAI）のほぼすべてがMCPに対応し、外部ツール連携のデファクトスタンダードになっています。

- **[Chrome DevTools MCP](https://github.com/ChromeDevTools/chrome-devtools-mcp)**:
  - AIエージェントがChromeブラウザのDevToolsを直接操作できるようにするMCPサーバー。AI自身がブラウザのコンソールログを確認したり、DOM構造を解析してデバッグすることが可能になります。
- **[Figma MCP Catalog](https://www.figma.com/ja-jp/mcp-catalog/)**:
  - FigmaのデザインデータをAIがコンテキストとして正確に読み取るためのMCP連携。デザインの仕様やスタイルガイドを直接AIに参照させながらコーディングを進めることができます。
- **MCP Atlas** (MongoDB): マルチステップのMCPワークフロー実行に特化したインフラ基盤。Gemini 3.5 Flashが83.6%のスコアを記録するなど、エージェントとの親和性が高い。

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
