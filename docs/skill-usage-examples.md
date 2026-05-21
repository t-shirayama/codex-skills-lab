# Skill Usage Examples

このドキュメントは、初期Skill群をCodexで使うときの依頼例をまとめたものです。

各Skillについて、日本語の依頼、英語の依頼、少し曖昧な依頼を1つずつ載せています。曖昧な依頼でもSkillが発火しやすいか、またSkill本文の「使わない場面」で適切に境界を引けるかを確認するために使います。

## code-review

- 日本語: この差分を `code-review` skill を使ってレビューして。バグ、設計リスク、テスト不足を中心に見て。
- English: Use the `code-review` skill to review this PR and call out bugs, security issues, and missing tests.
- 曖昧: これ、マージ前にざっと危ないところ見てくれる？

## test-writer

- 日本語: このバグ修正に対して、再発防止テストを `test-writer` skill で考えて。
- English: Use the `test-writer` skill to propose unit and integration tests for this new feature.
- 曖昧: この実装、どんなテストを足せば安心かな？

## pr-summary

- 日本語: この差分から `pr-summary` skill でPR本文を作って。背景、変更点、確認方法を入れて。
- English: Use the `pr-summary` skill to summarize this PR for reviewers.
- 曖昧: レビューに出す説明文、いい感じにまとめて。

## release-notes

- 日本語: 今回の変更内容から `release-notes` skill でリリースノートを作って。
- English: Use the `release-notes` skill to draft release notes with breaking changes highlighted.
- 曖昧: 今回のリリースでユーザーに伝えることを整理して。

## docs-writer

- 日本語: 新機能の使い方を `docs-writer` skill でREADMEに追記する案を作って。
- English: Use the `docs-writer` skill to improve the setup documentation for developers.
- 曖昧: この手順、初めて触る人にも分かるように書き直して。

## bug-investigation

- 日本語: このエラーログと再現手順から `bug-investigation` skill で原因を調べて。
- English: Use the `bug-investigation` skill to investigate this stack trace and propose likely causes.
- 曖昧: なんでここで落ちてるのか一緒に切り分けて。

## refactor-plan

- 日本語: この大きな関数を壊さず整理するために、`refactor-plan` skill で段階的な計画を作って。
- English: Use the `refactor-plan` skill to plan a safe refactor before changing this module.
- 曖昧: このへん複雑だから、先に安全な整理順を考えたい。

## ci-failure-fix

- 日本語: このCIログを `ci-failure-fix` skill で読んで、原因とローカル再現手順を整理して。
- English: Use the `ci-failure-fix` skill to diagnose this CI failure and suggest a fix.
- 曖昧: CIが赤いんだけど、どこから見ればいい？

## skill-reviewer

- 日本語: 追加した `SKILL.md` を `skill-reviewer` skill でレビューして。descriptionと安全上の注意を重点的に見て。
- English: Use the `skill-reviewer` skill to review this SKILL.md for structure, triggers, and safety.
- 曖昧: このSkill、Codexでちゃんと使いやすいか見て。
