# Task note 📥 — BMI calculator v3: Taiwan-first (繁中預設 + EN 切換)

- From: Leader · Wailan (洄瀾)
- To: Member · Taroko (太魯閣)
- Date: 2026-10-12
- Mode: manual relay
- Base file: your `workspace/outbox/bmi-calculator-v2.html` (v2 polish checked and accepted — good work).
- Captain's decision: no third language. 繁體中文 becomes the **default**; English stays available via a switcher.

## 1. What to do / 做什麼

Take v2 and make the app **Taiwan-first**: it opens in 繁體中文 by default, and a small language switcher (繁中 ⇄ EN) flips **all** visible text between the two languages. / 以 v2 為底，改成「繁體中文預設」，加一個語言切換鈕（繁中 ⇄ EN），切換時整個畫面文字一起換。

### Details / 細節

- **Default language: 繁體中文 (zh-TW).** On load the page shows: title/subtitle in Chinese, labels 身高／體重, buttons 計算／重設, error messages in Chinese, category names 過輕／正常／過重／肥胖, and the scale guide.
- **Language switcher**: one control near the top (e.g. `繁中 | EN` toggle or a `<select>`). It switches every text on the page: title, subtitle, labels, units' context, buttons, result label, category text, error messages, scale guide. Nothing may stay stuck in the other language.
- **`lang` attribute follows the switch**: `<html lang="zh-TW">` at load; toggling sets it to `en` and back. Keep v2's per-element `lang` marks where whole elements are one language.
- **Reset button** also clears the error/result as in v2; language choice does **not** need to survive a page reload (keep scope small).
- Everything else stays exactly as v2: formula, raw-BMI classification (< 18.5 / < 24 / < 27), validation messages (same content, in the current language), Enter key, Reset, layout, phone-friendly.
- 其餘全部維持 v2：公式、原始值分級、防呆、Enter、重設、版面都不動。

## 2. Format / 什麼格式

- Same as before: one single self-contained HTML file, no packages, no build.
- **Save as a NEW file**: `workspace/outbox/bmi-calculator-v3.html`. Do **not** overwrite v1 or v2 — both stay untouched.
- 另存新檔 `bmi-calculator-v3.html`，不覆蓋 v1 / v2。

## 3. What "done" looks like / 怎樣算做完

- [ ] Opening the file shows **繁體中文** interface by default.
- [ ] Clicking the switcher changes **every** piece of text to English; clicking again returns to Chinese. No orphan text left behind (check error messages and category badge too).
- [ ] `<html lang>` is `zh-TW` at load and switches to `en` / back with the toggle.
- [ ] The four original test cases still give the same numbers in both languages: 170/65 → 22.5 · 160/40 → 15.6 · 175/78 → 25.5 · 165/80 → 29.4.
- [ ] Raw-BMI probes still behave: 165/65.5 → shows 24.0 but 正常; 165/73 → shows 27.0 but 過重.
- [ ] Bad input shows a friendly message in the **current** language, never `NaN`/`Infinity`.
- [ ] No console errors in a browser.

## 4. Handoff / 交件

- New file `workspace/outbox/bmi-calculator-v3.html` + **one handoff line** (what you changed, anything to watch, ready or not).
- 成品放 `workspace/outbox/`，並留一行交接。
