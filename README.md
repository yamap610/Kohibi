# 🌸 小日子 | Day's & Moments

每一天的美好時光，都值得被記錄。

一個為家庭設計的寫真月曆 webapp，用去背貼紙照片記錄每一天的穿搭、美食、飲料與生活點滴。

---

## ✨ 功能

- 📅 **寫真月曆** — 每天上傳去背照片，自動呈現貼紙漂浮效果
- 🗂️ **四大分類** — 穿搭 / 美食 / 飲料 / 生活，各自獨立月曆
- ✂️ **裁切功能** — 上傳後可自由拖曳、縮放調整構圖（3:4 比例）
- 📝 **備註** — 每張照片可加入文字備註（顯示於格子底部）
- 🎀 **紀念日標記** — 設定固定日期，月曆自動顯示紅點提醒
- 📊 **統計頁** — 查看每個分類本月記錄天數與進度
- ☁️ **雲端同步** — Firebase Firestore 儲存，家人共用同一份資料
- 🖼️ **匯出 PNG** — 月曆原比例，適合傳給家人
- 📱 **匯出限動版** — 9:16 比例，適合 Instagram / Line 限時動態
- 🖨️ **匯出 PDF** — A4 直式，下載後可送印或列印
- 💾 **備份還原** — 匯出 JSON 備份，可跨裝置還原

---

## 🚀 使用方式

直接用瀏覽器開啟，不需安裝：

**[https://yamap610.github.io/kohibi/](https://yamap610.github.io/kohibi/)**

### 加到 iPhone 主畫面（推薦）
1. 用 **Safari** 開啟網址
2. 點底部 **分享** 按鈕 □↑
3. 選擇 **「加入主畫面」**
4. 名稱填「小日子」→ 點新增

---

## 🛠️ 技術

| 項目 | 內容 |
|------|------|
| 前端 | 純 HTML / CSS / JavaScript，無框架 |
| 部署 | GitHub Pages |
| 資料庫 | Firebase Firestore（免費方案） |
| 圖片儲存 | base64 壓縮後存入 Firestore（PNG，最長邊 600px） |
| 字體 | Cormorant Garamond + Zen Maru Gothic |

---

## 📁 檔案結構

```
kohibi/
└── index.html   # 全部功能在單一 HTML 檔案內
```

---

## 🔥 Firebase 設定

本專案使用 `home-hub-be41f` Firebase 專案的 Firestore。

Collection：`kohibi`  
Document key 格式：`年-月-日-分類`（例：`2026-3-16-outfit`）

Firestore Rules（需設定為允許讀寫）：
```
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    match /{document=**} {
      allow read, write: if true;
    }
  }
}
```

---

## 📸 去背推薦工具

上傳前建議先去背，效果最好：
- **[remove.bg](https://www.remove.bg/zh)** — 免費，自動去背，支援手機上傳

---

*小日子 · 記錄每一天的美好時光 🌸*
