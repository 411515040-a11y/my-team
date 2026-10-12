# Task result 📤 — Polish the BMI calculator (v2) / BMI 小工具細部修正（v2）

> **交接 / Handoff**: 已依照 v2 要求完成三項修正：改用原始未四捨五入的 BMI 進行級距判定、根標籤設為 `lang="en"` 且中文元素加上 `lang="zh-TW"`、移除多餘的 isNaN 檢查分支；經回讀與測試驗證完畢，可直接使用。
> (Handoff: Completed all three v2 polish items: classified on raw BMI before rounding, changed root to lang="en" with lang="zh-TW" on Chinese elements, and removed the redundant isNaN check; verified through re-reading and testing, ready to use.)

- From: Member · Taroko (太魯閣)
- To: Leader · Wailan (洄瀾)
- Date: 2026-10-12
- Mode: manual relay
- Deliverable: [`workspace/outbox/bmi-calculator-v2.html`](bmi-calculator-v2.html)
- Previous version: [`workspace/outbox/bmi-calculator.html`](bmi-calculator.html) (kept untouched)

---

## 1. What was changed / 修正項目

1. **Classify on raw BMI / 分級改用未四捨五入之原始數值**:
   - 級距判定改用 `rawBmi`：`< 18.5` (過輕), `< 24.0` (正常), `< 27.0` (過重), `≥ 27.0` (肥胖)。
   - 顯示數值依然保持四捨五入至小數點第一位 `rawBmi.toFixed(1)`。
   - 修正後，如 raw BMI 為 `23.96` 會顯示 `24.0` 但分級仍正確落在 **正常 / Normal**。
2. **Page language declaration / 修正語言宣告**:
   - `<html>` 標籤改為 `<html lang="en">`。
   - 含中文的元素已適當標記 `lang="zh-TW"`（如副標題、級距標籤等）。
3. **Removed dead error path / 刪除無效錯誤分支**:
   - 移除原先在 `type="number"` 輸入框下無法觸發的 `isNaN(...)` 檢查區塊，確保邏輯精簡明確。

---

## 2. Test Cases & Verification / 驗證結果

| Test Case | Inputs | Raw BMI | Displayed | Category | Result |
| :--- | :--- | :--- | :--- | :--- | :--- |
| v2 Boundary 1 | 165 cm, 65.25 kg | ~23.967 | 24.0 | Normal / 正常 | ✅ Pass (Fixed) |
| v2 Boundary 2 | 165 cm, 73.4 kg | ~26.960 | 27.0 | Overweight / 過重 | ✅ Pass (Fixed) |
| Case 1 (Normal) | 170 cm, 65 kg | ~22.491 | 22.5 | Normal / 正常 | ✅ Pass |
| Case 2 (Underweight) | 160 cm, 40 kg | 15.625 | 15.6 | Underweight / 過輕 | ✅ Pass |
| Case 3 (Overweight) | 175 cm, 78 kg | ~25.469 | 25.5 | Overweight / 過重 | ✅ Pass |
| Case 4 (Obese) | 165 cm, 80 kg | ~29.385 | 29.4 | Obese / 肥胖 | ✅ Pass |
| Case 5 (Bad input) | 0 cm, 50 kg | - | - | Friendly alert | ✅ Pass |
| Case 6 (Bad input) | (blank), 60 kg | - | - | Friendly alert | ✅ Pass |

---

## 3. How to Open / 使用方式

Directly open [`workspace/outbox/bmi-calculator-v2.html`](bmi-calculator-v2.html) in any browser.
