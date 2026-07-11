# 跟著 Young 走不會錯 - 福岡 7 日遊 🗾

2026/7/16（四）– 7/22（三）福岡自由行行程 App。純網頁單檔案，部署在 GitHub Pages，支援手機加入主畫面、離線瀏覽。

🔗 線上網址：https://cyysongyy.github.io/fukuoka-trip/福岡7日遊.html

## 功能

- **📅 每日行程**：7 天行程卡片式呈現，交通、住宿、美食、注意事項一次看
  - 每張卡片有編號，可用 ▲▼ 按鈕自行調整當天卡片順序（存在手機本機，可一鍵還原原始順序）
- **🍜 美食特輯 / 🎁 採買・伴手禮 / 🏪 超商必買**：分類整理的加碼景點與店家清單
- **🎒 備品清單**：出發前打包檢查表，可勾選、可自行新增/刪除品項，附進度條
- **🤖 AI 旅遊小幫手**：串接使用者自己的 Gemini 或 OpenAI API Key，針對行程內容即時問答
- **🔒 私人資訊**：PIN 碼保護的自訂欄位（密碼、包車資訊等），僅存手機本機
- **🧭 我在哪**：一鍵開啟 Google 地圖目前位置
- **PWA 離線支援**：加入主畫面後可離線瀏覽行程內容（AI 問答需要網路）

## 檔案結構

```
福岡7日遊.html   主程式（單一 HTML 檔，含所有行程資料與邏輯）
manifest.json    PWA 設定（App 名稱、圖示、啟動模式）
sw.js            Service Worker，負責離線快取
icon-192.png     App 圖示 192x192
icon-512.png     App 圖示 512x512
```

## 使用方式

### 手機安裝（推薦）

1. 用 **Safari** 開啟上方網址（不要用 LINE 內建瀏覽器，會擋 App 部分功能）
2. 分享 → **加入主畫面**
3. 桌面會出現圖示，點開即為全螢幕 App 體驗
4. 首次開啟時請保持連網，讓 Service Worker 完整快取一次，之後即可離線瀏覽行程內容

### AI 小幫手設定

點底部「🤖 小幫手」，貼上自己的 API Key 即可使用：

- **Gemini**（免費）：[Google AI Studio](https://aistudio.google.com/apikey) → 用個人 Gmail 登入 → Create API key（選 in new project）
- **OpenAI**：[platform.openai.com](https://platform.openai.com/api-keys) → API keys（需綁定付費）

Key 只會存在使用者自己手機的 localStorage，不會上傳到任何伺服器。

## 資料與隱私

本 App 沒有後端伺服器，所有使用者輸入（備品清單、卡片排序、私人資訊、AI Key）都只存在**該支裝置的瀏覽器 localStorage**，不會同步、不會外流。清除瀏覽器資料或換裝置會導致這些自訂內容遺失（行程本身的靜態內容不受影響）。

## 更新紀錄

- **v3**：新增「🎒 備品清單」（可勾選、新增、刪除品項）
- **v2**：每日行程卡片新增編號，可自行拖移排序（▲▼ 按鈕）
- **v1**：PWA 離線安裝支援（manifest + service worker）

## 技術

純 HTML / CSS / JavaScript（無框架、無建置工具），部署於 GitHub Pages。
