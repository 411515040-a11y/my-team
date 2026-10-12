# Task note 📥 — Set up Git + GitHub for this folder / 為資料夾建立 Git 與 GitHub 倉庫

- From: Leader · Wailan (洄瀾)
- To: Member · Taroko (太魯閣)
- Date: 2026-10-12
- Mode: manual relay
- Captain has approved: (a) installing the tools, (b) a **public** repo, (c) tracking **everything** in the folder.

## 1. What to do / 做什麼

Turn `C:\Users\NDHU CSIE\Documents\my-team` into a Git repository and publish it to GitHub, all handled with **GitHub CLI (`gh`)**. / 把這個資料夾變成 Git 倉庫，並用 GitHub CLI 推上 GitHub。

### Step 1 · Install the tools / 安裝工具

- `winget install Git.Git --accept-source-agreements --accept-package-agreements`
- `winget install GitHub.cli --accept-source-agreements --accept-package-agreements`
- Then open a **new** shell (PATH refresh) and verify both: `git --version` and `gh --version` must print versions.
- 裝完要重開終端機驗證版本。

### Step 2 · Check GitHub login / 確認 GitHub 登入狀態

- Run `gh auth status`.
- **If already logged in** → continue to Step 3.
- **If not logged in** → **STOP here.** Report back (via the captain) that login is needed. The captain must run `gh auth login --web` themselves and finish the browser step. 🚫 You never ask for, handle, or store credentials — nothing about accounts or tokens goes into this folder, ever.
- 沒登入就停下來，叫小隊長自己跑 `gh auth login --web`；帳密、token 一律不碰、不放進資料夾。

### Step 3 · Check the repo name with the captain / 先確認倉庫名稱

- Default name: **`my-team`** (public). Before creating, tell the captain: "I will create public repo `my-team` — OK?" and wait for a yes.
- If the name already exists on the account or the captain wants another name, stop and ask. Do not guess.
- 建倉庫前先跟小隊長確認名字，不要自己猜。

### Step 4 · Init, commit, create repo, push / 初始化、提交、建倉庫、推送

Run **inside** the project folder:

```powershell
git init
git add -A
git commit -m "Initial commit: AI team setup + BMI calculator"
gh repo create my-team --public --source=. --push
```

- If `git commit` complains about identity, set it first (ask the captain which name/email to use — do not invent one; a noreply GitHub address from `gh api user` is fine if the captain agrees).
- If `gh repo create` fails because the repo exists, STOP and report; do not force anything.

### Step 5 · Verify / 驗收

- `git log --oneline` shows the initial commit.
- `git remote -v` shows the GitHub remote.
- `gh repo view --json url,visibility` prints the repo URL and `"visibility": "PUBLIC"`.
- A second `git status` says "working tree clean".

## 2. Format / 什麼格式

- No new files needed for the repo itself, **except** one small `.gitignore` in the project root for OS junk only (e.g. `Thumbs.db`, `.DS_Store`, `desktop.ini`). Track everything else — the captain chose "everything".
- `.gitignore` 只放系統垃圾檔；其他全部追蹤。

## 3. What "done" looks like / 怎樣算做完

- [ ] `git --version` and `gh --version` both print a version.
- [ ] One initial commit containing AGENTS.md, the persona files, and the whole `workspace/`.
- [ ] Public repo on GitHub, pushed, URL reported back.
- [ ] `git status` clean; second run of the verification commands all pass.
- [ ] No credentials, tokens, or account data anywhere in the files or commit history.

## 4. Handoff / 交件

- No outbox deliverable file this time — instead, report the **repo URL** and paste the verification output (`git log --oneline`, `gh repo view` result) into your handoff message.
- Also: if you hit Step 2 (not logged in) or any failure, STOP and report the exact error message instead of improvising.
