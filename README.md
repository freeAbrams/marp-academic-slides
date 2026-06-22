# Marp Academic Slides

`marp-academic-slides` は、研究発表・講義・演習向けの Marp Markdown スライドを、落ち着いた学術スタイルで作成・改訂するための skill です。**Codex** と **Claude Code** の両方で利用できます。

## 目的

- アウトライン、講義計画、論文要旨、研究メモを Marp スライドへ変換する
- 主張型タイトル、簡潔な本文、表、コールアウトを使って説明しやすいデッキに整える
- 白背景・16:9・日本語対応フォントを前提に、編集しやすい Markdown テンプレートを提供する

## 構成

```text
.
├── SKILL.md                # Codex skill 本体
├── agents/
│   └── openai.yaml         # Codex UI 向け設定
├── assets/
│   └── marp-template.md
├── references/
│   └── style-guide.md
└── .claude/
    └── skills/
        └── marp-academic-slides/   # Claude Code skill（自己完結）
            ├── SKILL.md
            ├── assets/marp-template.md
            └── references/style-guide.md
```

- `SKILL.md`: skill のトリガー条件と基本ワークフロー
- `agents/openai.yaml`: Codex UI 向けの表示名、短い説明、既定プロンプト
- `assets/marp-template.md`: 新規デッキ作成時に使う Marp テンプレート
- `references/style-guide.md`: デザイン、文章、QA の詳細ガイド
- `.claude/skills/marp-academic-slides/`: Claude Code が読み込む skill。`SKILL.md` と各リソースを自己完結で同梱

## 使い方

### Codex

Codex で次のように依頼します。

```text
Use $marp-academic-slides to create a clean academic Marp slide deck from my outline.
```

既存デッキを改訂する場合は、対象ファイルと目的を指定します。

```text
Use $marp-academic-slides to revise this Marp deck for a 10-minute research talk.
```

### Claude Code

このリポジトリ内では `.claude/skills/marp-academic-slides/` が自動的に読み込まれます。アウトラインや論文要旨を渡して、アカデミックな Marp デッキの作成・改訂を依頼してください。

```text
アウトラインからアカデミックな Marp スライドを作って
```

どのプロジェクトでも使いたい場合は、skill フォルダをユーザー領域へコピーします。

```bash
cp -R .claude/skills/marp-academic-slides ~/.claude/skills/
```

## 開発メモ

skill を更新したら、必要に応じて次を確認します。

```bash
python /path/to/quick_validate.py /path/to/marp-academic-slides
```

Marp CLI が利用できる環境では、生成したデッキを PDF または HTML にレンダリングし、文字あふれ、長すぎる URL、根拠のない主張、CSS の崩れを確認します。
