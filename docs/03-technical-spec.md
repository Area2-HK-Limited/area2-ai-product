# 🌐 網站開發技術規格書
## Area2 AI — Nuxt 4 + Vue i18n 實作細節

**版本：** v1.0  
**日期：** 2026 年 3 月

---

## 1. 環境要求

```bash
Node.js >= 22.x
npm >= 10.x
Git
```

## 2. 項目初始化

```bash
# 建立 Nuxt 4 項目
npx nuxi@latest init area2-ai-website
cd area2-ai-website

# 安裝核心模組
npx nuxi module add ui          # @nuxt/ui (含 Tailwind v4)
npx nuxi module add i18n        # @nuxtjs/i18n
npx nuxi module add content     # @nuxt/content
npx nuxi module add image       # @nuxt/image
npx nuxi module add seo         # @nuxtjs/seo

# 其他依賴
npm install @pinia/nuxt pinia @vueuse/nuxt
```

## 3. nuxt.config.ts 完整配置

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

  // i18n
  i18n: {
    locales: [
      {
        code: 'zh-hk',
        iso: 'zh-HK',
        file: 'zh-hk.json',
        name: '廣東話',
        dir: 'ltr',
      },
      {
        code: 'en',
        iso: 'en-HK',
        file: 'en.json',
        name: 'English',
        dir: 'ltr',
      },
    ],
    defaultLocale: 'zh-hk',
    strategy: 'prefix_except_default',
    lazy: true,
    langDir: 'i18n/locales/',
    detectBrowserLanguage: {
      useCookie: true,
      cookieKey: 'area2_locale',
      redirectOn: 'root',
      cookieSecure: true,
    },
    vueI18n: './i18n/i18n.config.ts',
    compilation: {
      strictMessage: false, // 允許 HTML in messages
    },
  },

  // SEO
  site: {
    url: 'https://area2ai.hk',
    name: 'Area2 AI',
    description: '香港中小企 AI 業務助手 — 永久記憶、多渠道、真正執行任務',
    defaultLocale: 'zh-hk',
    indexable: true,
  },

  // Nuxt UI
  ui: {
    global: true,
    icons: ['heroicons', 'lucide', 'simple-icons'],
  },

  // Image
  image: {
    cloudflare: {
      baseURL: 'https://area2ai.hk',
    },
    quality: 85,
    format: ['webp', 'avif'],
  },

  // Content
  content: {
    highlight: {
      theme: 'github-dark',
    },
  },

  // App config
  app: {
    head: {
      htmlAttrs: { lang: 'zh-HK' },
      charset: 'utf-8',
      viewport: 'width=device-width, initial-scale=1',
    },
    pageTransition: { name: 'page', mode: 'out-in' },
  },

  // Color mode
  colorMode: {
    preference: 'light',
    fallback: 'light',
    classSuffix: '',
  },

  // CSS
  css: ['~/assets/css/main.css'],

  // SSR + Nitro
  ssr: true,
  nitro: {
    preset: 'cloudflare-pages',
    prerender: {
      routes: ['/', '/pricing', '/features', '/faq', '/en', '/en/pricing'],
    },
  },

  // Runtime Config
  runtimeConfig: {
    // Server-only
    resendApiKey: process.env.RESEND_API_KEY,
    calApiKey: process.env.CAL_API_KEY,
    // Public
    public: {
      siteUrl: 'https://area2ai.hk',
      gaMeasurementId: process.env.GA_MEASUREMENT_ID,
    },
  },

  // Dev tools
  devtools: { enabled: true },
})
```

## 4. 核心組件實作

### 4.1 LanguageSwitcher.vue

```vue
<template>
  <UDropdown :items="localeItems" :popper="{ placement: 'bottom-end' }">
    <UButton variant="ghost" size="sm" :label="currentLocaleName" 
             trailing-icon="i-heroicons-chevron-down-20-solid" />
  </UDropdown>
</template>

<script setup lang="ts">
const { locale, locales, setLocale } = useI18n()
const switchLocalePath = useSwitchLocalePath()

const currentLocaleName = computed(() => 
  locales.value.find(l => l.code === locale.value)?.name ?? locale.value
)

