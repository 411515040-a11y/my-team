# Task result 📤 — BMI calculator v3: Taiwan-first (繁中預設 + EN 切換)

> **交接 / Handoff**: 已完成 v3「繁體中文預設」與雙語即時切換功能（繁中 ⇄ EN）；包含頁面標題、標籤、按鈕、結果、分級徽章、錯誤提示與對照表皆無縫連動切換，`<html lang>` 同步更新；經完整測試驗證，可直接在瀏覽器使用。
> (Handoff: Completed v3 Taiwan-first design with Traditional Chinese default and dynamic 繁中 ⇄ EN switcher; all UI text, badges, errors, and scale guides sync seamlessly along with `<html lang>`; thoroughly verified and ready to use.)

- From: Member · Taroko (太魯閣)
- To: Leader · Wailan (洄瀾)
- Date: 2026-10-12
- Mode: manual relay
- Deliverable: [`workspace/outbox/bmi-calculator-v3.html`](bmi-calculator-v3.html)
- Prior versions: [`workspace/outbox/bmi-calculator-v2.html`](bmi-calculator-v2.html), [`workspace/outbox/bmi-calculator.html`](bmi-calculator.html) (both kept untouched)

---

## 1. What was done / 成果說明

1. **Taiwan-first 預設繁體中文**:
   - 開啟時預設為繁體中文介面，`<html lang="zh-TW">`。
   - 所有顯示元件（標題、副標題、欄位名稱「身高／體重」、提示文字、按鈕「計算／重設」、BMI 結果說明、分級標籤與分級對照表）均預設呈現繁體中文。
2. **雙語切換開關 (Language Switcher)**:
   - 頂部設置俐落的「繁中 | EN」膠囊切換鈕。
   - 點擊時同步切換全站所有文字與 `<html lang>` 屬性（`zh-TW` ⇄ `en`）。
   - 若畫面上已存在錯誤訊息或計算結果徽章，切換語言時會立即同步翻譯，無任何殘留文字。
3. **繼承 v2 精確規格**:
   - 維持原始 BMI 數值進行級距判定（`< 18.5`, `< 24.0`, `< 27.0`, `≥ 27.0`）。
   - 顯示數值四捨五入至小數點第 1 位。
   - 完整防呆驗證、Enter 鍵快捷送出、手機響應式排版。

---

## 2. Test Cases & Verification / 驗證結果

| Test Case | Inputs | Raw BMI | Displayed | 繁中 Category | EN Category | Result |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| Case 1 (Normal) | 170 cm, 65 kg | ~22.491 | 22.5 | 正常 | Normal | ✅ Pass |
| Case 2 (Underweight) | 160 cm, 40 kg | 15.625 | 15.6 | 過輕 | Underweight | ✅ Pass |
| Case 3 (Overweight) | 175 cm, 78 kg | ~25.469 | 25.5 | 過重 | Overweight | ✅ Pass |
| Case 4 (Obese) | 165 cm, 80 kg | ~29.385 | 29.4 | 肥胖 | Obese | ✅ Pass |
| Raw-BMI Probe 1 | 165 cm, 65.25 kg | ~23.967 | 24.0 | 正常 | Normal | ✅ Pass |
| Raw-BMI Probe 2 | 165 cm, 73.4 kg | ~26.960 | 27.0 | 過重 | Overweight | ✅ Pass |
| Switcher Toggle | - | - | - | 完整雙語連動 | Seamless sync | ✅ Pass |
| Error Message Sync | 0 cm, 0 kg | - | - | 顯示繁中錯誤 | 顯示英文錯誤 | ✅ Pass |

---

## 3. How to Open / 使用方式

Directly open [`workspace/outbox/bmi-calculator-v3.html`](bmi-calculator-v3.html) in any web browser.
