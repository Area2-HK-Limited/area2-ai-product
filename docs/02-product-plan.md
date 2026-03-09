# 🚀 Area2 AI Assistant — 產品開發計劃書 (v3)
## 基於 OpenClaw 平台的香港中小企 AI 訂閱服務
## WhatsApp 原生 × 越用越識你 × 真正懂搜索 × 香港安全守護

**版本：** v4.0  
**日期：** 2026 年 3 月  
**撰寫：** A2 (B03) × ErIc  

---

## 目錄
1. [產品定義與核心賣點](#1-產品定義)
2. [普通人能理解的功能解說](#2-功能解說普通人版)
3. [四大革新賣點](#3-四大革新賣點)
4. [Skills 技能包 vs MCP 工具 — 點解你唔需要懂分別](#4-skills-vs-mcp)
5. [Vibe Coding — 唔識寫程式都可以叫 AI 幫你造功能](#5-vibe-coding)
6. [完整能力清單](#6-完整能力清單)
7. [用戶痛點對照](#7-用戶痛點對照)
8. [訂閱方案設計](#8-訂閱方案設計)
9. [用戶故事 — 一天用下來的體驗](#9-用戶故事)
10. [資料安全 × 信任背書](#10-資料安全)
11. [網站架構規劃](#11-網站架構規劃)
12. [技術架構](#12-技術架構)
13. [Nuxt.js 開發規格](#13-nuxtjs-開發規格)
14. [SEO 策略](#14-seo-策略)
15. [開發路線圖](#15-開發路線圖)
16. [商業模型](#16-商業模型)

---

## 1. 產品定義

### 一句話定位

> **「你 WhatsApp 它，它幫你做嘢——而且越用越識你。」**

### 產品名稱
- **Area2 AI**（主品牌）
- 廣東話 Tagline：「住喺你 WhatsApp 入面的 AI 幫手，越用越識你」
- 英文 Tagline：*Your AI that lives in WhatsApp and learns your business*

### 核心差異化

| 普通 AI 工具 | Area2 AI |
|------------|---------|
| 要開另一個 App | **直接喺 WhatsApp 用** |
| 每次用完即忘記你 | **永久記住你的業務** |
| 你問，它答（被動） | **主動幫你做嘢、提醒你** |
| 只有一個 AI 腦 | **多個專門 AI 同時出動** |
| 英文介面為主 | **廣東話語音、廣東話回覆** |
| 功能固定，要等更新 | **你可以「講出」新功能叫它學** |
| 數據放外國伺服器 | **數據存香港，受 PDPO 保護** |
| AI 靠估，答案可能過時 | **Perplexity 即時搜索，有根有據附來源** |

---

## 2. 功能解說（普通人版）

> ⚠️ 本節故意用「日常語言」描述技術功能，避免 IT 術語。適合直接用於網站文案、廣告、銷售對話。

---

### 功能 A：「定時管家」（技術名：Cron Job）

**一般 AI 怎麼運作：**
```
你開 ChatGPT → 你問 → 它答 → 你關掉 → 它睡著
第二天：它完全唔記得你昨天問過咩
下班後：它不存在
```

**Area2 AI 的「定時管家」：**
```
你設定一次："每日早上 8 點，WhatsApp 我今日的待辦事項"
→ 之後每天，不需要你問，它自動 WhatsApp 你

你設定一次："每週一整理上週的客戶查詢摘要"
→ 每週一，你準時收到報告，什麼都不用做

你設定一次："監察 HKTVMall 競品價格，有變動通知我"
→ 24 小時靜默監察，有動靜即 WhatsApp 你
```

**比喻：** 就像請了一個唔需要食飯、唔需要放假、唔需要提醒的管家，24 小時按你的指示自動工作。

**真實使用例子：**
- 📊 每日早 8 點 WhatsApp 昨日銷售摘要
- 📅 每週一整理本週待跟進客戶清單
- ✈️ 每日自動查機票/酒店價格，平了通知你
- 📈 股票到達指定價位，即時 WhatsApp 你
- ⏰ 客戶合約到期前 30 日提醒你跟進
- 📝 凌晨自動處理大量數據，早上準備好等你查看

---

### 功能 B：「多個專員同時出動」（技術名：Multi-Agent System）

**一般 AI 怎麼運作：**
```
你問 ChatGPT：「幫我做一份市場研究報告」
→ 它用一個腦袋，一步一步做，等很久
→ 複雜的任務可能做不完或做得不夠全面
```

**Area2 AI 的「多個專員同時出動」：**
```
你說：「幫我做一份香港茶飲市場研究」
→ AI 自動拆解任務：
   專員 A：研究競爭對手（同時出動）
   專員 B：分析消費者口味趨勢（同時出動）
   專員 C：收集社交媒體數據（同時出動）
   專員 D：研究香港法規及申請手續（同時出動）
→ 四個同時進行，完成後交回主腦整合
→ 速度快 3–5 倍，內容更全面
```

**比喻：** 就像派出 4 個不同專業的顧問同時去做調查，再由你的 PA 整合成一份報告——而不是讓一個人逐一去做。

**真實使用例子：**
- 📊 大型市場研究（多個搜索線同時進行）
- 🔍 全面 QA 測試網站（桌面版、手機版、平板版同時測）
- 📄 批量處理 100 張發票圖片（分批同時 OCR）
- 🎯 競品分析（同時研究多個競爭對手）

---

### 功能 C：「無限記憶本」（技術名：Vector Memory Database）

**一般 AI 怎麼運作：**
```
ChatGPT 的記憶 = 便利貼（有限張數）：
- 記住你叫「陳生」
- 記住你係做貿易
- 記住你有間公司叫「XX 貿易」
→ 便利貼貼滿了，要刪舊的才能加新的
→ 唔識主動「聯想」，只係死記幾個事實
```

**Area2 AI 的「無限記憶本」：**
```
向量記憶 = 一個有理解力的助理：
- 不只記住「你做貿易」
- 更理解「你主要客係中東市場、
          通常週三確認訂單、
          李生那邊信用期 60 天、
          你對質量問題零容忍」
→ 下次你說「李生的訂單問題」
   AI 自動聯想到李生的完整背景
→ 越用越了解你，越來越準確
→ 容量：500條（入門）至 無限（企業版）
```

**比喻：** ChatGPT 的記憶是靜態的「通訊錄」；Area2 AI 的記憶是懂得理解上下文、會主動聯想的「老員工腦袋」。

---

### 功能 D：「技能包外掛」（技術名：Skills System）

**一般 AI 怎麼運作：**
```
ChatGPT 的能力 = 出廠時裝好，無法添加
想要新功能？→ 等 OpenAI 更新（可能等半年）
```

**Area2 AI 的「技能包外掛」：**
```
就像手機 App Store：
→ 需要查 HKTVMall 競品？→ 安裝「HKTVMall 監察」技能
→ 需要翻譯 Word 文件？→ 安裝「文件翻譯」技能
→ 需要生成廣東話語音？→ 安裝「語音生成」技能
→ 現有 40+ 個技能包，持續增加
→ 企業版可以「訂製」你獨有的技能
```

---

### 功能 E：「即時連線工具」（技術名：MCP Tools）

**與技能包的分別（普通人版）：**

```
技能包（Skills）= 已打包好的工作流程
就像「購買一個已裝好的廚房電器」
→ 買回來裝上，即用
→ 功能固定但強大
→ 例：HKTVMall 監察 Skill = 自動搜索+比價+通知

MCP 工具 = 即插即用的「萬能插頭」
就像「一個萬用介面，可接各種設備」
→ 讓 AI 直接操控外部軟件/服務
→ 例：接上 Google Maps → AI 可直接查地圖
       接上 Gmail → AI 可讀你的 Email
       接上 Playwright → AI 可操控網頁瀏覽器
```

**實際例子：**
| 場景 | 用技能包 | 用 MCP 工具 |
|------|---------|-----------|
| 分析競品網站 | ✅ `web-tester` Skill | ✅ Playwright MCP（直接操控瀏覽器）|
| 搜索市場資訊 | ✅ `perplexity-search` Skill | ✅ Perplexity MCP（直接接 API）|
| 操控 Google Maps | 無現成 Skill | ✅ Google Maps MCP |
| 讀取 Notion 文件 | 無現成 Skill | ✅ Notion MCP |

**簡單說：** 技能包係「已整合好的解決方案」；MCP 係「讓 AI 連接任何外部工具的橋樑」。**你不需要懂分別——遇到唔識搞的問題，問 Area2 AI，它會告訴你用哪種方法解決。**

---

### 功能 F：「有根有據的搜索員」（技術名：Perplexity AI 整合）

**為什麼一般 AI 的答案有時不可靠：**
```
ChatGPT / Claude / Gemini 的問題：
→ 用「訓練數據」回答，知識有截止日期
→ 遇到不確定的事，AI 可能「估」一個答案
→ 沒有引用來源，你無法核實
→ 結果：回答聽起來很確信，但實際可能過時或錯誤
  （業界叫做「AI 幻覺」）
```

**Area2 AI 整合 Perplexity 之後：**
```
每次遇到需要準確事實的查詢：
→ 自動調用 Perplexity API 即時搜索網絡
→ 整合多個可信來源
→ 回答時附上引用連結，你可以自行核實
→ 數據永遠是最新的

例子：
你問：「香港最低工資現在係幾多？」
普通 AI：「HK$40/小時」（可能已過時）
Area2 AI：「根據勞工處 2025 年最新公告：
           法定最低工資為 HK$XX/小時（自 XXXX 年起）
           → 來源：香港勞工處官方網站 [連結]」
```

**三個能力疊加 = Marketing Research 的底氣：**
```
1️⃣ Perplexity → 即時搜索，確保數據最新、有來源
2️⃣ Multi-Agent → 多個 AI 專員同時從不同角度搜索
3️⃣ MBA 框架 Skill → Porter's Five Forces、SWOT、PESTEL
                     把原始數據轉化成有商業洞察的分析

三者結合 = 原本外判 HK$20,000–50,000 的市場研究
          Area2 AI 幾小時內完成，有理有據可引用
```

**適合：** 所有人，尤其係需要查法規/政策/市場數據、做競品研究、需要事實核查的場景

---

## 3. 五大革新賣點

### 賣點 1：WhatsApp 原生（最低門檻 AI 採用）
→ [見 USP 詳細分析於競品比較文件]

### 賣點 2：越用越識你（記憶護城河）
→ [見 USP 詳細分析於競品比較文件]

### 賣點 3：Vibe Coding — 唔識 IT 都可以創造自己的 AI 工具
→ [見下方第 5 節詳細說明]

### 賣點 4：真正懂搜索——Perplexity 整合，有根有據

**一句話：** 其他 AI 靠估；Area2 AI 先搜尋、再核實、後回答——每個答案都有來源連結。

**為什麼重要：**
- ChatGPT 的知識有截止日期，可能過時幾個月
- AI「幻覺」問題：聽起來很確信，實際可能錯誤
- 業務決策用了錯誤數據，直接造成損失

**Area2 AI 的做法：**
- 整合 Perplexity AI API（全球最強 AI 搜索引擎之一）
- 事實類查詢自動即時搜索網絡，確保最新
- 回答附引用連結，可自行點擊核實
- 多個 AI 專員 + Perplexity + 分析框架 = Marketing Research 能力

### 賣點 5：資料安全 × Hostlink 20 年信任
→ [見詳細安全白皮書 05-security-trust.md]

---

## 4. Skills vs MCP 深度解說

### 何時用 Skills（技能包）

**適合場景：** 需要完整業務流程的自動化，功能預先整合好

| Skill 名稱 | 功能 | 業務場景 |
|-----------|------|---------|
| `whatsapp-assistant` | WhatsApp DM + Group 全面管理 | 客服自動化 |
| `social-scraper` | 小紅書/抖音/Instagram 爬蟲 | 競品/KOL 監察 |
| `stock-market` | 即時港股數據（yFinance）| 投資/業務相關股 |
| `hktvmall` | HKTVMall 產品搜索及監察 | 零售競品比價 |
| `taobao-search` | Taobao 搜索比價 | 採購參考 |
| `pdf-utils` | PDF 文字提取 + OCR | 合約/發票分析 |
| `docx-translator-v2` | Word 文件格式保留翻譯 | 中英文件翻譯 |
| `minimax-tts` | 廣東話 TTS 語音生成 | 客服語音/語音通知 |
| `minimax-video` | AI 影片生成 | 廣告/社媒內容 |
| `screen-to-script` | 錄屏 → 廣東話配音 | 產品示範影片 |
| `audio-handler` | 廣東話語音 → 行動事項 | 會議整理 |
| `youtube-summarizer` | YouTube 影片提取重點 | 培訓/競品研究 |
| `lark-tasks` | 飛書/Lark 任務管理 | 項目跟進 |
| `image-generation` | AI 圖片生成（阿里雲 Wanx）| 社媒配圖 |
| `web-tester` | 自動化網頁 QA 測試 | IT/軟件公司 |
| `marketing-research` | MBA 級市場研究框架 | 市場進入分析 |
| `batch-image-processor` | 批量圖片/PDF 處理 | 大量單據/發票 |
| `cms-manual-generator` | 自動生成 CMS 操作手冊 | 新員工培訓 |
| `reminders` | 智能提醒系統 | 任何定期提醒 |
| `cloudflare-deploy` | 網站自動部署 | IT/開發公司 |
| `perplexity-search` | AI 搜索引擎（有引用）| 任何市場調查 |

**現有 40+ 個技能包，持續增加中。**

### 何時用 MCP 工具

**適合場景：** 需要 AI 直接操控外部軟件或平台

| MCP 工具 | 功能 | 例子 |
|---------|------|------|
| Playwright Browser | 控制真實瀏覽器 | 自動填表、截圖、抓取動態網頁 |
| Perplexity | 直接接 AI 搜索 API | 即時網絡搜索 |
| Google Maps | 查地圖/地點資訊 | 找附近競店 |
| Notion | 讀寫 Notion 數據庫 | 同步業務筆記 |
| GitHub | 管理代碼庫 | 開發公司用 |
| Filesystem | 讀寫本地文件 | 處理本地文件 |

**用戶唔需要選擇：** 告訴 Area2 AI 你要做咩，它自動選用最合適的 Skill 或 MCP 工具。

---

## 5. Vibe Coding — 唔識寫程式都可以創造自己的 AI 功能

### 什麼是 Vibe Coding？

「Vibe Coding」係 2025 年最熱門的新概念——由 OpenAI 創辦人 Andrej Karpathy 提出：

> **用自然語言描述你想要的功能，讓 AI 幫你寫程式。**

傳統做法：想要一個功能 → 要請程式員（貴、慢、需要溝通）  
Vibe Coding：想要一個功能 → 直接用廣東話告訴 AI → AI 幫你做出來

### Area2 AI 的 Vibe Coding 實例

**場景 1：零售店想監察競品**
```
你（WhatsApp 告訴 Area2 AI）：
「我想每日自動搜尋 HKTVMall 上面同我賣一樣的洗髮水
 有冇新上架、有冇減價，整理成報告 WhatsApp 我」

Area2 AI：
「明白！我幫你建立一個定時監察功能，每日早上 9 點
 自動搜尋 HKTVMall，包括：
 1. 同類洗髮水新上架
 2. 你指定的 3 個競品有冇改價
 3. 整合成摘要 WhatsApp 你
 現在開始嗎？」

你：「開始」

Area2 AI：（自動建立 Skill + Cron）
「✅ 已設定！明天早上 9 點你會收到第一份報告。」
```

→ **全程不需要任何 IT 知識，不需要請程式員**

---

**場景 2：餐廳想自動整理訂座**
```
你：「我想每次有人 WhatsApp 訂座，
     AI 自動記錄日期、時間、人數、聯絡方式
     然後每日早上 WhatsApp 我今日的訂座清單」

Area2 AI：（自動建立訂座處理流程）
「好！我幫你建立訂座管理系統：
 1. 客人 WhatsApp 訂座訊息 → 自動提取資料儲存
 2. 自動回覆確認訊息給客人
 3. 每日早 8 點發今日訂座清單給你
 試用一下？」
```

---

**場景 3：貿易公司想自動整理供應商報價**
```
你：「每次供應商 Email 發報價單過來
     我想 AI 自動提取產品名稱、單價、最少訂量
     整理成 Excel，WhatsApp 我」

Area2 AI：（建立 Email + 文件處理流程）
「我幫你建立一個報價單自動化流程：
 1. 監察指定 Email 的附件
 2. OCR 提取報價數據
 3. 整理成 Excel 表格
 4. WhatsApp 你，附帶摘要
 需要哪個 Email 地址？」
```

### Vibe Coding 的界限

| 可以做 | 需要澄清 |
|--------|---------|
| 建立定時任務 | 涉及第三方 API 密鑰（需你提供）|
| 整合現有技能包 | 全新業務邏輯（可能需要更多描述）|
| 自動化重複流程 | 涉及你公司系統的 API 整合 |
| 處理文件、圖片、數據 | 高度定製化業務流程（Enterprise 服務）|

**不懂沒關係：** 遇到任何情況，直接告訴 Area2 AI「我想做 X」——它會告訴你能否做到，或者建議最接近的方案。

---

## 6. 完整能力清單

### 基礎能力（所有方案）

**💬 WhatsApp 原生**
- DM 個人助手模式（24/7 在線）
- Group 群組協作模式
- 語音訊息廣東話自動轉文字
- 圖片/截圖理解及分析
- PDF/Word/Excel 接收分析
- 主動提醒（定時推送到 WhatsApp）
- 自動回覆（可設定範本及條件）

**🧠 記憶系統**
- 向量記憶庫（語義理解式儲存）
- 業務背景永久記憶
- 客戶歷史及偏好記憶
- 每日自動整理新記憶（凌晨 4 點執行）
- 跨 Session 記憶延續
- 容量：500條（Starter）/ 5,000條（Business）/ 無限（Enterprise）

**⏰ 定時管家（Cron）**
- 每日/每週/每月定時任務
- 指定時間主動 WhatsApp 報告
- 業務監察（持續自動執行）
- 最多：3個（Starter）/ 20個（Business）/ 無限（Enterprise）

---

### 技能包清單（按類別）

#### 📊 市場情報（Perplexity 驅動）
- **Perplexity AI 搜索** ⭐ — 即時網絡搜索，回答附引用來源，確保準確不過時
- 社交媒體爬蟲（小紅書/抖音/Instagram/微博/B站）
- 即時股票市場數據
- MBA 級市場研究框架（Porter's Five Forces、SWOT、PESTEL 等）
- YouTube 影片內容提取

> **Perplexity 的角色：** 所有需要事實核查的查詢，Area2 AI 自動調用 Perplexity API——不靠 AI「估」，而是即時搜索最新網絡資料，附可點擊的來源連結。這也是 Area2 AI 具備 Marketing Research 能力的核心技術基礎。

#### 🛒 電商 & 採購
- HKTVMall 產品搜索及監察
- Taobao 搜索比價

#### 📄 文件處理
- PDF 文字提取 + 繁中英 OCR
- Word 文件格式保留翻譯（中英）
- 批量圖片/PDF 處理
- 自動生成 CMS 操作手冊

#### 🎙️ 語音 & 媒體
- 廣東話 TTS 語音生成
- 長篇文章轉有聲版
- 廣東話語音訊息轉行動事項
- AI 影片生成（MiniMax）
- 錄屏轉廣東話配音影片
- AI 作曲填詞

#### 🖼️ 圖像生成
- AI 圖片生成（阿里雲 Wanx）
- AI 圖片生成（MiniMax 風格）

#### 🔧 業務工具
- 飛書/Lark 任務管理
- 智能提醒系統
- WhatsApp 標準化工作流
- 項目看板管理（Planka）
- 自動化網頁 QA 測試

#### 🤖 AI 協作
- Sub-Agent 多個專員並行系統
- 多模型調度（MiniMax/Claude/GPT/Gemini）
- Bug 自動分析報告
- 網站部署自動化

---

## 7. 用戶痛點對照

| 痛點 | 舊方法 | Area2 AI 方案 |
|------|--------|--------------|
| WhatsApp 回唔切 | 自己回/請人 | 自動篩選 + 建議回覆 / 自動回覆 |
| 語音訊息聽唔完 | 自己播 | 廣東話自動轉文字 + 摘要 |
| 開會後冇人跟進 | Email 無人理 | 語音 → 行動清單 → 分配 → 定時提醒 |
| AI 唔記得你 | 每次重新解釋 | 向量記憶庫，越用越識你 |
| 下班後漏接客 | 無 | 24/7 WhatsApp 自動回覆 |
| 競品動態追唔到 | 人手搜索 | 定時自動爬社交媒體 + WhatsApp 摘要 |
| 股市/市場資訊 | 自己查 App | 每日自動推送 WhatsApp |
| PDF 合約要分析 | 自己讀 | 發 PDF → AI 即時解讀重點 |
| 文件要中英翻譯 | 人手翻譯 | Word 格式保留自動翻譯 |
| 廣告影片太貴 | 外包製作 | AI 生成影片 / 錄屏配廣東話音 |
| HKTVMall 競品 | 人手定期搜索 | 自動監察 + 價格通知 |
| 採購 Taobao 比價 | 人手上網 | 自動搜索比價報告 |
| 項目任務無人跟進 | 口頭/Email | Lark 任務自動創建 + 提醒 |
| 想要特定功能 | 請程式員（貴）| Vibe Coding：講出來 AI 幫你做 |
| 數據安全憂慮 | 用美國 AI 唯有接受 | 香港伺服器 + PDPO + ISO 27001 |
| **AI 答案唔準確/過時** | **自己 Google 核實** | **Perplexity 即時搜索，附來源連結** |
| **做市場研究太貴** | **外判 HK$20,000+** | **Multi-Agent + Perplexity，幾小時完成** |
| **不確定法規/政策** | **自己查政府網站** | **即時搜索官方來源，30 秒有答案** |

---

## 8. 訂閱方案設計

### 🌱 Starter（入門版）HK$298/月

**年付：HK$248/月（慳 17%）**  
**適合：** 個人老闆、自由職業者、1–3 人初創

| 功能 | 包含 |
|------|------|
| WhatsApp DM | ✅ 24/7 個人助手 |
| WhatsApp Group | ❌ |
| 記憶容量 | 500 條 |
| 每月對話 | 500 次 |
| 定時管家（Cron） | 3 個任務 |
| AI 語音訊息轉文字 | ✅ 100 次/月 |
| 基礎技能包 | 3 個（提醒、搜索、文件）|
| 主動 WhatsApp 推送 | ✅ |
| AI 模型 | 1 個（快速模型）|
| 技術支援 | Email，3 個工作日 |

---

### 💼 Business（商業版）HK$888/月 ⭐ 最多人選

**年付：HK$738/月（慳 17%）**  
**適合：** 5–20 人中小企、零售店、服務業、Agency

| 功能 | 包含 |
|------|------|
| WhatsApp DM + Group | ✅ 全部 |
| Telegram + Discord | ✅ |
| 記憶容量 | 5,000 條 |
| 每月對話 | 3,000 次 |
| 定時管家（Cron） | 20 個任務 |
| AI 語音訊息轉文字 | ✅ 無限 |
| 技能包 | 全部基礎 + 5 個進階 |
| 社交媒體監察 | ✅ 小紅書/Instagram |
| 文件翻譯 | ✅ 中英 |
| 股票/市場資訊 | ✅ |
| 圖片生成 | ✅ 100 次/月 |
| 廣東話 TTS 語音 | ✅ 500 次/月 |
| 多個專員並行（Sub-Agent）| 3 個同時 |
| AI 模型 | 3 個切換 |
| Vibe Coding 支援 | ✅ |
| 技術支援 | WhatsApp 即時（週一至六）|
| 設定服務 | 2 小時 1-on-1 |

---

### 🏢 Enterprise（企業版）HK$2,888/月起

**適合：** 20 人以上企業、連鎖店、金融機構、IT 公司

| 功能 | 包含 |
|------|------|
| 全部 Business 功能 | ✅ |
| 記憶容量 | 無限 |
| 對話次數 | 無限 |
| 定時管家（Cron） | 無限 |
| 多個專門 AI | ✅（客服 AI、行銷 AI、財務 AI）|
| **私有部署** | ✅ 數據唔離開公司 |
| 多個 WhatsApp 帳號 | ✅ |
| 客製化 Vibe Coding | ✅ 專人協助 |
| 訂製 MCP 工具整合 | ✅ |
| 專屬客戶成功經理 | ✅ |
| SLA 99.9% 保證 | ✅ |
| PDPO 合規架構 | ✅ 文件提供 |

---

### 增值服務

| 服務 | 定價 |
|------|------|
| 基礎設定服務 | HK$800（一次）|
| 深度設定服務 | HK$2,500（一次）|
| 客製化 Skill 開發 | HK$5,000 起 |
| 額外對話次數 | HK$100 / 1,000 次 |
| 電商監察 Add-on | HK$200/月 |

---

## 9. 用戶故事——陳生的一天

### 20 人貿易公司老闆的真實一天

```
07:30 AM — 起床，WhatsApp 一開
  Area2 AI：「早安陳生！
            ├── 3 條客戶查詢（草稿已備好，確認後發出？）
            ├── 今日待辦 2 項（美麗華訂單、李生付款追跟）
            └── 今日港股：你持倉相關股份 ↑1.2%」

08:30 AM — 錄一段廣東話語音備忘（剛想到的事）
  Area2 AI 自動：
  廣東話語音 → 轉文字 → 整理行動事項 → 加入 Lark 任務

10:00 AM — 開完同供應商的會
  陳生（Group）：「@Area2AI 整理下啱啱嘅會議內容」
  Area2 AI：「✅ 會議重點：
            1. 訂單確認 → 陳生 → 今日內
            2. 更新報價 → 小明 → 週三前
            3. 跟進付款 → 阿芬 → 本週五
            提醒已設定，時間到自動通知各人」

12:30 PM — 自動推送
  Area2 AI：「📊 今日市場摘要：
            • 你採購品類原材料 ↑3%（需要調整報價？）
            • 競品 X 公司昨在小紅書發佈新品
            • HKTVMall：你同類產品有 2 款減價」

03:00 PM — 客戶發來英文合約 PDF（23 頁）
  Area2 AI：「已分析合約：
            🔴 第 8 條：付款期限 15 日（比一般短）
            🟡 第 12 條：自動續約，需提前 30 日通知
            🟢 整體條款標準，無異常」

06:00 PM — 下班
  Area2 AI：「好！我繼續監察 WhatsApp。
            明早 7:30 再整理今日未處理事項。
            祝晚安！」

10:30 PM — 新客戶深夜查詢
  Area2 AI 自動回覆：
  「您好！陳生的 AI 助手已收到您的查詢，
   他明早會親自跟進，感謝您的耐心！」
   （同時 WhatsApp 通知陳生，讓他決定要唔要即時回）
```

**結果：**
- ⏱️ 每日節省 2–3 小時 WhatsApp 處理時間
- 💰 零深夜漏客（AI 24/7 在線）
- 🧠 所有客戶決定自動記錄
- 📊 每日市場情報不用自己搜索

---

## 10. 資料安全 × 信任背書

> **詳細安全白皮書見 `05-security-trust.md`**

### 核心承諾（三行版）

1. **數據在香港** — 三大雲端（AWS / Alibaba Cloud / Tencent Cloud）全部香港數據中心
2. **認證齊全** — ISO 27001、CSA STAR、SOC 2、HKSAR 金融行業審計
3. **Hostlink 背書** — 香港本地公司，20+ 年伺服器管理經驗，本地廣東話支援

### 三大雲端認證概覽

| 認證 | AWS HK | Alibaba HK | Tencent HK |
|------|--------|-----------|-----------|
| ISO 27001:2022 | ✅ | ✅ | ✅ |
| CSA STAR | ✅ | ✅ Gold | ✅ Gold |
| SOC 2 | ✅ | — | — |
| HKSAR 金融監管 | ✅ | — | ✅ HKMA+SFC+HKIA |
| PCI DSS | ✅ Level 1 | ✅ | — |

### PDPO 合規
- 數據儲存香港（受香港法律管轄，唔係美國 CLOUD Act）
- 唔出售、唔共享、唔用於訓練外部 AI 模型
- 可隨時申請完全刪除帳戶及所有數據
- 每個客戶數據完全隔離（Tenant Isolation）

### 常見疑慮解答（摘要）

| 疑慮 | 答案 |
|------|------|
| 「你係新公司」 | Hostlink 係香港 20+ 年 IT 公司，唔係初創 |
| 「我的數據會唔會被拿去用？」 | 絕對唔會——不用於訓練 AI，不出售給第三方 |
| 「萬一系統出問題？」 | 三大雲端備援，每日自動備份，多地儲存 |
| 「ChatGPT 都係雲端，點解你安全啲？」 | ChatGPT 伺服器在美國，受美國法律；我們在香港 |
| 「萬一你哋公司結業？」 | 可隨時導出全部數據，數據屬於你 |

---

## 11. 網站架構規劃

### 頁面地圖（v3，加入安全 Trust 頁）

```
/ (首頁)
├── #hero          → WhatsApp 示範 + 一句話定位
├── #pain-points   → 「你的 WhatsApp 每日係咁？」
├── #how-it-works  → 3 步驟：連接→說話→AI做嘢
├── #features      → 功能展示（普通人語言版）
├── #memory        → 越用越識你（Day1→Day90 時間軸）
├── #vibe-coding   → 「唔識 IT 都可以創造功能」
├── #trust         → 安全認證 + Hostlink 背景
├── #pricing       → 定價（3方案）
├── #testimonials  → 用戶心聲
└── #cta           → 免費 14 日試用

/features/whatsapp      → WhatsApp 深度功能頁
/features/memory        → 越用越識你詳解
/features/automation    → 定時管家詳解
/features/vibe-coding   → Vibe Coding 詳解 ⭐ 新增
/features/security      → 安全白皮書網頁版 ⭐ 新增

/use-cases/retail       → 零售/連鎖店
/use-cases/trade        → 貿易公司
/use-cases/agency       → 數碼營銷 Agency
/use-cases/professional → 專業服務（會計/律師）
/use-cases/restaurant   → 餐飲（WhatsApp 訂座）

/pricing                → 完整定價頁
/trust                  → 安全認證完整頁 ⭐ 新增
/compare                → vs ChatGPT / Superchat 比較
/skills-library         → 技能包完整目錄
/vibe-coding-guide      → Vibe Coding 操作指南 ⭐ 新增
/demo                   → 預約示範
/blog                   → 博客
/faq                    → 常見問題（含安全 FAQ）
```

### 首頁 Trust Section 設計

```
標題：「你的業務數據，永遠在你控制之下」

左：
[Hostlink 20+ 年 IT 經驗]
[香港本地公司 · 廣東話支援]
[辦公室：九龍旺角]

中：數據流向圖
你的 WhatsApp → Area2 AI → 🇭🇰 香港數據中心

右：認證標誌牆
[ISO 27001] [CSA STAR] [SOC 2] [PCI DSS]
[AWS Partner] [Alibaba Cloud] [Tencent Cloud]
[PDPO Compliant]

底部：
「了解我們的安全架構 →」（連結 /trust 頁）
```

---

## 12. 技術架構

### 前端技術棧

```
Nuxt 4 (Vue 3)
├── @nuxt/ui v4
├── @nuxtjs/i18n          → 廣東話（預設）+ 英文
├── @nuxt/content         → 博客 + 技能庫文件
├── @nuxt/image           → 圖片優化
├── @nuxtjs/seo           → SEO
├── Pinia                 → 定價 Toggle 狀態
└── Tailwind CSS v4
```

### 後端（Nitro + Cloudflare）

```
server/api/
├── contact.post.ts       → 聯絡表單 → Resend Email
├── demo.post.ts          → Demo 預約
└── newsletter.post.ts    → 電郵訂閱
```

### 部署

- Cloudflare Pages（GitHub push 觸發，唔用 wrangler deploy）
- `public/_headers`：no-cache 設定（防 CF 邊緣快取問題）
- `public/_redirects`：SPA routing
- 同 clock-practice 相同部署模式

---

## 13. Nuxt.js 開發規格

### 核心 nuxt.config.ts

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

### 廣東話翻譯 i18n 核心鍵值（新增 Vibe Coding + Security）

```json
{
  "vibeCoding": {
    "badge": "🆕 2025 最新概念",
    "title": "唔識寫程式，都可以叫 AI 幫你造功能",
    "subtitle": "Vibe Coding——用廣東話描述你想要的，Area2 AI 幫你實現",
    "example1": {
      "user": "我想每日自動搜尋競品，WhatsApp 我",
      "ai": "✅ 已建立！明天早 9 點開始自動運行。"
    },
    "example2": {
      "user": "每次有人訂座，自動記錄並每日 WhatsApp 我清單",
      "ai": "✅ 訂座管理系統已建立，包含自動確認回覆。"
    },
    "cta": "用廣東話告訴我你想要咩"
  },
  "security": {
    "title": "你的業務數據，永遠在你控制之下",
    "badge": "🇭🇰 香港本地公司 · 20+ 年 IT 經驗",
    "dataLocation": "數據儲存香港",
    "dataLocationDesc": "AWS / Alibaba Cloud / Tencent Cloud 香港數據中心",
    "certs": "ISO 27001 · CSA STAR · SOC 2 · PDPO 合規",
    "hostlink": "由 Hostlink (HK) 營運——香港超過 20 年伺服器管理經驗",
    "learnMore": "查看完整安全認證 →"
  },
  "automationFeature": {
    "title": "定時管家",
    "subtitle": "唔需要你問，它自動幫你做",
    "desc": "設定一次，AI 24 小時自動執行——報告、提醒、監察、跟進，全部自動",
    "examples": [
      "每日早 8 點 WhatsApp 你業務摘要",
      "競品有動靜即時通知",
      "客戶合約到期前自動提醒",
      "凌晨自動處理數據，早上等你查看"
    ]
  },
  "multiAgent": {
    "title": "多個專員同時出動",
    "subtitle": "複雜任務，多個 AI 腦並行處理",
    "desc": "一般 AI 一次只做一件事；Area2 AI 可以同時派出多個專員，速度快 3–5 倍"
  }
}
```

---

## 14. SEO 策略（v3）

### 新增關鍵詞（Vibe Coding + Security）

| 關鍵詞 | 搜索意圖 |
|-------|---------|
| vibe coding 香港 | 新興詞彙，早佔 |
| AI 幫我寫程式香港 | Vibe Coding 普通人搜索 |
| 香港 AI 助手資料安全 | 安全考量搜索 |
| PDPO AI 合規香港 | 企業合規搜索 |
| 香港伺服器 AI 助手 | 本地化搜索 |
| WhatsApp AI 香港安全 | WhatsApp + 安全組合 |

### 博客文章（新增）

| 文章 | 目標關鍵詞 |
|------|----------|
| 「Vibe Coding 係咩？香港老闆點用 AI 造自己的工具」 | vibe coding 香港 |
| 「唔識 IT 都係 IT 老闆——用廣東話叫 AI 幫你寫功能」 | AI 幫我寫程式 |
| 「ChatGPT 係美國 AI——香港老闆的數據安全在哪裡？」 | 香港 AI 資料安全 |
| 「ISO 27001、CSA STAR 係咩？香港老闆要了解的 AI 安全認證」 | PDPO AI 合規 |
| 「香港 Hostlink 20 年——為什麼老牌 IT 公司做 AI 更可信？」 | 香港 IT 公司 AI |

---

## 15. 開發路線圖

### Phase 1：MVP 網站（4–6 週）

**Week 1–2：基礎 + 安全頁**
- [ ] Nuxt 4 + UI + i18n 初始化
- [ ] 設計 Token（WhatsApp 綠為品牌色）
- [ ] Header / Footer / Language Switcher
- [ ] /trust 安全頁（認證標誌 + Hostlink 介紹）
- [ ] Cloudflare Pages 部署 + `_headers` + `_redirects`

**Week 3–4：核心頁面**
- [ ] 首頁（含 Vibe Coding Section + Trust Section）
- [ ] 定價頁（月付/年付 Toggle + 比較表）
- [ ] /features/vibe-coding 詳解頁
- [ ] Demo 預約頁（Cal.com）
- [ ] FAQ（含安全 FAQ）

**Week 5–6：完善**
- [ ] 英文翻譯
- [ ] SEO meta + OG Image
- [ ] Mobile 優化
- [ ] GA4 + Hotjar

### Phase 2：內容（2–4 週）
- [ ] 博客系統
- [ ] /compare 比較頁
- [ ] /skills-library 技能包目錄
- [ ] /vibe-coding-guide 操作指南
- [ ] 5 個 Use Case 頁

---

## 16. 商業模型

### 收入預測（Year 1，保守）

| 月份 | Starter | Business | Enterprise | MRR |
|------|---------|---------|------------|-----|
| M1–3 | 5 | 2 | 0 | HK$3,266 |
| M4–6 | 12 | 8 | 1 | HK$12,680 |
| M7–9 | 25 | 18 | 2 | HK$29,186 |
| M10–12 | 40 | 32 | 5 | HK$56,776 |

**Year 1 ARR 目標：HK$400,000+**

### 留客護城河

```
普通 SaaS：「功能好用就留，唔好用就走」（流失率 25-30%/年）

Area2 AI 的護城河：
→ 用 3 個月後，AI 記住 1,000+ 條業務記憶
→ 記住所有客戶歷史、SOP、偏好
→ Vibe Coding 造了幾個自定功能
→ 轉用其他 AI = 全部記憶歸零，重新教過
→ 用戶根本「轉不了」→ 估計 85%+ 留存率
```

---

*v3 更新：普通人語言版功能解說、Vibe Coding 賣點、MCP vs Skills 分別、三大雲端安全認證（AWS/Alibaba/Tencent）、Hostlink 背景、資料安全 FAQ、/trust 頁面設計、SEO 新增安全/Vibe Coding 關鍵詞*
