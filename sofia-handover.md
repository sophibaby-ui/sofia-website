# Sofia 蘇菲療癒轉化 — 網站專案說明

## 專案概述
這是一個用 **Vite + React 18** 建立的單頁應用（SPA），全繁體中文，服務於情緒陪伴品牌「Sofia 蘇菲療癒轉化」。

## 技術規格
- 框架：React 18（JSX）
- 打包工具：Vite 5
- 樣式：純 CSS-in-JS（inline style）+ CSS 變數
- 字型：Google Fonts（Cormorant Garamond、Noto Serif TC、Noto Sans TC）
- 無外部 UI 套件
- 單一檔案架構：所有程式碼都在 `src/App.jsx`

## 專案結構
```
sofia-project/
├── index.html
├── package.json
├── vite.config.js
├── public/
│   └── favicon.svg
└── src/
    ├── main.jsx        ← React 進入點
    └── App.jsx         ← 所有頁面與元件（主程式）
```

## 啟動方式
```bash
npm install
npm run dev
# 瀏覽器開啟 http://localhost:5173
```

## 8 個頁面（路由）
| 路由 key | 頁面名稱 | 說明 |
|----------|---------|------|
| home | 首頁 | Hero、三核心、服務層次、見證、Email 訂閱 |
| about | About Sofia | 品牌自述、工作方式、適合對象 |
| num | 生命數字 | 陽曆+農曆主命數、流年數、關係數計算器 |
| mem | 位置練習室 | 月費/年費會員，NT$2,980/月 |
| adv | 進階解讀 | 深入模式解讀服務 |
| deep | 深度陪跑 | 90 天一對一陪伴計畫 |
| art | 觀點文章 | 6 篇文章列表 |
| apply | 申請 | 聯絡表單 |

## 色彩系統（CSS 變數）
```css
--w: #FAF7F2      /* 主背景白 */
--cream: #F5F0E8  /* 奶油色區塊 */
--sand: #E8DFD0   /* 沙色 */
--sandm: #D4C8B5  /* 深沙色 */
--forest: #3D5A4C /* 深綠（主題色）*/
--wg: #9E9087     /* 暖灰（輔助文字）*/
```

## 重要常數（可直接修改）

### 客戶見證
```js
const TESTIMONIALS = [...]
// 每筆格式：{ stars, text, name, tag }
```

### 名額控制
```js
const QUOTA_CONFIG = {
  mem_current: 3,     // 位置練習室剩餘名額
  mem_total: 10,
  deep_open: true,    // 深度陪跑是否開放
  next_open: "5月1日"
}
```

### 申請表串接
```js
const FORM_ENDPOINT = ""
// 填入 Formspree URL 即可收到 Email 通知
// 例："https://formspree.io/f/xxxxxx"
```

### 生命數字說明
```js
const NUM_DESC = { 1: {...}, 2: {...}, ... 9: {...} }
// 每筆：{ color, bg, title, x（主命數說明）, yr（流年說明）}

const NUM_REL = { 2: "...", 3: "...", ... 12: "..." }
// 關係數 2-12 的說明文字
```

## 農曆功能
- 內建 1900–2050 農曆對照表（`const LD=[...]`）
- 計算農曆主命數、流年數
- 關係數由兩人農曆主命數相加（2–12），無路徑顯示
- 數字顯示格式：34/7、19/10/1（顯示化簡路徑）

## 主要元件
| 元件 | 說明 |
|------|------|
| `Testimonials` | 客戶見證區塊，讀取 TESTIMONIALS 陣列 |
| `EmailCapture` | 首頁 Email 訂閱欄位 |
| `QuotaBanner` | 名額狀態提示（type="mem" 或 "deep"）|
| `NumEmailCapture` | 生命數字結果頁 Email 收集 |
| `QuotaBanner` | 名額狀態，讀取 QUOTA_CONFIG |
| `NumCard` | 主命數+流年數卡片 |
| `RelCard` | 關係數卡片 |

## 待補充內容
1. 流年數 1–9 的詳細說明（目前為基礎版）
2. 觀點文章完整內文（目前只有標題和摘要）
3. FORM_ENDPOINT 填入 Formspree URL
4. 真實客戶見證（目前為示範文字）
5. 聯絡資訊（email、Line ID、Instagram）

## 品牌資訊
- 品牌：Sofia 蘇菲療癒轉化
- 副標語：情緒穩定 × 關係覺察 × 內在主導權
- 核心主張：穩住自己，關係才會穩。
- 目標客群：30–45 歲高責任女性
- 語氣：溫暖但清醒，有洞察但不說教
