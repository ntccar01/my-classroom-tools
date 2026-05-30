# my-classroom-tools — Handoff for New Codex Sessions

## Purpose

This repository is the classroom tools master project for building teacher-facing and student-facing web tools.

The user teaches vocational high school automotive courses and vocational high school math for grades 10-12. Many students are low-achieving or low-motivation learners, so tool design should favor scaffolding, short tasks, immediate feedback, Shida-style learning activities, and interactive web experiences.

## How To Resume

When starting a new Codex conversation, ask Codex to read:

1. `G:\我的雲端硬碟\my-classroom-tools\CLAUDE.md`
2. `G:\我的雲端硬碟\my-classroom-tools\HANDOFF.md`
3. `G:\我的雲端硬碟\secondbrain\my-classroom-tools\工作筆記.md`

Suggested prompt:

```text
開工，專案是 G:\我的雲端硬碟\my-classroom-tools。
請先讀 CLAUDE.md、HANDOFF.md，以及 Obsidian 工作筆記，告訴我上次做到哪、目前 git 狀態、接下來建議做什麼。
```

## Important Paths

| Item | Path |
|---|---|
| Main project folder | `G:\我的雲端硬碟\my-classroom-tools` |
| Obsidian vault | `G:\我的雲端硬碟\secondbrain` |
| Obsidian project note | `G:\我的雲端硬碟\secondbrain\my-classroom-tools\工作筆記.md` |
| First tool folder | `G:\我的雲端硬碟\my-classroom-tools\tools\coordinate-hunter` |
| Startup skill | `C:\Users\User\.claude-skills\startup\SKILL.md` |
| Shutdown skill | `C:\Users\User\.claude-skills\shutdown\SKILL.md` |

## GitHub

- Account: `ntccar01`
- Repository: `https://github.com/ntccar01/my-classroom-tools`
- Visibility: public
- Default branch: `main`
- Git note for Google Drive repo:

```powershell
git config windows.appendAtomically false
```

## Connected Services

### Firebase

- Firebase project display name: `my-teaching-tools`
- Firebase project ID: `my-teaching-tools-92611`
- Firestore database: `(default)`
- Firestore location: `asia-east1`
- Firebase MCP is enabled in Codex:

```text
firebase -> npx.cmd -y firebase-tools@latest mcp
```

Current Firestore rules are conservative: all public frontend reads/writes are closed, including `wordcloud_words`. Open specific collections only when building a tool, and avoid storing real student personal data.

### Supabase

- Supabase project name: `my-teaching-tools`
- Project ID: `flkbnsxauznqisvriuso`
- Status at setup: `ACTIVE_HEALTHY`
- Supabase MCP is enabled using OAuth:

```text
supabase -> https://mcp.supabase.com/mcp
```

A table exists:

```text
public.student_learning_records
```

It is designed for anonymized learning records using `student_code`, not real student names.

### Obsidian

- MCP server: `obsidian`
- Command: `C:\Users\User\AppData\Roaming\npm\mcpvault.cmd`
- Vault path: `G:\我的雲端硬碟\secondbrain`
- Web Clipper has been configured and tested.
- Clippings folder: `G:\我的雲端硬碟\secondbrain\Clippings`

### NotebookLM

- MCP server: `notebooklm-mcp`
- Google account used during setup: `lin1102@gm.ntc.edu.tw`
- NotebookLM CLI `nlm` is installed and authenticated.

## Skills And Workflow

Two local skill files were installed:

- Startup: `C:\Users\User\.claude-skills\startup\SKILL.md`
- Shutdown: `C:\Users\User\.claude-skills\shutdown\SKILL.md`

Expected workflow:

```text
開工
```

Codex should read the project note, inspect git status, and suggest next steps.

```text
收工
```

Codex should summarize work, update Obsidian project note, commit, and push.

SessionEnd hook was intentionally not enabled because automatic commit/push on close can accidentally publish unfinished or sensitive files.

## Current Status

Completed:

- Environment setup completed.
- GitHub connected.
- NotebookLM connected.
- Obsidian second brain connected.
- Supabase connected and tested.
- Firebase connected and tested.
- Classroom tools master folder created.
- GitHub public repo created and pushed.
- Obsidian project work note created.
- Startup/shutdown skill files installed.
- First tool folder created: `tools/coordinate-hunter`.

Not yet implemented:

- The first actual tool, Coordinate Hunter, has not been built yet.
- GitHub Pages for this repository has not yet been configured for a finished tool.
- SessionEnd hook has not been installed.

## Recommended Next Step

Build the first tool:

```text
請做一個直角座標練習遊戲，叫「座標獵人」。
功能：
- 11x11 整數格點，xy 從 -5 到 5
- 隨機產生 10 個隱藏座標
- 學生輸入猜測，例如 2,-3，命中就在棋盤上標記、計分 +1
- 60 秒倒數計時
- 結束顯示得分，滿分 10 分
- 重新開始按鈕
風格：黑底白字、橘色強調，像粉筆寫黑板。
完成後預覽給我看。
```

Build it in:

```text
G:\我的雲端硬碟\my-classroom-tools\tools\coordinate-hunter
```

## Safety Rules

- Never commit `.claude/`, `.env`, credentials, service role keys, or tokens.
- Use anonymized student data only: class code, seat number, or random student code.
- For Firebase, do not use broad `allow read, write: if true` rules for real student data.
- For Supabase, keep RLS conservative until a real frontend auth strategy is chosen.
- Before pushing, run `git status --short` and inspect changed files.

## Useful Commands

```powershell
cd "G:\我的雲端硬碟\my-classroom-tools"
git status --short
git log --oneline -5
git push origin main
codex mcp list
npx.cmd -y firebase-tools@latest projects:list
```
