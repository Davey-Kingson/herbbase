# Vercel 快速部署指南

## 🚀 方法一：通過 Vercel 網站部署（推薦）

### 1. 準備 GitHub 倉庫
1. 在 GitHub 創建新倉庫 `chinese-herbs-database`
2. 將項目文件上傳到倉庫

### 2. 連接 Vercel
1. 訪問 [vercel.com](https://vercel.com)
2. 使用 GitHub 帳號登錄
3. 點擊 "New Project"
4. 選擇您的 `chinese-herbs-database` 倉庫

### 3. 配置部署設置
```
Framework Preset: Vite
Build Command: npm run build
Output Directory: dist
Install Command: npm install
```

### 4. 部署
- 點擊 "Deploy" 按鈕
- 等待構建完成（通常1-2分鐘）
- 獲得您的網站地址：`https://your-project.vercel.app`

## 🚀 方法二：通過 Vercel CLI 部署

### 1. 安裝 Vercel CLI
```bash
npm i -g vercel
```

### 2. 登錄 Vercel
```bash
vercel login
```

### 3. 部署項目
```bash
# 在項目根目錄執行
vercel --prod
```

## ⚙️ 自定義域名設置

### 1. 在 Vercel 控制台
1. 進入項目設置
2. 點擊 "Domains" 標籤
3. 添加您的自定義域名

### 2. 配置 DNS
在您的域名提供商處添加以下記錄：
```
Type: CNAME
Name: www (或您的子域名)
Value: cname.vercel-dns.com
```

## 🔧 環境變量（如需要）

在 Vercel 控制台的 "Environment Variables" 中添加：
```
NODE_ENV=production
```

## 📊 性能優化

Vercel 自動提供：
- 全球 CDN 加速
- 自動 HTTPS
- 圖片優化
- 緩存優化

## 🛠️ 故障排除

### 構建失敗
1. 檢查 Node.js 版本（需要 18+）
2. 確認所有依賴已正確安裝
3. 查看構建日誌中的錯誤信息

### 圖片無法顯示
1. 確認圖片在 `public/images/herbs/` 目錄
2. 檢查圖片路徑是否正確
3. 確認圖片文件名大小寫匹配

### 路由問題
Vercel 自動處理 SPA 路由，無需額外配置。

---

# Netlify 快速部署指南

## 🚀 方法一：拖拽部署

### 1. 構建項目
```bash
npm run build
```

### 2. 部署
1. 訪問 [netlify.com](https://netlify.com)
2. 將 `dist` 文件夾拖拽到部署區域
3. 等待部署完成

## 🚀 方法二：GitHub 集成

### 1. 連接 GitHub
1. 在 Netlify 點擊 "New site from Git"
2. 選擇 GitHub 並授權
3. 選擇您的倉庫

### 2. 配置構建設置
```
Build command: npm run build
Publish directory: dist
```

### 3. 部署
點擊 "Deploy site" 完成部署。

---

# GitHub Pages 部署指南

## 🚀 自動部署設置

### 1. 安裝依賴
```bash
npm install --save-dev gh-pages
```

### 2. 修改 package.json
添加 homepage 和 deploy 腳本：
```json
{
  "homepage": "https://yourusername.github.io/chinese-herbs-database",
  "scripts": {
    "deploy": "gh-pages -d dist"
  }
}
```

### 3. 部署
```bash
npm run build
npm run deploy
```

### 4. 啟用 GitHub Pages
1. 在 GitHub 倉庫設置中
2. 找到 "Pages" 部分
3. 選擇 "gh-pages" 分支作為源

---

## 🎯 部署檢查清單

### 部署前確認
- [ ] 所有圖片文件已包含在 `public/images/herbs/` 目錄
- [ ] 項目可以本地正常構建 (`npm run build`)
- [ ] 所有依賴已正確安裝
- [ ] 配置文件已更新

### 部署後測試
- [ ] 網站可以正常訪問
- [ ] 所有中藥材卡片可以點擊
- [ ] 圖片可以正常顯示和下載
- [ ] 身份驗證功能正常
- [ ] 性狀鑑定頁面內容完整
- [ ] 手機端顯示正常

## 📞 技術支持

如遇到部署問題：
1. 檢查構建日誌
2. 確認 Node.js 版本
3. 查看瀏覽器控制台錯誤
4. 參考平台官方文檔

