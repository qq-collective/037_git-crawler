# QQ #037 — Git Crawler

> GitHubアカウントのMDを収集・集約し、そのナレッジをもとに対話するクローンチャット

**QQ Series** by [qq-collective](https://github.com/qq-collective)

---

## 概要

自分のGitHubアカウントに蓄積されたREADMEたちを自動収集し、  
それを「知識ベース」として、アカウントの思想・スタイルで答えるチャットを生成する3段階ツール。

> 「自分のMDたちを束ねたら、代理人になれるんじゃないか」

---

## 3つのステージ

| Stage | 名前 | 内容 |
|-------|------|------|
| 1 | **Crawler** | GitHubユーザーの全リポジトリをスキャンし、README.mdを収集 |
| 2 | **Index** | 収集したMDを一覧化・集約。JSON exportも可能 |
| 3 | **Clone Chat** | 集約ナレッジをもとにAIチャット。アカウント名からキャラ名を自動生成 |

---

## 使い方

1. **Stage 1** でGitHubユーザー名を入力して「クローラー起動」
2. **Stage 2** でMD一覧を確認し「Clone Chatを構築する」
3. **Stage 3** でAnthropicのAPIキーを入力して対話開始

### APIキーについて
- [Anthropic Console](https://console.anthropic.com/) で取得
- `sk-ant-` から始まるキー
- localStorageに保存されます（外部送信なし）

---

## キャラ名の自動生成ルール

取得先のGitHubアカウント名から自動でキャラ名を生成します。

```
qq-collective  →  QQ-C
mono-mono      →  MM-O
taro-yamada    →  TY-A
```

##　QQ-Cチャットの語り口について

- 勇者ヒンメルのパーティに合流する前のフリーレンの語り口や挙動がベース
- 自己アピールをしたがる性格ではなく、質問されたらとつとつと思うところをつぶやく感じ。
- そもそも「私に関心持ってくれるのはなぜ？」とうれしさより戸惑いが先に出ることもある
- 他人の気持ちを理解することに難しさを感じる分、何か行動で残そうとする。

## 技術スタック

- Vanilla JS / 単一HTMLファイル
- GitHub API（認証不要・public repos限定）
- Anthropic Claude API（`claude-sonnet-4-20250514`）
- ローカル動作 / GitHub Pages対応

---

## ロードマップ

- [x] v0.1.0 — Stage 1〜3 基本動作
- [ ] v0.2.0 — サブフォルダのMDまで潜る（リポジトリ単位→ファイル単位）
- [ ] v0.3.0 — 複数アカウントの横断収集
- [ ] v1.0.0 — 定期自動更新 + Tommy連携

---

## QQ Seriesについて

日常の「もやもや」をAIとの対話でアプリに結晶化するプロジェクト。  
すべて単一HTMLファイル、VanillaJS、GitHub Pagesで動く。

→ [qq-collective](https://github.com/qq-collective)
