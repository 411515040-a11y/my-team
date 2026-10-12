# Task note 📥 — Polish the BMI calculator (v2) / BMI 小工具細部修正（v2）

- From: Leader · Wailan (洄瀾)
- To: Member · Taroko (太魯閣)
- Date: 2026-10-12
- Mode: manual relay
- Re: your `workspace/outbox/bmi-calculator.html` — accepted, good work. This is a small polish round, three items only.

## 1. What to do / 做什麼

Keep the app exactly as it is; change only these three spots. / 維持原本功能，只改下面三個地方。

### (1) Classify on the raw BMI, not the rounded one / 分級改用「四捨五入前」的數值

- Now: the category is decided from the *rounded* value, so raw BMI `23.96` shows `24.0 → 過重`, even though it is still below 24.
- Change: compare the **raw** BMI against the cut-offs (`< 18.5`, `< 24`, `< 27`), and keep **displaying** the value rounded to 1 decimal place.
- 改成分級用原始值判斷（< 18.5 / < 24 / < 27），顯示仍然四捨五入到小數第一位。

### (2) Fix the page language / 修正頁面語言宣告

- Change `<html lang="zh-TW">` to `<html lang="en">`.
- Mark the Chinese text as Chinese: put `lang="zh-TW"` on the elements that contain Chinese (subtitle, category text, scale-guide labels, error messages). Bilingual sentences inside one element (e.g. `Underweight / 過輕`) may stay as-is.
- 主語言改 `en`；含中文的元素加上 `lang="zh-TW"`。

### (3) Remove the dead error path / 刪掉永遠不會觸發的錯誤分支

- The `isNaN(...)` / "請輸入有效數字" branch can never fire (number inputs already block letters). Delete it so the code says only what it really does.
- 刪掉那段永遠不會執行的 `isNaN` 錯誤訊息，程式碼才誠實。

## 2. Format / 什麼格式

- Same as before: one single HTML file, no build step, no packages.
- **Save as a NEW file**: `workspace/outbox/bmi-calculator-v2.html`. Do **not** overwrite the original `bmi-calculator.html` — v1 stays untouched.
- 另存新檔 `bmi-calculator-v2.html`，**不要覆蓋**第一版。

## 3. What "done" looks like / 怎樣算做完

- [ ] Raw BMI `23.96` (e.g. 165 cm, 65.5 kg) → displays `24.0` but category is **正常 / Normal**.
- [ ] Raw BMI `26.95` (e.g. 165 cm, 73 kg) → displays `27.0` but category is **過重 / Overweight**.
- [ ] The four original test cases still give the same results: 170/65 → 22.5 正常 · 160/40 → 15.6 過輕 · 175/78 → 25.5 過重 · 165/80 → 29.4 肥胖.
- [ ] Bad input still shows friendly messages, never `NaN`/`Infinity`.
- [ ] `<html lang="en">`; Chinese elements carry `lang="zh-TW"`; no `isNaN` branch left in the code.
- [ ] No console errors when opening in a browser.

## 4. Handoff / 交件

- New file `workspace/outbox/bmi-calculator-v2.html` + **one handoff line** (what you changed, anything to watch, ready or not).
- 成品放 `workspace/outbox/`，並留一行交接。
