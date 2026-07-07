# Apple 官網切版練習

這是一個以 [Apple 官網](https://www.apple.com/) 為參考設計的**前端切版學習專案**，透過模仿知名網站的版面結構與視覺風格，練習 HTML、CSS 與 RWD（響應式網頁設計）的實作能力。

> 本專案僅供個人學習與練習使用，與 Apple Inc. 無任何關聯。所有商標、產品名稱與圖片僅作教學示範用途。

---

## 學習目標

- 練習語意化 HTML 結構（`header`、`section`、`footer` 等）
- 熟悉 Flexbox 與 CSS Grid 版面配置
- 實作固定導覽列與行動版漢堡選單
- 使用背景圖片（`background-image`）呈現產品視覺
- 練習 Media Query 響應式斷點設計
- 以原生 JavaScript 處理簡單的 DOM 互動

---

## 技術棧

| 類別          | 說明                                      |
| ------------- | ----------------------------------------- |
| HTML5         | 頁面結構                                  |
| CSS3          | 樣式與響應式排版                          |
| JavaScript    | 行動選單開關邏輯                          |
| normalize.css | 瀏覽器預設樣式重置                        |
| SASS（選用）  | `style.sass` 原始檔，可編譯為 `style.css` |

---

## 頁面結構

```
導覽列（Navbar）
├── 桌面版：水平選單
└── 行動版：漢堡按鈕 + 全螢幕選單

Hero 區塊 × 2
├── iPhone 17
└── AirPods Pro 3

Grid 產品區塊 × 4（2 欄排版）
├── iPad Air
├── MacBook Air
├── Watch SE
└── iPad

頁尾（Footer）
```

---

## 專案目錄

```
APPLE練習/
├── README.md
├── asset/                  # 靜態資源
│   └── image/              # 產品圖片素材
│       ├── iphone.png
│       ├── airpods pro 3.jpg
│       ├── ipad_air4.png
│       ├── mac_book_air.png
│       ├── watch_se.png
│       └── ipad.png
└── src/                    # 程式碼
    ├── index.html          # 主頁面
    └── css/
        ├── normalize.css   # CSS 重置
        ├── style.css       # 主要樣式
        ├── style.sass      # SASS 原始檔
        └── style.css.map
```

---

## 響應式斷點

| 斷點      | 行為                                       |
| --------- | ------------------------------------------ |
| `> 960px` | 顯示完整桌面導覽列                         |
| `≤ 960px` | 隱藏導覽列，顯示漢堡按鈕                   |
| `≤ 800px` | Grid 改為單欄排版，背景圖改為 `cover` 填滿 |

---

## 如何預覽

本專案為純靜態網頁，無需安裝套件。擇一方式開啟即可：

### 方法一：直接開啟

在瀏覽器中開啟 `src/index.html`。

### 方法二：使用 Live Server（建議）

若使用 VS Code，可安裝 **Live Server** 擴充功能，對 `src/index.html` 右鍵選擇「Open with Live Server」，以本地伺服器預覽並支援熱重載。

### 方法三：使用 Python 內建伺服器

在專案根目錄執行：

```bash
python -m http.server 8080
```

瀏覽器前往 `http://localhost:8080/src/` 即可預覽。

---

## 主要功能說明

### 導覽列

- 固定於頁面頂部（`position: fixed`）
- 半透明黑色背景，模擬 Apple 官網風格
- 小螢幕以 JavaScript 複製桌面選單內容至行動選單，避免重複撰寫 HTML

### Hero 區塊

- 全寬產品展示區，包含標題、副標題與 CTA 按鈕
- 產品圖片以 `background-image` 呈現，路徑引用 `../asset/image/`
- 大螢幕使用 `contain` 完整顯示圖片；小螢幕使用 `cover` 填滿容器

### Grid 產品區

- 使用 CSS Grid 實作 2 欄排版
- 每個區塊含產品名稱、說明文字與操作按鈕

---

## 授權

MIT License — Copyright (C) 2025 ning
