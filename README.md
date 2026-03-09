# Area2 AI — AI 訂閱產品網站

> 香港中小企第一個真正執行任務的 AI 業務助手

## 項目概覽

本 Repo 儲存 Area2 AI 產品網站的計劃書、市場研究、及技術規格。

## 文件索引

| 文件 | 說明 |
|------|------|
| [01-marketing-research.md](docs/01-marketing-research.md) | 香港 AI 市場競爭分析、用戶痛點、定價研究 |
| [02-product-plan.md](docs/02-product-plan.md) | 完整產品計劃書、功能設計、訂閱方案、商業模型 |
| [03-technical-spec.md](docs/03-technical-spec.md) | Nuxt 4 + Vue i18n 開發技術規格 |

## 技術棧

- **前端框架：** Nuxt 4 (Vue 3)
- **UI 組件：** Nuxt UI v4 + Tailwind CSS v4
- **多語言：** @nuxtjs/i18n（廣東話、英文）
- **博客：** @nuxt/content
- **部署：** Cloudflare Pages
- **付款：** Stripe（計劃中）

## 快速開始（網站開發）

```bash
# 進入網站目錄（待建立）
cd area2-ai-website

# 安裝依賴
npm install

# 開發模式
npm run dev

# 建立生產版本
npm run build
```

## 目錄結構

```
area2-ai-product/
├── docs/
│   ├── 01-marketing-research.md    # 市場研究
│   ├── 02-product-plan.md          # 產品計劃書
│   └── 03-technical-spec.md        # 技術規格
├── area2-ai-website/               # 網站代碼（待建立）
│   ├── app/
│   ├── content/
│   ├── i18n/
│   ├── public/
│   └── nuxt.config.ts
└── README.md
```

## 路線圖

- [x] 市場研究完成
- [x] 產品計劃書完成
- [x] 技術規格完成
- [ ] Nuxt 網站初始化
- [ ] 首頁 MVP
- [ ] 定價頁
- [ ] i18n 廣東話 + 英文
- [ ] Cloudflare Pages 部署
- [ ] 博客系統

## 聯絡

**ErIc** — Area2 Limited  
Telegram: [@area2hk]

---

*由 A2 (B03) 撰寫，2026 年 3 月*
