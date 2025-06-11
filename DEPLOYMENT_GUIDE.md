# 中藥資源數據庫 - 獨立部署指南

## 🌐 項目概述

這是一個專業的中藥資源數據庫，包含27種中藥材的詳細信息、圖片檢視、性狀鑑定等功能。

## 🚀 推薦部署平台

### 1. Vercel (最推薦)
- **優點**：免費、快速、支持React、自動HTTPS、全球CDN
- **適用**：個人和商業項目
- **域名**：提供免費子域名，支持自定義域名

### 2. Netlify
- **優點**：免費、易用、支持表單處理
- **適用**：靜態網站
- **域名**：提供免費子域名，支持自定義域名

### 3. GitHub Pages
- **優點**：完全免費、與GitHub集成
- **適用**：開源項目
- **域名**：username.github.io/repository-name

## 📋 部署前準備

### 系統要求
- Node.js 18+ 
- npm 或 pnpm
- Git

### 項目結構
```
chinese-herbs-database/
├── public/
│   ├── images/herbs/          # 中藥材圖片
│   └── index.html
├── src/
│   ├── components/            # React組件
│   ├── App.jsx               # 主應用
│   └── main.jsx              # 入口文件
├── package.json              # 依賴配置
├── vite.config.js           # 構建配置
└── README.md                # 說明文檔
```

## 🔧 本地開發

### 1. 安裝依賴
```bash
npm install
# 或
pnpm install
```

### 2. 啟動開發服務器
```bash
npm run dev
# 或
pnpm run dev
```

### 3. 構建生產版本
```bash
npm run build
# 或
pnpm run build
```

## 🌐 部署到 Vercel

### 方法一：通過 Vercel CLI
1. 安裝 Vercel CLI
```bash
npm i -g vercel
```

2. 登錄 Vercel
```bash
vercel login
```

3. 部署項目
```bash
vercel --prod
```

### 方法二：通過 GitHub 集成
1. 將代碼推送到 GitHub
2. 訪問 [vercel.com](https://vercel.com)
3. 點擊 "New Project"
4. 選擇您的 GitHub 倉庫
5. 配置構建設置：
   - Framework Preset: Vite
   - Build Command: `npm run build`
   - Output Directory: `dist`
6. 點擊 "Deploy"

## 🌐 部署到 Netlify

### 方法一：拖拽部署
1. 運行 `npm run build` 構建項目
2. 訪問 [netlify.com](https://netlify.com)
3. 將 `dist` 文件夾拖拽到部署區域

### 方法二：GitHub 集成
1. 將代碼推送到 GitHub
2. 在 Netlify 中連接 GitHub 倉庫
3. 配置構建設置：
   - Build command: `npm run build`
   - Publish directory: `dist`

## 🌐 部署到 GitHub Pages

### 1. 安裝 gh-pages
```bash
npm install --save-dev gh-pages
```

### 2. 修改 package.json
```json
{
  "scripts": {
    "deploy": "gh-pages -d dist"
  },
  "homepage": "https://yourusername.github.io/chinese-herbs-database"
}
```

### 3. 部署
```bash
npm run build
npm run deploy
```

## ⚙️ 環境配置

### Vite 配置 (vite.config.js)
```javascript
import { defineConfig } from 'vite'
import react from '@vitejs/plugin-react'
import path from 'path'

export default defineConfig({
  plugins: [react()],
  resolve: {
    alias: {
      '@': path.resolve(__dirname, './src'),
    },
  },
  base: './', // 用於相對路徑部署
})
```

## 🔒 自定義域名

### Vercel
1. 在項目設置中點擊 "Domains"
2. 添加您的域名
3. 配置 DNS 記錄指向 Vercel

### Netlify
1. 在站點設置中點擊 "Domain management"
2. 添加自定義域名
3. 配置 DNS 記錄

### GitHub Pages
1. 在倉庫設置中找到 "Pages" 部分
2. 添加自定義域名
3. 配置 DNS 記錄

## 🛠️ 故障排除

### 常見問題

1. **圖片無法顯示**
   - 確保圖片路徑正確
   - 檢查 `public/images/herbs/` 目錄

2. **路由問題**
   - 配置服務器重定向到 `index.html`
   - 使用 Hash 路由模式

3. **構建失敗**
   - 檢查 Node.js 版本
   - 清除 node_modules 重新安裝

### 性能優化

1. **圖片優化**
   - 壓縮圖片文件
   - 使用 WebP 格式

2. **代碼分割**
   - 使用 React.lazy() 懶加載
   - 分離第三方庫

3. **緩存策略**
   - 配置適當的緩存頭
   - 使用 CDN 加速

## 📞 技術支持

如果在部署過程中遇到問題，可以：
1. 檢查構建日誌
2. 查看瀏覽器控制台錯誤
3. 參考平台官方文檔

## 📄 許可證

本項目僅供學習和研究使用。

