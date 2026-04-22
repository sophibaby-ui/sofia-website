# Sofia 蘇菲療癒轉化 — 網站專案

## 本機啟動

```bash
npm install
npm run dev
```

瀏覽器開啟 http://localhost:5173

## 部署到 Vercel

1. 推上 GitHub：
```bash
git init
git add .
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/你的帳號/sofia-website.git
git push -u origin main
```

2. 到 vercel.com → Import Project → 選你的 repo → Deploy

## 常用設定位置（在 src/App.jsx 裡搜尋）

| 功能 | 搜尋關鍵字 |
|------|-----------|
| 客戶見證內容 | `const TESTIMONIALS` |
| 名額控制 | `const QUOTA_CONFIG` |
| 申請表串接 | `const FORM_ENDPOINT` |
| 主命數說明 | `const NUM_DESC` |
| 關係數說明 | `const NUM_REL` |

## 專案結構

```
sofia-project/
├── index.html          # 入口 HTML
├── package.json        # 套件設定
├── vite.config.js      # Vite 設定
├── public/
│   └── favicon.svg     # 網站圖示
└── src/
    ├── main.jsx        # React 進入點
    └── App.jsx         # 主程式（所有頁面都在這裡）
```
