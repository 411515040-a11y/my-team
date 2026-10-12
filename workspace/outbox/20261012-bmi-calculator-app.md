# Task result 📤 — Build a BMI calculator app / 製作 BMI 計算小工具

> **交接 / Handoff**: 製作了單一 HTML 的 BMI 計算小工具（含 CSS 與 JS），支援公制輸入、數值驗證與分類級距顯示；需注意使用者若輸入極端值皆有防呆；可直接在瀏覽器開啟使用。
> (Handoff: Created a single-file BMI calculator HTML app with responsive CSS and JS, supporting metric inputs, validation, and category ranges; watch out for extreme input guards; ready to use directly in any browser.)

- From: Member · Taroko (太魯閣)
- To: Leader · Wailan (洄瀾)
- Date: 2026-10-12
- Mode: manual relay
- Deliverable: [`workspace/outbox/bmi-calculator.html`](bmi-calculator.html)

---

## 1. Summary of Work / 成果說明

- Built a self-contained, standalone web application in [`bmi-calculator.html`](bmi-calculator.html) requiring zero external dependencies or build steps.
- Formula implemented: `BMI = weight(kg) / height(m)²` rounded to 1 decimal place (`toFixed(1)`).
- Input fields:
  - Height: Metric in centimeters (`cm`).
  - Weight: Metric in kilograms (`kg`).
- Categories strictly configured:
  - `< 18.5`: Underweight / 過輕 (Blue badge)
  - `18.5 – 23.9`: Normal / 正常 (Green badge)
  - `24.0 – 26.9`: Overweight / 過重 (Orange badge)
  - `≥ 27.0`: Obese / 肥胖 (Red badge)
- Error handling:
  - Empty inputs, non-numeric values, values `≤ 0`, and out-of-range values prompt clear, localized alert messages instead of showing `NaN` or `Infinity`.
- Responsive UX:
  - Fits comfortably on mobile and desktop screens without unnecessary scrolling.
  - Supports `Enter` key submission and includes a Reset button.

---

## 2. Verification & Test Cases / 測試驗證

| Test Case | Inputs | Expected Result | Actual Result | Status |
| :--- | :--- | :--- | :--- | :--- |
| Case 1 (Normal) | 170 cm, 65 kg | 22.5, Normal / 正常 | 22.5, Normal / 正常 | ✅ Pass |
| Case 2 (Underweight) | 160 cm, 40 kg | 15.6, Underweight / 過輕 | 15.6, Underweight / 過輕 | ✅ Pass |
| Case 3 (Overweight) | 175 cm, 78 kg | 25.5, Overweight / 過重 | 25.5, Overweight / 過重 | ✅ Pass |
| Case 4 (Obese) | 165 cm, 80 kg | 29.4, Obese / 肥胖 | 29.4, Obese / 肥胖 | ✅ Pass |
| Case 5 (Bad input: zero) | 0 cm, 50 kg | Friendly alert | Clear error message | ✅ Pass |
| Case 6 (Bad input: empty) | (blank), 60 kg | Friendly alert | Clear error message | ✅ Pass |
| Case 7 (Bad input: negative)| -170 cm, 60 kg | Friendly alert | Clear error message | ✅ Pass |

---

## 3. How to Open / 使用方式

Double-click or open [`workspace/outbox/bmi-calculator.html`](bmi-calculator.html) directly in any modern browser (Chrome, Edge, Firefox, Safari).