const localeItems = computed(() =>
  [locales.value.map(l => ({
    label: l.name,
    click: () => setLocale(l.code),
    icon: locale.value === l.code ? 'i-heroicons-check' : undefined,
  }))]
)
</script>
```

### 4.2 PricingCard.vue

```vue
<template>
  <UCard
    :class="[
      'relative flex flex-col',
      popular && 'ring-2 ring-primary-500',
    ]"
  >
    <div v-if="popular" 
         class="absolute -top-4 left-1/2 -translate-x-1/2">
      <UBadge color="primary" size="lg">
        {{ $t('pricing.mostPopular') }}
      </UBadge>
    </div>
    
    <template #header>
      <div class="text-center space-y-2">
        <h3 class="text-lg font-bold">{{ name }}</h3>
        <p class="text-sm text-gray-500">{{ desc }}</p>
        <div class="text-4xl font-black text-gray-900">
          HK$<span>{{ displayPrice }}</span>
          <span class="text-base font-normal text-gray-500">/{{ $t('pricing.monthly') }}</span>
        </div>
        <p v-if="yearlySaving" class="text-sm text-green-600 font-medium">
          {{ $t('pricing.savePercent', { percent: yearlySaving }) }}
        </p>
      </div>
    </template>
    
    <ul class="space-y-3 flex-1">
      <li v-for="feature in features" :key="feature" 
          class="flex items-start gap-2">
        <UIcon name="i-heroicons-check-circle" 
               class="w-5 h-5 text-green-500 flex-shrink-0 mt-0.5" />
        <span class="text-sm">{{ feature }}</span>
      </li>
    </ul>
    
    <template #footer>
      <UButton 
        :color="popular ? 'primary' : 'gray'"
        :variant="popular ? 'solid' : 'outline'"
        block
        size="lg"
        :to="ctaLink"
      >
        {{ cta }}
      </UButton>
    </template>
  </UCard>
</template>

<script setup lang="ts">
interface Props {
  name: string
  desc: string
  monthlyPrice: number
  yearlyPrice: number
  isYearly: boolean
  features: string[]
  cta: string
  ctaLink: string
  popular?: boolean
}

const props = withDefaults(defineProps<Props>(), { popular: false })

const displayPrice = computed(() => 
  props.isYearly ? props.yearlyPrice : props.monthlyPrice
)

const yearlySaving = computed(() => {
  if (!props.isYearly) return null
  const saving = Math.round((1 - props.yearlyPrice / props.monthlyPrice) * 100)
  return saving > 0 ? saving : null
})
</script>
```

### 4.3 首頁 Hero Section

```vue
<!-- app/components/landing/HeroSection.vue -->
<template>
  <section class="relative overflow-hidden bg-gradient-to-b from-white to-gray-50 pt-20 pb-32">
    <!-- 背景裝飾 -->
    <div class="absolute inset-0 -z-10">
      <div class="absolute top-0 right-0 w-[600px] h-[600px] 
                  bg-primary-100/30 rounded-full blur-3xl -translate-y-1/2 translate-x-1/4" />
    </div>
    
    <div class="container mx-auto px-4 max-w-6xl">
      <div class="grid lg:grid-cols-2 gap-12 items-center">
        <!-- 左側文字 -->
        <div class="space-y-6">
          <!-- Badge -->
          <UBadge variant="subtle" color="primary" size="lg" 
                  icon="i-heroicons-sparkles">
            {{ $t('hero.badge') }}
          </UBadge>
          
          <!-- H1 -->
          <h1 class="text-4xl lg:text-5xl font-black text-gray-900 leading-tight">
            {{ $t('hero.title') }}
          </h1>
          
          <!-- Subtitle -->
          <p class="text-xl text-gray-600 leading-relaxed">
            {{ $t('hero.subtitle') }}
          </p>
          
          <!-- CTA Buttons -->
          <div class="flex flex-wrap gap-4">
            <UButton size="xl" color="primary" :to="localePath('/demo')">
              {{ $t('hero.cta') }}
            </UButton>
            <UButton size="xl" variant="ghost" 
                     icon="i-heroicons-play-circle"
                     :to="localePath('/demo#video')">
              {{ $t('hero.ctaSecondary') }}
            </UButton>
          </div>
          
          <!-- Social Proof -->
          <div class="flex items-center gap-4 text-sm text-gray-500">
            <div class="flex items-center gap-1">
              <UIcon name="i-heroicons-star" class="text-yellow-400" />
              <span>4.9★</span>
            </div>
            <span>•</span>
            <span>14日免費試用</span>
            <span>•</span>
            <span>無需信用卡</span>
          </div>
        </div>
        
        <!-- 右側 Mockup -->
        <div class="hidden lg:block">
          <NuxtImg 
            src="/images/hero-mockup.png" 
            alt="Area2 AI WhatsApp 示範"
            class="w-full max-w-lg mx-auto drop-shadow-2xl"
            width="500" height="600"
            loading="eager"
          />
        </div>
      </div>
    </div>
  </section>
