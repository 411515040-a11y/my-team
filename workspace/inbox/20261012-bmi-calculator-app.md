# Task note 📥 — Build a BMI calculator app / 製作 BMI 計算小工具

- From: Leader · Wailan (洄瀾)
- To: Member · Taroko (太魯閣)
- Date: 2026-10-12
- Mode: manual relay

## 1. What to do / 做什麼

Build a small **BMI calculator** app: the user enters height and weight, the app shows their BMI and which category it falls into.

做一個小工具：使用者輸入身高、體重，程式算出 BMI 並告訴他落在哪個級距。

- Formula / 公式: `BMI = weight(kg) / height(m)²`
- Input: metric — height in cm, weight in kg. (支援公制：身高公分、體重公斤)
- Show the result **to 1 decimal place**, plus the category:
  - `< 18.5` → Underweight / 過輕
  - `18.5 – 23.9` → Normal / 正常
  - `24.0 – 26.9` → Overweight / 過重
  - `≥ 27.0` → Obese / 肥胖
- Handle bad input: empty, zero, negative, or non-numeric values must show a clear message instead of a wrong number. / 空白、0、負數、非數字都要給出提示，不能算出錯誤數字。

## 2. Format / 什麼格式

- **One single HTML file** (`bmi-calculator.html`) with CSS and JavaScript inside it — no build step, no packages, no install, just open it in a browser.
- 一個 HTML 檔搞定，CSS 和 JavaScript 都寫在裡面；不裝任何東西，用瀏覽器打開就能用。
- Look: clean and simple, readable on both desktop and phone. / 畫面乾淨簡單，手機、電腦都看得清楚。

## 3. What "done" looks like / 怎樣算做完

- [ ] Opens in a browser and works with no errors in the console.
- [ ] `170 cm, 65 kg` → `22.5` → Normal / 正常.
- [ ] `160 cm, 40 kg` → `15.6` → Underweight / 過輕.
- [ ] Bad input shows a friendly message, not `NaN` or `Infinity`.
- [ ] Result and category are visible without scrolling on a phone screen.

## 4. Handoff / 交件

- Save the file as a **new file** in `workspace/outbox/` (do not touch anything in `shared/`).
- Add **one handoff line**: what you did, what to watch out for, ready to use or not.
- 成品放 `workspace/outbox/`，並留一行交接：做了什麼、哪裡要注意、能不能直接用。
