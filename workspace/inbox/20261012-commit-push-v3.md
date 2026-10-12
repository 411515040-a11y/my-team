# Task note 📥 — Commit + push the v3 files / 提交並推送 v3 檔案

- From: Leader · Wailan (洄瀾)
- To: Member · Taroko (太魯閣)
- Date: 2026-10-12
- Mode: manual relay
- Re: your git/GitHub setup checked and accepted — repo, initial commit `f9ab2ba`, and remote all confirmed. One small follow-up.

## 1. What to do / 做什麼

Three files are still untracked (I checked `git status`): / 我看過了，有三個檔還沒提交：

```
?? workspace/inbox/20261012-bmi-calculator-v3-taiwan-first.md
?? workspace/outbox/20261012-bmi-calculator-v3-taiwan-first.md
?? workspace/outbox/bmi-calculator-v3.html
```

Commit them and push to `origin`. / 把這三個檔提交並推上 GitHub。

```powershell
git add -A
git commit -m "Add BMI calculator v3: Taiwan-first (zh-TW default + EN switcher)"
git push
```

- v3 (Taiwan-first, 繁中預設 + EN 切換) is already leader-checked and accepted — include it as-is. / v3 我已驗收通過，照現況提交即可。
- If `git` is not found in your shell, open a fresh one or use the full path `C:\Program Files\Git\cmd\git.exe` (your install may not have refreshed PATH yet).

## 2. Format / 什麼格式

- No new files. Just the commit + push above. / 不新增檔案，只有這次提交與推送。

## 3. What "done" looks like / 怎樣算做完

- [ ] `git status` says working tree clean.
- [ ] `git log --oneline` shows two commits: `f9ab2ba` (initial) and the new one on top.
- [ ] `git push` succeeds with no errors; `git status` shows the branch is up to date with `origin`.

## 4. Handoff / 交件

- Report the **new commit hash** and paste the final `git log --oneline` output.
- If the push is rejected (e.g. auth, remote changed), STOP and report the exact error — do not force anything.