</template>
```

## 5. Server API 實作

### 5.1 聯絡表單 API

```typescript
// server/api/contact.post.ts
import { Resend } from 'resend'
import { z } from 'zod'

const schema = z.object({
  name: z.string().min(1).max(100),
  email: z.string().email(),
  company: z.string().optional(),
  message: z.string().min(10).max(2000),
  phone: z.string().optional(),
})

export default defineEventHandler(async (event) => {
  const config = useRuntimeConfig()
  const body = await readBody(event)
  
  const result = schema.safeParse(body)
  if (!result.success) {
    throw createError({ statusCode: 400, message: 'Invalid input' })
  }
  
  const resend = new Resend(config.resendApiKey)
  
  await resend.emails.send({
    from: 'Area2 AI <noreply@area2ai.hk>',
    to: 'hello@area2ai.hk',
    subject: `新查詢：${result.data.name} (${result.data.company ?? '未提供'})`,
    html: `
      <h2>新聯絡表單</h2>
      <p><strong>姓名：</strong>${result.data.name}</p>
      <p><strong>Email：</strong>${result.data.email}</p>
      <p><strong>公司：</strong>${result.data.company ?? '未提供'}</p>
      <p><strong>訊息：</strong>${result.data.message}</p>
    `,
  })
  
  return { success: true }
})
```

## 6. Cloudflare Pages 部署設定

### 6.1 public/_headers

```
/*
  X-Frame-Options: DENY
  X-Content-Type-Options: nosniff
  Referrer-Policy: strict-origin-when-cross-origin
  Permissions-Policy: camera=(), microphone=(), geolocation=()

/
  Cache-Control: no-cache, no-store, must-revalidate

/index.html
  Cache-Control: no-cache, no-store, must-revalidate

/_nuxt/*
  Cache-Control: public, max-age=31536000, immutable
```

### 6.2 public/_redirects

```
/* /index.html 200
```

### 6.3 GitHub Actions 自動部署

```yaml
# .github/workflows/deploy.yml
name: Deploy to Cloudflare Pages

on:
  push:
    branches: [main]

jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      
      - uses: actions/setup-node@v4
        with:
          node-version: '22'
          cache: 'npm'
      
      - run: npm ci
      - run: npm run build
        env:
          NUXT_PUBLIC_GA_MEASUREMENT_ID: ${{ secrets.GA_MEASUREMENT_ID }}
      
      - uses: cloudflare/pages-action@v1
        with:
          apiToken: ${{ secrets.CF_API_TOKEN }}
          accountId: ${{ secrets.CF_ACCOUNT_ID }}
          projectName: area2-ai-website
          directory: .output/public
          gitHubToken: ${{ secrets.GITHUB_TOKEN }}
```

## 7. 效能優化清單

- [ ] Core Web Vitals 目標：LCP < 2.5s, FID < 100ms, CLS < 0.1
- [ ] 圖片全部用 WebP/AVIF 格式
- [ ] Critical CSS inline
- [ ] Font 使用 `font-display: swap`
- [ ] 第三方腳本 lazy load（GA4、Hotjar）
- [ ] Bundle size 目標：< 200KB gzip
- [ ] 預渲染關鍵頁面（/, /pricing, /features）

## 8. 安全設定

```typescript
// nuxt.config.ts 加入
security: {
  headers: {
    contentSecurityPolicy: {
      'default-src': ["'self'"],
      'script-src': ["'self'", "'unsafe-inline'", 'https://www.googletagmanager.com'],
      'style-src': ["'self'", "'unsafe-inline'"],
      'img-src': ["'self'", 'data:', 'https:'],
      'connect-src': ["'self'", 'https://api.resend.com'],
    },
  },
},
```
