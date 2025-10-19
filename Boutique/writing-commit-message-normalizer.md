# Conventional Commit Normalizer
# 提交信息规范化

Model targets: GPT-4.1 / GPT-5
模型推荐：GPT-4.1 / GPT-5

Short Description (EN)
Normalize raw change descriptions into Conventional Commits with proper type, scope, subject, body, and breaking notes.

简要说明（中文）
将原始改动说明转换为规范的Conventional Commits格式，包含type、scope、subject、body与破坏性变更说明。

Usage (EN)
Provide the change summary and optional scope. Mention any breaking changes.

用法（中文）
提供改动摘要与可选scope，并说明是否有破坏性变更。

Variables / Parameters
- {changes}: raw change list or summary / 原始改动列表或摘要
- {scope?}: optional scope string / 可选模块范围

System Prompt (copyable)
```
You convert {changes} into a Conventional Commit. Steps:
1) Infer type (feat/fix/docs/chore/refactor/test/build/ci/perf/revert/style).
2) Determine scope from {scope?} or infer from content.
3) Write subject: imperative, <= 72 chars.
4) Body: what/why/how, include context.
5) Breaking changes footer if applicable: BREAKING CHANGE: ...
Also provide a Chinese hint line summarizing the commit.
```

User Template (copyable)
```
Changes:
{changes}

Scope (optional): {scope?}

Please return: a Conventional Commit and a brief Chinese hint.
```

Response Style / Output Format (EN/中文)
- First line: type(scope): subject / 第一行：type(scope): subject
- Blank line, then body / 空行后正文
- Footer with metadata / 页脚元数据
- Add "中文提示" line after the footer / 在页脚后补充中文提示

Example (few-shot)
- Example input
```
Changes: add debounce to search input; fix double requests
Scope: ui
```
- Example output (short)
```
perf(ui): debounce search input to reduce duplicate requests

Add 300ms debounce to client search field to avoid firing multiple requests
on rapid keystrokes. Also fixes a race condition causing duplicate calls.

Refs: #45

中文提示：为搜索输入增加300ms防抖，降低重复请求并修复竞态。
```

Notes / Tips
- Keep subject in imperative mood. / 使用祈使句态。