# 小乖記帳｜家庭智慧記帳與多人拆帳系統（Demo）

> 這是一個以「家庭日常記帳、多人拆帳、欠款／還款與本輪結算」為核心的個人專案 Demo。  
> 為保護隱私與機密資訊，本 Repository 僅保留展示用版本，**不包含正式環境的 API Key、Token、Secret、姓名、真實交易資料或正式後端網址**。

---

## 專案介紹

「小乖記帳」是一套以實際家庭使用情境出發所設計的記帳系統。

相較於一般單人記帳 App，更著重在：

- 多人共同消費
- 誰先付款、誰需要分攤
- 欠款與還款關係
- 本輪尚未結清的債務
- 個人本輪消費與分類分析
- LINE / Web 介面整合

目標是把原本分散在聊天訊息、人工計算與記憶中的家庭帳務，整理成一套可以記錄、追蹤、修改與結算的流程。

---

## Demo 說明

Demo 版本已移除或替換以下內容：

- 真實家庭成員姓名
- 真實消費與交易紀錄
- 正式 Google Sheet ID
- Apps Script 正式部署網址
- LINE Channel Secret / Access Token
- LIFF 正式設定
- API Secret
- 其他正式環境憑證與私人資料

畫面中的人物、金額與交易內容皆為 **Mock Data / 示範資料**。

> ⚠️ 本 Demo 不做為正式帳務系統使用。

---

## 主要功能

### 1. 一般記帳

可記錄：

- 記帳人
- 金額
- 消費項目
- 消費分類
- 付款方式
- 信用卡
- 回饋 %
- 外幣金額與匯率換算

海外消費可使用參考匯率換算為台幣，並保留手動修改匯率的彈性。

### 2. 多人拆帳

適合家庭聚餐、旅遊、共同採買等情境。

系統可記錄：

- 付款人
- 參與分帳人
- 總金額
- 個人分攤金額
- 付款資訊
- 消費分類

並將「實際消費」與「替其他人代墊」分開計算。

### 3. 欠款

支援直覺式的債務關係，例如：

```text
成員 B 欠 成員 A 500 午餐代墊
```

系統會建立應收／應付關係，並納入本輪債務計算。

### 4. 還款

支援記錄成員之間的還款，例如：

```text
成員 B 還 成員 A 500 午餐代墊
```

還款後會同步更新債務關係。

### 5. 記帳明細

提供完整明細查詢，可依條件篩選：

- 記帳人
- 類型
- 年月
- 關鍵字

並支援：

- 本輪明細
- 編輯
- 刪除
- 查看原始送出內容

手機版與桌面版皆有對應排版。

### 6. 本輪結算

系統會根據尚未結清的資料，計算每位成員的：

- 本輪總花費
- 本輪總代墊
- 應收總額
- 應付總額

並呈現成員間的債務關係。

### 7. 視覺化分析

結果頁目前包含：

#### 支出與代墊比較圖

比較各成員：

- 本輪總支出
- 本輪總代墊

#### 個人本輪消費明細

依目前選取的成員顯示各分類消費金額，例如：

- 飲食
- 交通
- 居家
- 購物
- 醫療
- 休閒
- 其他分類

可用圖表切換方式查看不同視角。

### 8. LINE / LIFF 整合

正式版本可由 LINE Rich Menu 快速進入：

- 一般記帳
- 多人拆帳
- 欠款
- 還款
- 記帳明細
- 本輪債務

並可使用 LIFF 在 LINE App 內直接操作 Web 介面。

> Demo 不包含正式 LIFF ID 與 LINE 憑證。

---

## 系統架構

正式版本採用以下架構：

```text
LINE / LIFF
      │
      ▼
Cloudflare Frontend
      │
      ▼
Google Apps Script API
      │
      ▼
Google Sheets
```

各層職責：

| 層級 | 用途 |
|---|---|
| Cloudflare | Web / LIFF 前端介面 |
| Google Apps Script | API、商業邏輯、自動化 |
| Google Sheets | 第一階段資料儲存 |
| LINE Messaging API | Bot 記帳與互動 |
| LIFF | LINE App 內嵌 Web 操作 |

---

## 使用技術

- HTML
- CSS
- JavaScript
- Google Apps Script
- Google Sheets
- Cloudflare Workers / Pages
- LINE Messaging API
- LIFF
- Google Charts

---

## 專案重點

這個專案不是單純的「記帳」，而是針對真實家庭帳務流程所做的系統化設計。

主要思考包含：

- 如何把聊天語句轉成結構化帳務資料
- 如何區分「本人消費」與「替別人代墊」
- 如何正確處理欠款與還款方向
- 如何保存原始輸入，方便後續查核與修改
- 如何讓桌面版與手機版共用同一套資料邏輯
- 如何將 LINE、Web 與 Google Sheets 串成同一個流程

---

## 隱私與安全

Demo Repository 為公開展示版本，遵循以下原則：

```text
Never commit:
- API Keys
- Access Tokens
- Channel Secrets
- Spreadsheet IDs
- Admin Secrets
- Personal transaction data
- member information
```

正式環境中的敏感參數不直接寫入前端程式碼或公開 Repository。

---

## Demo 與正式版差異

| 功能 | Demo | 正式版本 |
|---|---:|---:|
| UI / RWD | ✅ | ✅ |
| 一般記帳流程 | ✅ | ✅ |
| 多人拆帳流程 | ✅ | ✅ |
| 欠款 / 還款 | ✅ | ✅ |
| 記帳明細 | ✅ | ✅ |
| 結算視覺化 | ✅ | ✅ |
| Mock Data | ✅ | - |
| 真實 Google Sheets | ❌ | ✅ |
| LINE Bot | ❌ / 模擬 | ✅ |
| LIFF 正式串接 | ❌ | ✅ |
| 正式 API Secret | ❌ | ✅ |

---

## 執行 Demo

此版本為純前端 Demo，可直接：

```bash
git clone <YOUR_REPOSITORY_URL>
cd <YOUR_PROJECT_FOLDER>
```

接著直接開啟：

```text
index.html
```

或使用 VS Code Live Server / GitHub Pages 執行。

---

## Live Demo

👉 **Demo 網址：**  
`https://sylvia-original.github.io/Xiaoguai-accounts-demo/`

---

## Author

**Sylvia**

---

## License / Usage

本專案主要作為個人作品集與技術展示使用。

Demo 程式碼可供學習與參考；如需使用於正式環境，請自行補齊身份驗證、權限控管、資料庫與資訊安全機制。
