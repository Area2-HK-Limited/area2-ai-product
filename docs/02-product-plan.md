# 🚀 Area2 AI Assistant — 產品開發計劃書 (v2)
## 基於 OpenClaw 平台的香港中小企 AI 訂閱服務
## 核心賣點：WhatsApp 原生 × 越用越識你

**版本：** v2.0  
**日期：** 2026 年 3 月  
**撰寫：** A2 (B03) × ErIc  

---

## 目錄
1. [產品定義與核心賣點](#1-產品定義與核心賣點)
2. [兩大獨家賣點深度解析](#2-兩大獨家賣點深度解析)
3. [完整能力清單（基於實際 Skills）](#3-完整能力清單)
4. [用戶痛點 × 真實能力對照](#4-用戶痛點對照)
5. [訂閱方案設計](#5-訂閱方案設計)
6. [用戶故事——一天用下來的體驗](#6-用戶故事)
7. [網站架構規劃](#7-網站架構規劃)
8. [技術架構](#8-技術架構)
9. [Nuxt.js 開發規格](#9-nuxtjs-開發規格)
10. [頁面設計細則](#10-頁面設計細則)
11. [多語言策略](#11-多語言策略)
12. [SEO 策略](#12-seo-策略)
13. [開發路線圖](#13-開發路線圖)
14. [商業模型](#14-商業模型)

---

## 1. 產品定義與核心賣點

### 1.1 一句話定位

> **「你 WhatsApp 它，它幫你做嘢——而且越用越識你。」**

### 1.2 產品名稱
- **Area2 AI**（主品牌）
- 英文 Tagline：*Your AI that lives in WhatsApp and learns your business*
- 廣東話 Tagline：「住喺你 WhatsApp 入面的 AI 幫手，越用越識你」

### 1.3 兩大核心賣點（USP）

```
╔════════════════════════════════════════════════════════╗
║  USP 1: WhatsApp 原生                                  ║
║  「唔使裝 App、唔使改習慣——直接喺 WhatsApp 用 AI」     ║
╠════════════════════════════════════════════════════════╣
║  USP 2: 越用越識你                                     ║
║  「記住你的業務、客戶、習慣——AI 會不斷學習你的心意」   ║
╚════════════════════════════════════════════════════════╝
```

### 1.4 核心差異化表

| 普通 AI 工具 | Area2 AI |
|------------|---------|
| 要開另一個 App | **直接喺 WhatsApp 用** |
| 每次 Session 忘記你 | **永久記住你的業務（越用越識）** |
| 你問，它答（被動） | **它主動幫你做嘢（主動）** |
| 只有一個 AI | **多個專門 AI 腦協作** |
| 英文介面為主 | **廣東話語音、廣東話回覆** |
| 照單全收 | **學習你的偏好，自動適應** |

---

## 2. 兩大獨家賣點深度解析

### 2.1 USP 1：WhatsApp 原生（最低門檻的 AI 採用）

#### 為什麼 WhatsApp 是香港最佳切入點
- 香港 WhatsApp 滲透率約 90%
- 73% 香港中小企已用 WhatsApp 做客服
- 老闆每日平均花 3–4 小時在 WhatsApp

#### Area2 AI 的 WhatsApp 體驗

**個人 DM 模式（Personal Assistant）：**
```
ErIc → Area2 AI（WhatsApp）：
「幫我搵下今日港股有咩大升幅，整個摘要」

Area2 AI 自動：
1. 搜尋即時股市數據
2. 整理今日大升幅股票
3. WhatsApp 回覆清晰摘要（附數字）

全程：用戶喺 WhatsApp，AI 喺 WhatsApp，唔需要跳去任何 App
```

**WhatsApp Group 模式（Team Assistant）：**
```
Group「銷售團隊」：
陳生：「今日同 ABC 公司開完會，要 follow up 三件事...」
（一段語音訊息）

Area2 AI 自動：
1. 轉錄廣東話語音
2. 識別行動事項
3. 在 Group 回覆「✅ 已記錄以下 Follow Up：
   1. [事項A] → 陳生負責 → 本週五前
   2. [事項B] → ...」
4. 設定提醒，時間到自動再提醒 Group
```

#### 支援的 WhatsApp 功能
- ✅ DM（個人對話）
- ✅ Group Chat（群組）
- ✅ 語音訊息（廣東話自動轉文字）
- ✅ 圖片/截圖分析
- ✅ PDF/文件接收分析
- ✅ 主動發送提醒
- ✅ 定時報告

---

### 2.2 USP 2：越用越識你（學習型 AI 記憶）

#### 記憶如何運作

```
你每次同 Area2 AI 互動，它都在學習：

📝 學習你的業務
   → 你係做咩行業、賣咩產品、主要客群係邊個

👥 學習你的客戶
   → 張生係你嘅大客、李小姐偏好週五下午開會、
     ABC公司每月訂 50 件

📋 學習你的工作習慣
   → 你通常幾點睇報告、你鍾意用廣東話定英文回客、
     你嘅報價單格式

🎯 學習你的偏好
   → 你鍾意直接答案、唔鍾意廢話、
     你對某類客戶有特別處理方式

第 1 天用：一個聰明的 AI
第 30 天用：一個識你的 AI  
第 90 天用：一個幾乎係你「數字孖生」的 AI
```

#### 記憶的商業價值（留客機制）

```
用了 Area2 AI 3 個月後的用戶：

AI 記住了：
✓ 100+ 個客戶的偏好和歷史
✓ 你的業務流程和 SOP
✓ 你的回覆風格和常用說法
✓ 你的重要 deadline 和習慣

如果轉用 ChatGPT？
→ 要從頭解釋所有嘢
→ 新 AI 完全唔識你
→ 用戶根本唔捨得轉

這就是最強的留客護城河（Retention Moat）
```

#### 記憶技術（向量記憶庫）
- **儲存格式：** LanceDB 向量資料庫
- **搜索方式：** 混合搜索（語義 70% + 關鍵詞 30%）
- **記憶分類：** 業務事實、決定記錄、用戶偏好、實體信息
- **記憶容量：** Starter 500條 / Business 5,000條 / Enterprise 無限
- **學習方式：** 每次對話自動提取重要信息存入記憶

---

## 3. 完整能力清單

### 3.1 基礎能力（所有方案）

#### 💬 WhatsApp 原生
- DM 個人助手模式
- Group 群組協作模式
- 語音訊息廣東話轉文字
- 圖片/截圖分析
- PDF/Word/Excel 接收分析
- 主動提醒（定時推送到 WhatsApp）

#### 🧠 記憶系統
- 向量記憶庫（LanceDB）
- 業務背景永久記憶
- 客戶歷史記憶
- 自動學習用戶偏好
- 跨 Session 記憶延續

#### ⏰ 主動任務
- Cron 定時任務（每日/每週/指定時間）
- 主動提醒和跟進
- 定時報告推送（WhatsApp 發送）
- 業務監察（競品、社媒、市場）

---

### 3.2 技能包（Skills）——基於真實已有功能

#### 📊 市場情報技能包
| 技能 | 功能 | 業務場景 |
|------|------|---------|
| 社交媒體監察 | 小紅書/抖音/Instagram/微博 爬蟲 | 監察競品、KOL 動態 |
| 股票市場 | 即時股票數據（yFinance API）| 每日港股摘要 |
| 網絡研究 | Perplexity AI 搜索 + 引用 | 任何市場調查 |
| YouTube 摘要 | 提取影片要點 | 培訓材料、競品研究 |

#### 📄 文件處理技能包
| 技能 | 功能 | 業務場景 |
|------|------|---------|
| PDF 文字提取 + OCR | 繁中英 OCR | 合約、發票、報告 |
| Word 翻譯 | DOCX 格式保留翻譯 | 客戶文件中英翻譯 |
| 批量圖片處理 | 批量 OCR / 分析 | 大量收據、單據 |
| PDF 轉 Word | 格式轉換 | 文件整理 |

#### 🎙️ 語音和媒體技能包
| 技能 | 功能 | 業務場景 |
|------|------|---------|
| 廣東話 TTS | 文字轉廣東話語音 | 語音通知、客服語音 |
| 長文 TTS | 長篇文章轉音頻 | 培訓材料有聲版 |
| 語音分析 | 會議錄音 → 行動事項 | 開會後自動整理 |
| 影片生成 | AI 生成影片（MiniMax） | 廣告、社媒內容 |
| 音樂生成 | AI 作曲填詞 | 廣告音樂、背景音 |
| 產品示範片 | 錄屏 → 專業廣東話配音 | 產品介紹影片 |

#### 🖼️ 圖像技能包
| 技能 | 功能 | 業務場景 |
|------|------|---------|
| 圖片生成 | 阿里雲 Wanx AI 出圖 | 社媒配圖、產品圖 |
| MiniMax 圖片 | MiniMax 圖片生成 | 另一風格選擇 |
| 視覺分析 | DashScope 圖片理解 | 產品圖分析、比較 |

#### 🛒 電商情報技能包
| 技能 | 功能 | 業務場景 |
|------|------|---------|
| HKTVMall 監察 | 搜索、監察產品/價格 | 競品定價、選品 |
| Taobao 搜索 | 搜索商品 | 採購參考、比價 |

#### 🔧 業務工具技能包
| 技能 | 功能 | 業務場景 |
|------|------|---------|
| Lark/飛書任務 | 任務 CRUD、清單管理 | 項目管理 |
| 智能提醒 | WhatsApp Group/DM 精準提醒 | 會議提醒、跟進 |
| WhatsApp 助手 | 標準化 WhatsApp 工作流 | 全面 WhatsApp 管理 |
| QA 測試 | 網頁自動測試 | IT 公司適用 |
| CMS 文件生成 | 自動生成 CMS 操作手冊 | 系統培訓 |
| Planka 看板 | 項目看板管理 | 項目追蹤 |

#### 🤖 AI 協作技能包
| 技能 | 功能 | 業務場景 |
|------|------|---------|
| Sub-Agent 系統 | 複雜任務拆解並行 | 大型研究、報告生成 |
| 多模型調度 | 根據任務選最佳模型 | 成本 + 效果優化 |
| Bug 分析 | 用戶反饋 → 技術報告 | IT/軟件公司 |

---

### 3.3 渠道能力（多於 WhatsApp）

| 渠道 | 支援 | 用途 |
|------|------|------|
| **WhatsApp** | ✅ DM + Group | **主要渠道——香港首選** |
| **Telegram** | ✅ Bot + Group | 科技圈、初創常用 |
| **Discord** | ✅ Server + Channel | IT/遊戲/社群公司 |
| Web Chat | ✅ 嵌入式 | 官網客服 |
| Signal（預計） | 🔜 計劃中 | 高私隱需求 |

---

## 4. 用戶痛點對照

### 4.1 完整痛點 × 解決方案矩陣

| 用戶痛點 | 傳統解決 | Area2 AI 方案 | 使用技能 |
|---------|---------|--------------|--------|
| WhatsApp 回唔切 | 自己回/請人 | WhatsApp AI 自動篩選、建議/自動回覆 | whatsapp-assistant |
| 語音訊息聽唔完 | 自己播晒 | 廣東話自動轉文字 + 摘要 | audio-handler |
| 開會後冇人跟進 | Email 發出去無人理 | 會議語音 → 行動清單 → 分配 → 自動提醒 | audio-handler + cron |
| AI 唔記得你 | 每次重新解釋 | 向量記憶庫，永久記住業務背景 | memory system |
| 下班後漏接客 | 無 | 24/7 WhatsApp 自動回覆 | whatsapp + cron |
| 競品動態追唔到 | 人手搜索 | 定時自動爬社交媒體 + WhatsApp 摘要 | social-scraper + cron |
| 股市/市場資訊 | 自己查 App | 每日自動股市摘要推送 WhatsApp | stock-market + cron |
| PDF/合約要分析 | 自己讀/外包 | WhatsApp 發 PDF → AI 即時解讀 | pdf-utils |
| 文件要中英翻譯 | 人手翻譯/翻譯社 | Word 文件格式保留翻譯 | docx-translator-v2 |
| 社媒帖文耗時 | 自己寫/外包 | AI 生成符合品牌語氣帖文 + 配圖 | image-generation |
| 廣告影片太貴 | 外包製作公司 | AI 生成影片 / 錄屏 → 配音 | minimax-video, screen-to-script |
| 客服語音太貴 | 請人 / IVR | 廣東話 AI 語音回覆 | minimax-tts |
| HKTVMall 競品監察 | 人手定期搜索 | 自動監察價格 + 通知 | hktvmall |
| 採購比價 | 人手上 Taobao | 自動搜索比價 | taobao-search |
| YouTube 培訓影片太長 | 自己全看 | AI 提取重點 + 中文摘要 | youtube-summarizer |
| 項目任務無人跟進 | Email/口頭 | Lark 任務自動創建 + 提醒 | lark-tasks |

---

## 5. 訂閱方案設計

### 🌱 Starter（入門版）
**HK$298/月**（年付 HK$248/月，慳 17%）

**適合：** 自由職業者、1–3人初創、個人老闆

**核心亮點：** WhatsApp AI + 基礎記憶——比 ChatGPT 多 WhatsApp，同價

| 功能 | 包含 |
|------|------|
| **WhatsApp DM** | ✅ 個人助手 |
| **WhatsApp Group** | ❌ |
| 記憶容量 | 500 條 |
| 每月對話次數 | 500 次 |
| AI 模型 | 1 個（MiniMax 快速模型）|
| **語音訊息轉文字** | ✅ 100 次/月 |
| **定時任務（Cron）** | 3 個 |
| 技能包 | 基礎 3 個（提醒、搜索、文件）|
| 主動 WhatsApp 推送 | ✅ |
| 廣東話 TTS | ❌ |
| 技術支援 | Email，3個工作日 |

---

### 💼 Business（商業版）⭐ 最多人選
**HK$888/月**（年付 HK$738/月，慳 17%）

**適合：** 5–20人中小企、零售店、服務業、Agency

**核心亮點：** 全渠道 + 完整記憶 + 業務自動化——一個 AI，解決日常 80% 重複工作

| 功能 | 包含 |
|------|------|
| **WhatsApp DM + Group** | ✅ 全部 |
| **Telegram + Discord** | ✅ |
| 記憶容量 | 5,000 條 |
| 每月對話次數 | 3,000 次 |
| AI 模型 | 3 個切換（MiniMax + Claude + GPT）|
| **語音訊息轉文字** | ✅ 無限 |
| **定時任務（Cron）** | 20 個 |
| 技能包 | 全部基礎 + 5 個進階 |
| **社交媒體監察** | ✅ 小紅書/Instagram |
| **文件翻譯** | ✅ 中英 |
| **股票/市場資訊** | ✅ |
| **圖片生成** | ✅ 100 次/月 |
| **廣東話 TTS** | ✅ 500 次/月 |
| Sub-Agents | 3 個並行 |
| 技術支援 | WhatsApp 即時（週一至六）|
| 設定服務 | 2 小時 1-on-1 |
| **Google Workspace 整合** | ✅ |

---

### 🏢 Enterprise（企業版）
**HK$2,888/月起**

**適合：** 20人以上企業、連鎖店、IT 公司

| 功能 | 包含 |
|------|------|
| 全部 Business 功能 | ✅ |
| 記憶容量 | 無限 |
| 對話次數 | 無限 |
| AI 模型 | 全部 + 可微調 |
| 技能包 | 全部 + 客製化開發 |
| **多個專門 AI** | ✅（客服AI、行銷AI、財務AI）|
| **私有部署** | ✅（數據不離開公司）|
| Sub-Agents | 無限 |
| 定時任務 | 無限 |
| WhatsApp 帳號數量 | 多個 |
| 專屬客戶成功經理 | ✅ |
| SLA 99.9% | ✅ |
| 符合 PDPO | ✅ |

---

### 增值服務 Add-ons

| 服務 | 定價 | 說明 |
|------|------|------|
| 基礎設定服務 | HK$800（一次） | 2 小時設定 + 培訓 |
| 深度設定服務 | HK$2,500（一次） | 全天設定 + 業務流程設計 |
| 客製化 Skill 開發 | HK$5,000 起 | 按需開發專屬功能 |
| 額外對話次數 | HK$100/1,000 次 | 超額使用 |
| HKTVMall/電商監察 | HK$200/月 Add-on | 加購技能包 |
| 定期月報分析 | HK$500/月 | AI 使用效益報告 |

---

## 6. 用戶故事——一天用下來的體驗

### 陳生的一天（20人貿易公司老闆）

```
07:30 AM — 起床，WhatsApp 一打開
  Area2 AI：「早安陳生！昨晚有 3 條客戶查詢，我已幫你
            整理好：
            1. 美麗華公司問報價 → 我已準備好草稿，
               你確認後發出？
            2. 李生問貨期 → 根據上次紀錄，
               應該係下週三，確認嗎？
            3. 新客戶 ABC Ltd 詢盤 → 未有背景資料，
               需要你親自跟進」

08:00 AM — 讀了一段語音備忘（廣東話）
  Area2 AI 自動：轉文字 → 整理成行動事項 →
                 儲存到 Lark Tasks

10:00 AM — 開完同供應商嘅會議
  陳生（WhatsApp Group）：「剛才開完會，
                          [@Area2AI 幫我整理下行動事項]」
  Area2 AI：「✅ 已整理：
             1. 訂單確認 → 陳生 → 今日內
             2. 更新報價 → 小明 → 週三前
             3. 跟進付款 → 阿芬 → 本週五
             已設定提醒，時間到會通知各人」

12:30 PM — 午飯時間
  Area2 AI 主動推送：「📊 今日市場摘要：
                      • 你主要採購品類原材料價格上升 3%
                      • 競品 X 公司昨日喺小紅書發佈新品
                      • 港股：你持倉相關股份升 1.2%」

03:00 PM — 收到客戶發來一份英文合約 PDF
  陳生（WhatsApp）：「幫我睇下呢個合約有咩要注意」
  Area2 AI：「✅ 已分析合約（23頁）：
             🔴 風險條款：第 8 條付款期限較短（15日）
             🟡 注意：第 12 條自動續約條款，需提前 30 日通知
             🟢 整體條款標準，無異常」

06:00 PM — 下班
  陳生：「今日OK，收工」
  Area2 AI：「好！我繼續監察 WhatsApp，如有緊急查詢
            我先回覆。明早 7:30 再整理今日未處理事項給你。
            祝晚安！」

10:30 PM — 新客戶深夜發查詢
  Area2 AI 自動回覆：「您好！感謝查詢，本公司 AI 助手
                      已收到您的訊息。陳生明早會親自跟進，
                      請期待！同時我已記下您的需求：[摘要]」
```

### 結果：
- ⏱️ 陳生每日節省 **2–3 小時** WhatsApp 處理時間
- 💰 零深夜漏客（AI 24/7 在線）
- 🧠 所有客戶資料、決定自動記錄
- 📊 每日市場情報不用自己搜索

---

## 7. 網站架構規劃

### 7.1 頁面結構（WhatsApp 為重心）

```
/ (首頁)
├── #hero          → WhatsApp 操作 GIF/示範
├── #pain-points   → 「你的 WhatsApp 地獄」共鳴區
├── #how-it-works  → 3 步驟：連接→說話→AI做嘢
├── #features      → 功能展示（WhatsApp中心）
├── #use-cases     → 3個行業場景
├── #memory        → 「越用越識你」專門section
├── #pricing       → 定價
├── #demo-video    → 2分鐘示範影片
└── #cta           → 免費試用

/features
├── /features/whatsapp     → WhatsApp 深度功能
├── /features/memory       → 記憶系統解說
├── /features/automation   → 自動化任務
└── /features/skills       → 技能包目錄

/use-cases
├── /use-cases/retail         → 零售/連鎖店
├── /use-cases/trade          → 貿易公司
├── /use-cases/agency         → 數碼營銷 Agency
├── /use-cases/professional   → 專業服務（會計/律師）
└── /use-cases/restaurant     → 餐飲業（WhatsApp 訂座）

/pricing         → 定價（3方案 + FAQs）
/demo            → 預約示範（Cal.com）
/blog            → 博客
/faq             → 常見問題
/about           → 關於我們
/skills-library  → 全部技能包目錄（SEO頁）
/compare         → 與 ChatGPT / Superchat 比較
```

### 7.2 關鍵「WhatsApp」設計決策
- Hero 區：展示手機 WhatsApp 對話截圖（真實感）
- 功能說明：全部用 WhatsApp 對話氣泡展示
- 「越用越識你」Section：時間軸展示（Day1 vs Day90 對比）
- CTA：「立即連接你的 WhatsApp」（唔係「免費試用」）

---

## 8. 技術架構

### 8.1 前端技術棧
```
Nuxt 4 (Vue 3)
├── @nuxt/ui v4          → UI 組件
├── @nuxtjs/i18n         → 多語言（zh-hk / en）
├── @nuxt/content        → 博客 + 技能包文件
├── @nuxt/image          → 圖片優化
├── @nuxtjs/seo          → SEO
├── Pinia                → 狀態（定價 toggle 等）
└── Tailwind CSS v4      → 樣式
```

### 8.2 後端（Nitro + Cloudflare）
```
server/api/
├── contact.post.ts      → 聯絡表單 → Resend Email
├── demo.post.ts         → Demo 預約
└── newsletter.post.ts   → 電郵訂閱
```

### 8.3 第三方服務
| 服務 | 用途 |
|------|------|
| Cloudflare Pages | 靜態部署 + Edge Functions |
| Resend | 電郵發送 |
| Cal.com | Demo 預約 |
| Stripe | 訂閱付款（Phase 2）|
| GA4 + Hotjar | 流量 + 行為分析 |

---

## 9. Nuxt.js 開發規格

### 9.1 核心 nuxt.config.ts

```typescript
export default defineNuxtConfig({
  compatibilityDate: '2025-07-15',
  future: { compatibilityVersion: 4 },

  modules: [
    '@nuxt/ui',
    '@nuxtjs/i18n',
    '@nuxt/content',
    '@nuxt/image',
    '@nuxtjs/seo',
    '@pinia/nuxt',
    '@vueuse/nuxt',
  ],

  i18n: {
    locales: [
      { code: 'zh-hk', iso: 'zh-HK', file: 'zh-hk.json', name: '廣東話' },
      { code: 'en',    iso: 'en-HK', file: 'en.json',    name: 'English' },
    ],
    defaultLocale: 'zh-hk',
    strategy: 'prefix_except_default',
    lazy: true,
    langDir: 'i18n/locales/',
    detectBrowserLanguage: {
      useCookie: true,
      cookieKey: 'area2_locale',
      redirectOn: 'root',
    },
    vueI18n: './i18n/i18n.config.ts',
  },

  site: {
    url: 'https://area2ai.hk',
    name: 'Area2 AI',
    description: '住喺你 WhatsApp 入面的 AI — 越用越識你的業務',
  },

  css: ['~/assets/css/main.css'],
  ssr: true,
  nitro: { preset: 'cloudflare-pages' },
})
```

### 9.2 i18n 翻譯核心鍵值（zh-hk.json）

```json
{
  "nav": {
    "features": "功能",
    "pricing": "定價",
    "useCases": "使用場景",
    "blog": "博客",
    "demo": "預約示範",
    "connect": "連接 WhatsApp"
  },
  "hero": {
    "badge": "🇭🇰 香港第一個 WhatsApp AI 幫手",
    "title": "你 WhatsApp 它，它幫你做嘢",
    "titleHighlight": "越用越識你",
    "subtitle": "唔使裝 App、唔使改習慣——直接喺 WhatsApp 用 AI。永久記憶你的業務，主動幫你跟進。",
    "cta": "連接你的 WhatsApp",
    "ctaSecondary": "睇 2 分鐘示範 ▶",
    "socialProof": "已有 {count} 間香港企業使用"
  },
  "painPoints": {
    "title": "你嘅 WhatsApp 每日係咁？",
    "items": {
      "overflow": {
        "title": "WhatsApp 回唔切",
        "desc": "每日 100+ 訊息，自己回到手軟，一唔小心就漏咗重要客"
      },
      "voiceMsg": {
        "title": "語音訊息播極都播唔完",
        "desc": "廣東話語音訊息一段 3 分鐘，要自己播晒先知講咩"
      },
      "afterHours": {
        "title": "下班後仲係響",
        "desc": "晚上 10 點收到查詢，無人回，客人去左競爭對手"
      },
      "noMemory": {
        "title": "AI 唔記得你",
        "desc": "每次用 ChatGPT 都要重新解釋公司背景，用極都唔識你"
      }
    }
  },
  "howItWorks": {
    "title": "三步驟，即刻開始",
    "steps": {
      "connect": {
        "num": "01",
        "title": "連接你的 WhatsApp",
        "desc": "掃描 QR Code，30 秒完成設定"
      },
      "tell": {
        "num": "02",
        "title": "告訴 AI 你的業務",
        "desc": "用廣東話介紹你的公司、產品、常見問題"
      },
      "work": {
        "num": "03",
        "title": "AI 開始幫你做嘢",
        "desc": "從今日起，AI 喺 WhatsApp 自動幫你處理、提醒、跟進"
      }
    }
  },
  "memory": {
    "title": "越用越識你——不只是 AI，而是你的數字孖生",
    "day1": "第 1 日",
    "day30": "第 30 日",
    "day90": "第 90 日",
    "day1Desc": "一個聰明的 AI",
    "day30Desc": "一個識你業務的 AI",
    "day90Desc": "一個幾乎係你數字孖生的 AI",
    "moat": "用了 3 個月後，AI 已記住你的客戶、習慣、SOP——轉用其他工具要從頭教過，用戶根本唔捨得走"
  },
  "pricing": {
    "title": "簡單透明定價",
    "toggle": {
      "monthly": "月付",
      "yearly": "年付",
      "save": "慳 17%"
    },
    "currency": "HK$",
    "period": "/月",
    "mostPopular": "最多人選",
    "plans": {
      "starter": {
        "name": "入門版",
        "price": { "monthly": 298, "yearly": 248 },
        "desc": "個人老闆 / 1–3人初創",
        "highlight": "WhatsApp DM + 基礎記憶",
        "cta": "免費試用 14 日"
      },
      "business": {
        "name": "商業版",
        "price": { "monthly": 888, "yearly": 738 },
        "desc": "5–20 人中小企",
        "highlight": "全渠道 + 完整記憶 + 業務自動化",
        "cta": "免費試用 14 日"
      },
      "enterprise": {
        "name": "企業版",
        "price": { "monthly": 2888, "yearly": 2398 },
        "desc": "20 人以上企業",
        "highlight": "多個專門 AI + 私有部署",
        "cta": "聯絡我們"
      }
    }
  }
}
```

### 9.3 WhatsApp Mockup 組件（核心視覺元素）

```vue
<!-- app/components/ui/WhatsAppChat.vue -->
<!-- 展示 AI 對話的手機 WhatsApp 截圖風格組件 -->
<template>
  <div class="relative max-w-[320px] mx-auto">
    <!-- 手機殼 -->
    <div class="bg-gray-900 rounded-[2.5rem] p-3 shadow-2xl">
      <!-- 狀態欄 -->
      <div class="bg-[#075E54] rounded-t-[2rem] px-4 py-3 flex items-center gap-3">
        <div class="w-8 h-8 bg-green-400 rounded-full flex items-center justify-center text-xs font-bold">A2</div>
        <div>
          <div class="text-white text-sm font-medium">Area2 AI</div>
          <div class="text-green-200 text-xs">在線</div>
        </div>
      </div>
      
      <!-- 對話區域 -->
      <div class="bg-[#ECE5DD] min-h-[400px] p-3 space-y-2 rounded-b-[2rem]">
        <!-- 用戶訊息 -->
        <div v-for="msg in messages" :key="msg.id"
             :class="msg.from === 'user' ? 'flex justify-end' : 'flex justify-start'">
          <div :class="[
            'max-w-[80%] rounded-lg px-3 py-2 text-sm shadow-sm',
            msg.from === 'user' 
              ? 'bg-[#DCF8C6] text-gray-800 rounded-tr-none'
              : 'bg-white text-gray-800 rounded-tl-none'
          ]">
            <p class="leading-relaxed whitespace-pre-wrap">{{ msg.text }}</p>
            <div class="text-[10px] text-gray-400 text-right mt-1">{{ msg.time }}</div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
interface Message {
  id: number
  from: 'user' | 'ai'
  text: string
  time: string
}

const props = defineProps<{ messages: Message[] }>()
</script>
```

---

## 10. 頁面設計細則

### 10.1 首頁設計（重點 Section）

#### Hero Section
```
[Badge] 🇭🇰 香港第一個 WhatsApp AI 幫手

H1: 你 WhatsApp 它，
    它幫你做嘢——
    [越用越識你] ← 漸層高亮

Subtitle: 唔使裝 App、唔使改習慣
          直接喺 WhatsApp 用 AI
          永久記憶你的業務，主動幫你跟進

[連接你的 WhatsApp]  [睇 2 分鐘示範 ▶]

右側：手機 WhatsApp 對話動畫
      (展示 AI 自動處理客戶查詢)

下方 Social Proof：
「✓ 香港本地團隊  ✓ 廣東話 AI  
 ✓ 14日免費試用  ✓ 無需信用卡」
```

#### 「越用越識你」Section（重點設計）
```
標題：不只是 AI——它是你的數字孖生

時間軸（橫向）：

Day 1          Day 30         Day 90
  ↓               ↓               ↓
聰明的 AI      識你業務的 AI   你的數字孖生
一般回答       用你嘅語氣      主動預測你嘅需要
               記住你客戶      幾乎唔需要指示
               自動用你格式

下方文字：
「用了 Area2 AI 3 個月的老闆說：
 『它比我秘書更識我的業務』」
```

#### 「它能做什麼」Section（WhatsApp 氣泡展示）
```
6 個 Tab，每個 Tab 展示一個 WhatsApp 對話場景：

Tab 1: 📱 自動回覆客戶
Tab 2: 🎙️ 語音轉行動事項
Tab 3: 📊 每日業務報告
Tab 4: 📄 分析你發來的文件
Tab 5: 🔍 市場情報搜集
Tab 6: ⏰ 智能提醒跟進
```

### 10.2 /compare 比較頁（SEO 強）

```
標題：Area2 AI vs ChatGPT vs Superchat

詳細比較表格（所有功能逐項比較）
+ 每個差異點的詳細解說

針對的搜索關鍵詞：
- "ChatGPT WhatsApp 整合"
- "香港 AI 助手比較"
- "Superchat 替代方案"
```

---

## 11. 多語言策略

### 語言優先級
1. **廣東話（zh-hk）** — 主要，預設，最詳細
2. **英文（en）** — 外資企業、國際客戶

### 廣東話口語策略
| Section | 語氣 | 例子 |
|---------|------|------|
| Hero / CTA | 廣東話口語 | 「幫你做嘢」「唔使改習慣」「越用越識你」|
| 功能說明 | 書面繁中 | 「支援廣東話語音識別，自動轉換為文字」|
| FAQ | 廣東話口語 | 「我唔識技術可以用嗎？」|
| 法律條款 | 純書面 | 正式中文 |

---

## 12. SEO 策略

### 目標關鍵詞（v2，WhatsApp 中心）

| 關鍵詞 | 月搜索量（估） | 優先級 |
|-------|------------|-------|
| WhatsApp AI 香港 | 高 | ⭐⭐⭐ |
| AI WhatsApp 自動回覆香港 | 高 | ⭐⭐⭐ |
| 香港中小企 AI 助手 | 高 | ⭐⭐⭐ |
| WhatsApp chatbot 香港 | 高 | ⭐⭐⭐ |
| 廣東話 AI 助手 | 中 | ⭐⭐ |
| ChatGPT WhatsApp 整合 | 中 | ⭐⭐ |
| AI 幫助回覆客戶 WhatsApp | 中 | ⭐⭐ |
| 香港 AI 自動化中小企 | 中 | ⭐⭐ |

### 內容行銷計劃（WhatsApp 主題）

| 文章 | 預計流量 |
|------|---------|
| 「2025 香港 WhatsApp AI 全攻略」| 高 |
| 「點樣用 AI 幫你回覆 WhatsApp（免費教學）」| 高 |
| 「ChatGPT 點解唔夠用——香港老闆最需要的 AI 係...」| 高 |
| 「WhatsApp Group AI 助手實測：節省了多少時間？」| 中 |
| 「廣東話 AI 大比拼：邊個最識香港人講嘢？」| 中 |

---

## 13. 開發路線圖

### Phase 1：MVP 網站（4–6 週）

**Week 1–2：基礎**
- [ ] 初始化 Nuxt 4 + UI + i18n
- [ ] 設計 Token（顏色、字體——WhatsApp 綠為品牌色）
- [ ] Header / Footer / Language Switcher
- [ ] Cloudflare Pages 部署 + `_headers` 設定

**Week 3–4：核心頁面**
- [ ] 首頁（全部 Sections，含 WhatsApp Mockup）
- [ ] 定價頁（月付/年付 Toggle + 比較表）
- [ ] /how-it-works 頁
- [ ] Demo 預約頁（Cal.com 整合）
- [ ] 聯絡頁

**Week 5–6：完善**
- [ ] 英文翻譯
- [ ] SEO meta + OG Image
- [ ] Mobile 優化
- [ ] Performance（Core Web Vitals）
- [ ] GA4 + Hotjar

### Phase 2：內容 + 轉化（2–4 週）
- [ ] 博客系統（@nuxt/content）
- [ ] /compare 比較頁
- [ ] /skills-library 技能包目錄
- [ ] 3 個行業 Use Case 頁
- [ ] 示範影片（2 分鐘，廣東話配音）

### Phase 3：商業化（持續）
- [ ] Stripe 訂閱整合
- [ ] 用戶 Dashboard
- [ ] 自助 Onboarding

---

## 14. 商業模型

### 14.1 收入預測

**Year 1（保守）：**

| 月份 | Starter | Business | Enterprise | MRR |
|------|---------|---------|------------|-----|
| M1–3 | 5 | 2 | 0 | HK$3,266 |
| M4–6 | 12 | 8 | 1 | HK$12,680 |
| M7–9 | 25 | 18 | 2 | HK$29,186 |
| M10–12 | 40 | 32 | 5 | HK$56,776 |

**Year 1 ARR 目標：HK$400,000+**

### 14.2 留客機制（越用越懂）

```
傳統 SaaS 流失原因：
- 用唔到效果 → 取消
- 找到更便宜替代 → 轉用

Area2 AI 獨有護城河：
- 用 3 個月 → AI 記住 1,000+ 條業務記憶
- 記住所有客戶習慣和偏好
- 轉用新 AI = 一切從零開始
- 用戶根本「轉不了」→ 極高留存率

預計 12 個月留存率：85%+（行業平均 75%）
```

### 14.3 增長槓桿
1. **口碑：** 轉介享 1 個月免費（介紹者同被介紹者各一個月）
2. **WhatsApp 病毒式傳播：** 其他人見到 Group 入面有 AI，自然問「呢個係咩？」
3. **政府資助：** 協助申請 AI 資助，降低採用門檻
4. **行業深耕：** 餐飲業 WhatsApp 訂座 + 零售業客服

---

## 附錄 A：競品定價詳細對比

| 功能 | ChatGPT Plus HK$156 | OperativeAI HK$488 | Superchat HK$840 | **Area2 AI HK$298** |
|------|---------------------|---------------------|------------------|---------------------|
| WhatsApp DM | ❌ | ❌ | ✅ | ✅ |
| WhatsApp Group | ❌ | ❌ | ✅ | ✅ |
| AI 記憶（向量）| ❌ | ❌ | ❌ | ✅ |
| 廣東話語音 | ⚠️ | ⚠️ | ❌ | ✅ |
| 主動推送 | ❌ | ❌ | ⚠️ | ✅ |
| 社媒監察 | ❌ | ❌ | ❌ | ✅ |
| 文件分析 | ✅ | ✅ | ❌ | ✅ |
| 越用越識你 | ❌ | ❌ | ❌ | ✅ |

## 附錄 B：技術能力清單（基於實際 Skills）

**已確認可用的 Skills（40+個）：**
- whatsapp-assistant, whatsapp-smart-reminder
- audio-handler（廣東話語音）
- social-scraper（小紅書/抖音/Instagram）
- stock-market（yFinance API）
- pdf-utils, docx-translator-v2, batch-image-processor
- minimax-tts, minimax-tts-async（廣東話 TTS）
- minimax-video, minimax-music, screen-to-script
- image-generation（Wanx AI）
- youtube-summarizer
- hktvmall, taobao-search
- lark-tasks, planka
- web-tester, qa-testing, bug-analyzer
- perplexity-search, web-research-citation
- marketing-research
- cms-manual-generator
- reminders, cron 系統

**記憶系統：** LanceDB（105+ 條，hybrid search）  
**多模型：** MiniMax M2.5 / Claude Sonnet / GPT-4o / Gemini

---

*v2 更新：WhatsApp 為核心賣點、越用越識你記憶策略、基於實際 Skills 的完整能力清單、用戶故事一天體驗、/compare 比較頁、留客護城河分析*
