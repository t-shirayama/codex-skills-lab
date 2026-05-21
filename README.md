# codex-skills-lab

GitHub description:

```text
Codex向けの実用Agent Skillsを集めて育てるリポジトリ
```

## 目的

このリポジトリは、Codexで日常的な開発作業に使うAgent Skillsを整理し、実際の作業で使いやすい形に改善していくためのものです。

ここでは、外部サービス連携やAPI連携を前提にしたSkillではなく、コードレビュー、テスト作成、ドキュメント整備、バグ調査など、開発作業で頻繁に使うinstruction-onlyのSkillを扱います。

## Skillとは

Skillは、Codexに特定の作業を安定して実行させるための手順書です。目的、使う場面、入力確認、手順、安全上の注意、出力形式を明確にすることで、同じ種類の作業を再現性高く進められるようにします。

## 使い方

このリポジトリのSkillは、CodexのSkillディレクトリに配置して利用することを想定しています。

例:

```bash
mkdir -p ~/.codex/skills
cp -r skills/code-review ~/.codex/skills/
```

利用時は、Codexに次のように依頼します。

```text
この差分を code-review skill を使ってレビューして
```

依頼は日本語でも英語でも構いません。例: `review this PR`、`write tests`、`summarize this PR`。

## 初期Skill一覧

| Skill名 | 用途 | 想定する利用場面 | 注意点 |
| --- | --- | --- | --- |
| `code-review` | コード差分やPull Requestをレビューする | PRレビュー、git diff確認、実装後のセルフレビュー | バグ、設計リスク、保守性、セキュリティ、テスト不足を優先して見る |
| `test-writer` | 実装内容に対するテスト方針を作る | 新機能、バグ修正、テスト不足の確認 | 依存関係追加やE2Eテストのコストを明示する |
| `pr-summary` | 変更差分からPull Request本文を作る | PR説明文、背景、確認方法、影響範囲の整理 | 実装していない内容を含めない |
| `release-notes` | 変更内容からリリースノートを作る | リリース前の変更点整理 | breaking changesを明示する |
| `docs-writer` | 開発ドキュメントを作成・改善する | README、使い方、設計メモ、運用手順 | 秘密情報や未確定仕様を書かない |
| `bug-investigation` | バグ報告やログから原因調査を進める | 不具合調査、再現条件整理、修正方針作成 | 推測と確認済み事実を分ける |
| `refactor-plan` | 既存コードを壊さず整理する計画を作る | 大きな変更前、複雑な関数分割、責務分離 | 仕様変更を混ぜない |
| `ci-failure-fix` | CI失敗ログから原因と修正方針を整理する | テスト、lint、型チェック、ビルド失敗 | ローカル再現手順と影響範囲を確認する |
| `skill-reviewer` | `SKILL.md` の品質をレビューする | Skill追加時、既存Skill改善時 | descriptionの具体性と安全性を重点確認する |

## ディレクトリ構成

```text
codex-skills-lab/
  README.md
  AGENTS.md
  LICENSE
  NOTICE.md
  skills/
    code-review/
      SKILL.md
    test-writer/
      SKILL.md
    pr-summary/
      SKILL.md
    release-notes/
      SKILL.md
    docs-writer/
      SKILL.md
    bug-investigation/
      SKILL.md
    refactor-plan/
      SKILL.md
    ci-failure-fix/
      SKILL.md
    skill-reviewer/
      SKILL.md
  templates/
    skill-template/
      SKILL.md
  docs/
    dogfooding-notes.md
    skill-usage-examples.md
    skill-review-checklist.md
    license-policy.md
```

## 利用例

Codexへ依頼するときの具体例は [docs/skill-usage-examples.md](docs/skill-usage-examples.md) にまとめています。

実際にSkillを試した結果や改善メモは [docs/dogfooding-notes.md](docs/dogfooding-notes.md) に記録します。

## Skill作成方針

- 1つのSkillは、1つの明確な開発作業に集中させます。
- Skill名、ディレクトリ名、frontmatterの `name` は英語のkebab-caseにします。
- 各 `SKILL.md` にはYAML frontmatterを必ず含め、`name` と `description` を書きます。
- `description` には、CodexがいつそのSkillを使うべきか分かる具体的なトリガー語を含めます。
- 本文は「目的」「使う場面」「使わない場面」「確認する入力」「手順」「安全上の注意」「出力形式」を基本構成にします。
- 手順は番号付きリストで書きます。
- 破壊的変更、依存関係追加、仕様変更、テスト不足、秘密情報の扱いには必ず注意書きを入れます。
- 初期構成では `scripts/` を作らず、すべてinstruction-onlyのSkillにします。
- Skillを追加・変更した場合は、必要に応じてREADMEの一覧も更新します。
- 出力形式は日本語を基本にしますが、リリースノートなど用途に応じて一般的な英語見出しを使う場合があります。

## ライセンスと出典管理

このリポジトリ自体はMIT Licenseを想定しています。

他のリポジトリや公開Skillを参考にする場合は、ライセンスを必ず確認してください。本文を丸ごとコピーせず、自分の言葉で書き直し、必要な帰属表示を `NOTICE.md` または該当Skill内に記載します。ライセンス不明のものは取り込みません。
