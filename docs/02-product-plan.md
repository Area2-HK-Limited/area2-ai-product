# 🚀 Area2 AI Assistant — 產品開發計劃書
## 基於 OpenClaw 平台的香港中小企 AI 訂閱服務

**版本：** v1.0  
**日期：** 2026 年 3 月  
**撰寫：** A2 (B03) × ErIc  
**狀態：** 草稿

---

## 目錄
1. [產品定義與願景](#1-產品定義與願景)
2. [用戶痛點對照功能表](#2-用戶痛點對照功能表)
3. [產品能力清單](#3-產品能力清單)
4. [訂閱方案設計](#4-訂閱方案設計)
5. [網站架構規劃](#5-網站架構規劃)
6. [技術架構](#6-技術架構)
7. [Nuxt.js 開發規格](#7-nuxtjs-開發規格)
8. [頁面設計細則](#8-頁面設計細則)
9. [多語言策略](#9-多語言策略)
10. [SEO 策略](#10-seo-策略)
11. [開發路線圖](#11-開發路線圖)
12. [商業模型](#12-商業模型)

---

## 1. 產品定義與願景

### 1.1 一句話定位
> **「香港第一個會主動幫你做嘢的 AI 幫手——唔只係問答，而係真正執行任務。」**

### 1.2 產品名稱建議
- **Area2 AI**（主品牌）
- 副標題：智能業務自動化平台
- 英文：*Area2 AI — Your Always-On Business Agent*

### 1.3 核心差異化
| 普通 AI 工具 | Area2 AI |
|------------|---------|
| 你問，它答 | **它主動幫你做嘢** |
| 每次 Session 忘記你 | **永久記住你的業務背景** |
| 只能在網頁用 | **WhatsApp / Telegram / Discord 都得** |
| 只有一個 AI | **多個 AI 腦並行（分工合作）** |
| 需要自己設定 | **我哋幫你度身設定** |
| 英文介面 | **廣東話 AI + 繁體中文** |

### 1.4 產品願景
成為香港中小企最得力的「數字員工」——24 小時在線、永不請病假、永遠記得你公司的事、自動處理重複工作，讓老闆和員工專注更有價值的事。

---

## 2. 用戶痛點對照功能表

| 用戶痛點 | 現有解決 | Area2 AI 方案 | 使用的能力 |
|---------|---------|--------------|-----------|
| 每日大量 WhatsApp 回覆佔用時間 | 自己回 / 請人 | AI 自動篩選、分類、建議回覆甚至自動回 | WhatsApp 整合 + 自動化 |
| 下班後客戶訊息無人跟進 | 無 | 24/7 在線，自動接收並回應或記錄 | Heartbeat 機制 + 多渠道 |
| 每次 AI 都要重新介紹公司背景 | 重複輸入 prompt | 永久記憶（公司簡介、產品、SOP） | Milvus 向量記憶庫 |
| 不同工具資訊分散（Email、Sheet、WhatsApp） | 人手整合 | 跨工具資料搜集、整合、總結 | Skills 系統 + API 整合 |
| 想用 AI 但不懂 prompt | 買咗唔識用 | 度身定製 prompt，用戶只需自然語言指令 | 客製化設定服務 |
| 需要整理、撰寫報告 | 人手打字 | AI 自動生成報告、摘要、提案 | LLM + 文件處理 |
| 招聘廣告、內容創作耗時 | 自己寫/外包 | AI 生成符合品牌語氣的文案 | 多模型 + 品牌記憶 |
| 需要追蹤競爭對手/市場情報 | 人手搜索 | 定期自動搜集、整理、通知 | Web Search + Cron 任務 |
| 多語言客戶（中英文混用） | 人手翻譯 | 即時翻譯、自動切換語言回覆 | 多語言 LLM |
| 員工培訓 SOP 文件無效 | 印出來冇人睇 | AI 成為「活的 SOP」，隨時問隨時答 | RAG + 文件上傳 |
| 安排會議、跟進事項靠人腦 | Google Calendar | AI 自動提醒、安排、跟進 | Calendar 整合 + Cron |
| 發票/報價單需人手處理 | Excel 打字 | OCR + AI 提取資料、自動填表 | PDF 處理 + 文件 Skills |
| 社交媒體需要每日更新 | 人手創作 | AI 生成貼文、安排發佈 | 社交媒體 Skills |
| 開會後行動項目無人跟進 | Email 發出去冇人理 | 語音轉文字 + 自動生成行動清單 + 分配 | STT + Task 管理 |

---

## 3. 產品能力清單

### 3.1 核心能力（所有方案包含）

#### 🧠 智能記憶系統
- **業務背景記憶：** 公司名稱、產品、客戶、SOP、行業術語
- **跨 Session 記憶：** 上次討論的項目自動記起
- **人員記憶：** 記住重要客戶、員工、合作夥伴的偏好和歷史
- **技術：** Milvus 向量資料庫 + Hybrid Search（向量 70% + BM25 關鍵詞 30%）

#### 📱 多渠道接入
- **WhatsApp Business：** 接收/發送訊息、自動回覆、群組管理
- **Telegram：** Bot 形式，支援命令、群組、媒體
- **Discord：** 企業群組協作
- **Web Chat：** 嵌入式聊天窗口
- **Email（計劃中）：** Gmail / Outlook 整合

#### ⚙️ 任務執行引擎
- **Cron 定時任務：** 定期執行、報告、提醒
- **Sub-Agent 系統：** 複雜任務自動拆解、並行處理
- **Web 搜索：** 即時獲取最新資訊
- **文件處理：** PDF、Word、Excel 讀取分析
- **截圖/視覺分析：** 分析圖片、截圖、設計稿

#### 🎯 廣東話優先
- AI 回覆預設廣東話書面語
- 理解廣東話俚語和商業用語
- 支援繁體中文 + 英文切換

### 3.2 進階能力（商業版及以上）

#### 🤖 多 AI 模型調度
| 任務類型 | 推薦模型 | 原因 |
|---------|---------|------|
| 日常問答、快速回覆 | MiniMax M2.5 | 速度快、成本低 |
| 複雜分析、長文件 | Claude Sonnet/Opus | 理解能力強 |
| 代碼、數據分析 | GPT-4o | 邏輯能力強 |
| 圖像生成 | Wanx / DALL-E | 創意內容 |
| 語音轉文字 | Qwen-Omni | 廣東話準確 |

#### 📊 業務整合
- **Google Workspace：** Gmail、Calendar、Docs、Sheets
- **Microsoft 365：** Outlook、Teams、OneDrive
- **CRM：** HubSpot、Salesforce（透過 API）
- **會計系統：** Xero、QuickBooks（透過 API）
- **電商：** Shopify、WooCommerce 訂單監控
- **Lark/飛書：** 任務管理、文件協作

#### 🛠️ Skills 技能包系統
技能包是可安裝的功能模組，擴展 AI 能力：

| 技能包名稱 | 功能 | 適合行業 |
|-----------|------|---------|
| **社交媒體管家** | 自動爬取競品內容、生成貼文建議 | 全行業 |
| **客服機械人** | 自動回覆 FAQ、升級複雜查詢 | 零售、服務業 |
| **合約分析師** | 閱讀合約、標記風險條款 | 貿易、法律 |
| **市場情報員** | 每日自動搜集行業新聞、競品動態 | 全行業 |
| **會議記錄員** | 語音轉文字 + 行動清單 | 全行業 |
| **招聘助手** | 篩選履歷、生成面試問題 | 全行業 |
| **SEO 顧問** | 分析網站、建議優化策略 | 數碼營銷 |
| **QA 測試員** | 自動測試網頁、生成報告 | 科技公司 |

### 3.3 企業版能力

#### 🏢 多 Agent 架構
- 可設定多個專門 AI（如：客服 AI、行銷 AI、財務 AI）
- 每個 AI 有獨立記憶和工作空間
- AI 之間可以協作、互相傳遞任務

#### 🔒 私隱和安全
- 自架部署選項（數據不離開公司）
- 符合香港《個人資料（私隱）條例》
- 角色權限管理（員工只能存取授權 AI）
- 完整操作日誌

---

## 4. 訂閱方案設計

### 4.1 方案詳情

---

### 🌱 Starter（入門版）
**HK$298/月**（年付 HK$248/月）

**適合：** 自由職業者、1–3人初創

| 功能 | 包含 |
|------|------|
| AI 渠道 | Telegram 或 WhatsApp（選一） |
| 記憶容量 | 500 條記憶 |
| 每月對話次數 | 500 次 |
| AI 模型 | 1 個模型（MiniMax） |
| Skills 技能包 | 基礎 3 個 |
| Sub-Agents | 無 |
| 定時任務（Cron） | 3 個 |
| 技術支援 | Email，3 個工作日回覆 |
| 設定服務 | 自助設定（文件指引） |

---

### 💼 Business（商業版）
**HK$888/月**（年付 HK$738/月）

**適合：** 5–20人中小企

| 功能 | 包含 |
|------|------|
| AI 渠道 | WhatsApp + Telegram + Discord（全部） |
| 記憶容量 | 5,000 條記憶 |
| 每月對話次數 | 3,000 次 |
| AI 模型 | 3 個模型切換（MiniMax + Claude + GPT） |
| Skills 技能包 | 全部基礎技能 + 3 個進階技能 |
| Sub-Agents | 最多 3 個並行 |
| 定時任務（Cron） | 20 個 |
| 業務整合 | Google Workspace / Microsoft 365 |
| 技術支援 | 即時 WhatsApp 支援（週一至六） |
| 設定服務 | 2 小時 1-on-1 設定服務 |
| 廣東話 TTS | 500 次/月 |

---

### 🏢 Enterprise（企業版）
**HK$2,888/月起**（按需報價）

**適合：** 20人以上企業、連鎖店

| 功能 | 包含 |
|------|------|
| AI 渠道 | 全渠道 + 自訂整合 |
| 記憶容量 | 無限 |
| 每月對話次數 | 無限 |
| AI 模型 | 全部模型 + 自訂微調 |
| Skills 技能包 | 全部 + 客製化開發 |
| Sub-Agents | 無限並行 |
| 定時任務（Cron） | 無限 |
| 部署方式 | 雲端或自架（私有部署） |
| 業務整合 | 全部 + API 客製化 |
| Agent 數量 | 多個專門 AI（客服、行銷、財務...） |
| 支援 | 專屬客戶成功經理 |
| SLA | 99.9% 在線率保證 |

---

### 4.2 增值服務（Add-ons）

| 服務 | 定價 | 說明 |
|------|------|------|
| 設定服務（基礎） | HK$800 一次性 | 2 小時設定 + 培訓 |
| 設定服務（深度） | HK$2,500 一次性 | 全天設定 + 流程設計 |
| 客製化 Skill 開發 | HK$5,000 起 | 按需開發專屬功能 |
| 額外對話次數 | HK$100/1,000次 | 超額使用 |
| 緊急支援 | HK$500/小時 | SLA 以外緊急協助 |
| 月度健康報告 | 免費（企業版） | AI 使用分析報告 |

---

## 5. 網站架構規劃

### 5.1 頁面結構

```
/ (首頁)
├── /features (功能介紹)
│   ├── /features/memory (永久記憶)
│   ├── /features/channels (多渠道)
│   ├── /features/automation (自動化)
│   └── /features/skills (技能包)
├── /pricing (定價)
├── /use-cases (使用場景)
│   ├── /use-cases/retail (零售)
│   ├── /use-cases/agency (Marketing Agency)
│   ├── /use-cases/trade (貿易公司)
│   └── /use-cases/professional-services (專業服務)
├── /blog (博客)
├── /about (關於我們)
├── /contact (聯絡)
├── /demo (預約示範)
├── /faq (常見問題)
└── /legal
    ├── /legal/privacy (私隱政策)
    └── /legal/terms (服務條款)
```

### 5.2 多語言版本
```
/                    → 自動偵測（預設廣東話）
/zh-hk/              → 廣東話（香港）
/zh-tw/              → 繁體中文（台灣）
/en/                 → 英文
```

---

## 6. 技術架構

### 6.1 前端技術棧

```
Nuxt 4 (Vue 3)
├── @nuxt/ui (UI 組件庫)
├── @nuxtjs/i18n (多語言)
├── @nuxt/content (博客/文件)
├── @nuxt/image (圖片優化)
├── @nuxtjs/seo (SEO 工具)
├── Pinia (狀態管理)
├── VueUse (Composables)
└── Tailwind CSS v4
```

### 6.2 後端（最小化）

```
Nitro (Nuxt 內置)
├── /api/contact (聯絡表單)
├── /api/demo (預約示範)
└── /api/newsletter (訂閱電郵)
```

### 6.3 第三方服務

| 服務 | 用途 | 費用 |
|------|------|------|
| Cloudflare Pages | 靜態部署 | 免費 |
| Cloudflare R2 | 圖片存儲 | 幾乎免費 |
| Resend | 電郵發送 | 免費層夠用 |
| Stripe | 訂閱付款 | 2.9% + HK$2.35/筆 |
| Cal.com | 預約 Demo | 免費（自架或雲端） |
| Google Analytics 4 | 流量分析 | 免費 |
| Hotjar | 用戶行為 | 免費層可用 |

### 6.4 部署架構

```
GitHub (Source Code)
    ↓ Git Push
Cloudflare Pages (自動部署)
    ├── 靜態資源 CDN
    ├── Edge Functions (API)
    └── R2 Storage (媒體)
```

---

## 7. Nuxt.js 開發規格

### 7.1 目錄結構

```
area2-ai-website/
├── app/
│   ├── assets/
│   │   ├── css/
│   │   │   └── main.css          # Tailwind + 自訂樣式
│   │   └── images/               # 靜態圖片
│   ├── components/
│   │   ├── landing/
│   │   │   ├── HeroSection.vue   # 首頁 Hero
│   │   │   ├── PainPoints.vue    # 用戶痛點
│   │   │   ├── Features.vue      # 功能展示
│   │   │   ├── Pricing.vue       # 定價表
│   │   │   ├── Testimonials.vue  # 客戶見證
│   │   │   ├── FAQ.vue           # 常見問題
│   │   │   └── CTA.vue           # 行動號召
│   │   ├── layout/
│   │   │   ├── AppHeader.vue     # 頂部導航
│   │   │   ├── AppFooter.vue     # 底部
│   │   │   └── LanguageSwitcher.vue
│   │   └── ui/
│   │       ├── PricingCard.vue   # 定價卡片
│   │       ├── FeatureCard.vue   # 功能卡片
│   │       └── UseCaseCard.vue   # 場景卡片
│   ├── composables/
│   │   ├── useI18nHelper.ts      # i18n 工具函數
│   │   └── usePricing.ts         # 定價邏輯
│   ├── layouts/
│   │   ├── default.vue           # 預設佈局
│   │   └── landing.vue           # 落地頁佈局
│   ├── pages/
│   │   ├── index.vue             # 首頁
│   │   ├── features/
│   │   │   └── index.vue
│   │   ├── pricing.vue           # 定價頁
│   │   ├── use-cases/
│   │   │   └── [slug].vue        # 動態場景頁
│   │   ├── blog/
│   │   │   ├── index.vue         # 博客列表
│   │   │   └── [slug].vue        # 博客文章
│   │   ├── demo.vue              # 預約示範
│   │   ├── faq.vue               # FAQ
│   │   └── contact.vue           # 聯絡
│   └── plugins/
│       └── analytics.client.ts   # GA4 初始化
├── content/
│   ├── blog/
│   │   ├── zh-hk/               # 廣東話博客
│   │   └── en/                  # 英文博客
│   └── faq/
│       ├── zh-hk.yml
│       └── en.yml
├── i18n/
│   ├── locales/
│   │   ├── zh-hk.json            # 廣東話翻譯
│   │   ├── zh-tw.json            # 繁中翻譯
│   │   └── en.json               # 英文翻譯
│   └── i18n.config.ts
├── public/
│   ├── _headers                  # Cloudflare 快取控制
│   ├── _redirects                # SPA 路由
│   ├── robots.txt
│   └── sitemap.xml
├── server/
│   └── api/
│       ├── contact.post.ts       # 聯絡表單
│       └── demo.post.ts          # 預約 Demo
├── nuxt.config.ts
├── tailwind.config.ts
└── package.json
```

### 7.2 nuxt.config.ts 核心配置

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
  ],
  
  // i18n 設定
  i18n: {
    locales: [
      { code: 'zh-hk', iso: 'zh-HK', file: 'zh-hk.json', name: '廣東話' },
      { code: 'zh-tw', iso: 'zh-TW', file: 'zh-tw.json', name: '繁體中文' },
      { code: 'en',    iso: 'en-HK', file: 'en.json',    name: 'English' },
    ],
    defaultLocale: 'zh-hk',
    strategy: 'prefix_except_default',  // / = 廣東話，/en/ = 英文
    detectBrowserLanguage: {
      useCookie: true,
      cookieKey: 'area2_locale',
      redirectOn: 'root',
    },
    vueI18n: './i18n/i18n.config.ts',
  },
  
  // SEO
  site: {
    url: 'https://area2ai.hk',
    name: 'Area2 AI',
    description: '香港中小企 AI 業務助手',
  },
  
  // 靜態部署
  ssr: true,
  nitro: {
    preset: 'cloudflare-pages',
  },
  
  // 顏色模式
  colorMode: { preference: 'light' },
  
  // CSS
  css: ['~/assets/css/main.css'],
})
```

### 7.3 i18n 翻譯鍵結構

```json
// i18n/locales/zh-hk.json
{
  "nav": {
    "features": "功能",
    "pricing": "定價",
    "useCases": "使用場景",
    "blog": "博客",
    "demo": "預約示範",
    "login": "登入"
  },
  "hero": {
    "badge": "香港首創 AI 業務助手",
    "title": "你的 AI 幫手，真係會幫你做嘢",
    "subtitle": "唔只係問答——WhatsApp 即回、自動整理、永久記憶、24 小時在線",
    "cta": "免費試用 14 日",
    "ctaSecondary": "睇示範"
  },
  "painPoints": {
    "title": "你係咪有以下問題？",
    "items": {
      "whatsapp": {
        "title": "WhatsApp 回唔切",
        "desc": "每日 100+ 訊息，自己回到手軟，一唔小心就漏咗重要客"
      },
      "memory": {
        "title": "AI 唔記得你",
        "desc": "每次用 ChatGPT 都要重新解釋公司背景，浪費時間"
      },
      "offline": {
        "title": "下班客戶仲問嘢",
        "desc": "晚上 10 點收到查詢，無人回覆，客人轉去競爭對手"
      },
      "tools": {
        "title": "工具太多太散",
        "desc": "Email、WhatsApp、Excel、Google Doc... 資訊到處都係"
      }
    }
  },
  "features": {
    "title": "Area2 AI 點解決",
    "memory": {
      "title": "永久記憶你的業務",
      "desc": "記住你的公司、產品、客戶、SOP——唔使每次重頭講"
    },
    "channels": {
      "title": "WhatsApp + Telegram 齊上",
      "desc": "用你慣用的渠道溝通，唔使改變工作習慣"
    },
    "automation": {
      "title": "真正執行任務",
      "desc": "唔只答問題——幫你搵資料、整報告、發提醒、排會議"
    },
    "cantonese": {
      "title": "廣東話 AI",
      "desc": "用廣東話溝通，理解香港商業用語和文化"
    }
  },
  "pricing": {
    "title": "簡單透明定價",
    "monthly": "每月",
    "yearly": "每年",
    "savePercent": "慳 {percent}%",
    "mostPopular": "最多人選",
    "plans": {
      "starter": {
        "name": "入門版",
        "price": "298",
        "desc": "自由職業者 / 初創適用",
        "cta": "立即開始"
      },
      "business": {
        "name": "商業版",
        "price": "888",
        "desc": "5–20人中小企",
        "cta": "免費試用 14 日"
      },
      "enterprise": {
        "name": "企業版",
        "price": "2,888",
        "desc": "20人以上企業",
        "cta": "聯絡我們"
      }
    }
  },
  "cta": {
    "title": "準備好讓 AI 幫你做嘢？",
    "subtitle": "14 日免費試用，無需信用卡",
    "button": "立即免費試用"
  },
  "footer": {
    "tagline": "香港中小企最得力的數字員工",
    "product": "產品",
    "company": "公司",
    "legal": "法律",
    "copyright": "© {year} Area2 Limited. 版權所有。"
  }
}
```

---

## 8. 頁面設計細則

### 8.1 首頁設計（index.vue）

#### Section 1: Hero
```
[上方導航：Logo | 功能 | 定價 | 場景 | [預約示範 CTA Button]]

Hero 區域：
- Badge：「🇭🇰 香港第一個 AI 業務助手」
- H1：你的 AI 幫手，真係會幫你做嘢
- Subtitle：唔只係問答——WhatsApp 即回、自動整理、永久記憶、24 小時在線
- CTA 主按鈕：「免費試用 14 日」
- CTA 次按鈕：「睇 2 分鐘示範 ▶」
- 右側：AI 聊天界面 Mockup（展示 WhatsApp 自動回覆場景）

Social Proof Bar：
「已有 [XXX] 間香港企業使用 | 4.9★ 用家評分 | 14日免費試用」
```

#### Section 2: 痛點（Pain Points）
```
標題：「你係咪有以下問題？」
4個痛點卡片（圖標 + 標題 + 描述）：
1. 📱 WhatsApp 回唔切
2. 🧠 AI 唔記得你
3. 🌙 下班後客戶仲問嘢
4. 🗂️ 工具太多太散

→ 過渡：「Area2 AI 一個解決晒」
```

#### Section 3: 功能展示
```
標籤式展示（每個功能有示範 GIF/截圖）：
Tab 1: 永久記憶 → 展示記憶如何運作
Tab 2: 多渠道 → WhatsApp + Telegram 示範
Tab 3: 任務執行 → 自動整理報告示範
Tab 4: 廣東話 AI → 廣東話對話示範
```

#### Section 4: 使用場景（Use Cases）
```
3 個場景卡片：
1. 貿易公司老闆 → AI 自動回客戶查詢 + 每日銷售摘要
2. Marketing Agency → AI 幫整 client report + 社媒帖文
3. 零售店 → AI 管理 WhatsApp Group + 處理投訴
```

#### Section 5: 定價
```
月付 / 年付 切換 Toggle
3個定價卡片（Starter / Business / Enterprise）
年付省 16% 提示
常見問題摺疊（FAQAccordion）
```

#### Section 6: 客戶見證
```
3–5 個真實客戶引言
（初期可用：「Beta 測試用家」）
```

#### Section 7: CTA
```
全寬 Banner：
「準備好讓 AI 幫你做嘢？」
「14 日免費試用，無需信用卡，隨時取消」
[立即免費試用] [預約 Demo]
```

### 8.2 定價頁設計細節

- 月付/年付 toggle（年付顯示節省百分比）
- Feature comparison table（所有方案詳細對比）
- FAQ accordion（付款、取消、升降級問題）
- 企業版 custom quote 表單

### 8.3 Demo 預約頁

- Cal.com 嵌入式日曆
- 表單：公司名、聯絡人、公司規模、主要痛點（多選）、偏好時間
- 預約後：自動 WhatsApp/Email 確認 + 前一天提醒

---

## 9. 多語言策略

### 9.1 語言優先級
1. **廣東話（zh-hk）** — 主要語言，預設語言，最詳細
2. **英文（en）** — 面向外資企業、國際客戶
3. **繁體中文（zh-tw）** — 方便台灣/新加坡市場（後期加）

### 9.2 廣東話 vs 書面中文策略
- **行銷文案（Hero、CTA）：** 廣東話口語（「做嘢」「唔使」「即刻」）
- **功能說明：** 書面繁體中文（正式、清晰）
- **FAQ：** 廣東話口語（貼近用戶表達方式）
- **法律條款：** 純書面文（正式）

### 9.3 SEO 多語言標籤
```html
<!-- 每頁 head 加入 hreflang -->
<link rel="alternate" hreflang="zh-HK" href="https://area2ai.hk/" />
<link rel="alternate" hreflang="en-HK" href="https://area2ai.hk/en/" />
<link rel="alternate" hreflang="x-default" href="https://area2ai.hk/" />
```

---

## 10. SEO 策略

### 10.1 目標關鍵詞

| 關鍵詞 | 搜索意圖 | 優先級 |
|-------|---------|-------|
| 香港 AI 助手 | 商業 | ⭐⭐⭐ |
| AI WhatsApp 自動回覆香港 | 商業 | ⭐⭐⭐ |
| 中小企 AI 自動化香港 | 商業 | ⭐⭐⭐ |
| Hong Kong AI business assistant | 商業 | ⭐⭐⭐ |
| ChatGPT 替代方案香港 | 比較 | ⭐⭐ |
| AI 幫手訂閱 | 商業 | ⭐⭐ |
| WhatsApp chatbot 香港 | 商業 | ⭐⭐ |
| 廣東話 AI | 資訊 | ⭐ |

### 10.2 內容行銷策略（博客）

**月度博客計劃（前 6 個月）：**

| 月份 | 文章主題 |
|------|---------|
| 1 | 香港中小企 AI 實戰指南（2025）|
| 1 | 點解你的 ChatGPT 幫唔到你的業務？|
| 2 | WhatsApp AI 自動回覆：實測對比 5 大工具 |
| 2 | 貿易公司如何用 AI 省下每月 80 小時 |
| 3 | AI 記憶系統是什麼？比 ChatGPT 強在哪裏？ |
| 3 | 香港政府 AI 資助懶人包（附申請步驟）|
| 4 | Marketing Agency 如何用 AI 同時服務 10 個客戶 |
| 5 | 廣東話 AI 大比拼：哪個最識廣東話？ |
| 6 | 6 個月回顧：Area2 AI 客戶成效報告 |

---

## 11. 開發路線圖

### Phase 1: MVP 網站（4–6 週）

**Week 1–2: 基礎建設**
- [ ] 初始化 Nuxt 4 項目
- [ ] 設定 Tailwind CSS v4 + Nuxt UI
- [ ] 設定 i18n（zh-hk + en）
- [ ] 建立基礎 Layout（Header + Footer）
- [ ] Cloudflare Pages 部署設定

**Week 3–4: 核心頁面**
- [ ] 首頁（Hero + 痛點 + 功能 + 定價 + CTA）
- [ ] 定價頁
- [ ] 聯絡頁 + API
- [ ] Demo 預約頁（Cal.com 整合）
- [ ] FAQ 頁

**Week 5–6: 完善**
- [ ] 英文翻譯完成
- [ ] SEO meta tags（每頁）
- [ ] OG Image 生成
- [ ] Performance 優化（Core Web Vitals）
- [ ] 手機版優化
- [ ] Analytics 整合

### Phase 2: 博客 + 內容（2–4 週）
- [ ] 設定 @nuxt/content
- [ ] 博客列表 + 文章頁
- [ ] 首 4 篇博客文章
- [ ] 使用場景頁（3 個垂直行業）
- [ ] 客戶案例頁（1–2 個）

### Phase 3: 轉化優化（持續）
- [ ] A/B 測試 Hero 文案
- [ ] Hotjar 熱圖分析
- [ ] 提升 CTA 點擊率
- [ ] 加入客戶見證（真實客戶）
- [ ] 示範視頻製作

### Phase 4: 商業化功能（後期）
- [ ] Stripe 訂閱付款整合
- [ ] 用戶 Dashboard（管理訂閱）
- [ ] 自助 Onboarding 流程
- [ ] Skills Marketplace 頁面

---

## 12. 商業模型

### 12.1 收入預測（保守估計）

**Year 1 目標：**

| 月份 | 客戶數 | MRR（月經常性收入） |
|------|--------|-------------------|
| M1–M3 | 5 | HK$3,490 |
| M4–M6 | 15 | HK$10,470 |
| M7–M9 | 35 | HK$24,430 |
| M10–M12 | 60 | HK$41,880 |

**Year 1 ARR 目標：HK$300,000+**

### 12.2 成本結構

| 成本項目 | 每月 | 備注 |
|---------|------|------|
| 伺服器（雲端） | HK$500–1,500 | 視用戶數量 |
| AI API 成本 | HK$1,000–5,000 | 視使用量 |
| 域名/SSL | HK$100 | 年付 |
| 行銷費用 | HK$2,000–5,000 | 初期 |
| 人工（ErIc + 兼職） | 視實際情況 | |

**目標毛利率：70%+**（SaaS 行業標準）

### 12.3 增長槓桿
1. **口碑轉介：** 每成功轉介一客，兩者各獲 1 個月免費
2. **行業垂直：** 深耕 1–2 個行業，建立口碑
3. **政府資助：** 協助客戶申請 AI 資助，降低採用門檻
4. **Channel Partner：** 與 IT 公司、會計師樓合作，代銷分成

---

## 附錄

### A. 技術資源
- OpenClaw 文件：https://docs.openclaw.ai
- Nuxt 文件：https://nuxt.com
- Nuxt UI：https://ui.nuxt.com
- @nuxtjs/i18n：https://i18n.nuxtjs.org

### B. 競品參考
- OperativeAI：https://operativeai.hk
- Superchat：https://superchat.com
- ChatGPT Team：https://chat.openai.com
- SkyBot：https://skywork.ai

### C. 香港 AI 資助資訊
- 數碼轉型支援先導計劃：https://www.digitisation.gov.hk
- BUD 專項基金：https://www.tid.gov.hk/bud
- 香港生產力局 HKPC：https://www.hkpc.org

---

*此計劃書由 A2 (B03) 撰寫，基於 2026 年 3 月市場研究數據。*  
*定期更新：每季度檢視一次，根據市場反饋調整策略。*
